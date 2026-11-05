# Тестовое окружение для русской локализации Spree 6.0.2

## Исходный код

- База: официальный тег `v6.0.2` (`439f7350926011abc4a986e7e8373299fb405e68`).
- Рабочая ветка форка: `feature/russian-localization-6.0.2`.
- Зависимости JS: `pnpm-lock.yaml`, установка `pnpm install --frozen-lockfile` с pnpm `11.1.1`.
- Исходная проверка: сборки `@spree/dashboard-starter...` и `@spree/seller-dashboard-starter...` проходят.

## Сервисы стенда

Воспроизводить из рабочей копии, расположенной в каталоге, доступном UID 1000 контейнера Rails (например, `/tmp/spree-ru-localization`). Контейнер Rails не может читать путь, закрытый правами `/root`.

`server/` — отдельный клон `spree/spree-starter`; его `.env` содержит только путь к этому checkout. Внутри Gemfile добавлен `ostruct`: Ruby 4.0.9 в контейнере его больше не включает по умолчанию, хотя его вызывает `stringex` из locked bundle.

Стенд поднимается отдельным Compose-проектом `spree-ru-test`:

- Rails API: `http://127.0.0.1:3300`;
- PostgreSQL 18: `127.0.0.1:5433`, отдельный volume `spree-ru-test_postgres_data`;
- Mailpit: SMTP `127.0.0.1:1025`, web `http://127.0.0.1:8025`;
- операторская панель: `http://127.0.0.1:5173`;
- панель продавца: `http://127.0.0.1:5174`.

Rails создаёт отдельные пустые базы `spree_development` и `spree_test`; они не подключены к рабочему магазину. Rails, PostgreSQL, Mailpit и обе панели привязаны к loopback-интерфейсу.

Прокси панелей на Rails задаётся в `packages/dashboard-starter/.env.local` и `packages/seller-dashboard-starter/.env.local`:

```dotenv
VITE_API_PROXY_TARGET=http://127.0.0.1:3300
```

## Запуск

Из корня checkout, задав новый случайный `SECRET_KEY_BASE` для локального процесса:

```bash
pnpm install --frozen-lockfile
SPREE_PATH="$PWD" SPREE_PORT=127.0.0.1:3300 SECRET_KEY_BASE="$(openssl rand -hex 64)" \
  docker compose -p spree-ru-test \
  -f server/docker-compose.dev.yml -f scripts/docker-compose.edge.yml up -d --build web

pnpm exec turbo build --filter=@spree/dashboard-starter... --output-logs=errors-only
pnpm exec turbo build --filter=@spree/seller-dashboard-starter... --output-logs=errors-only
pnpm --dir packages/dashboard-starter dev --host 127.0.0.1 --port 5173 --strictPort
pnpm --dir packages/seller-dashboard-starter dev --host 127.0.0.1 --port 5174 --strictPort
```

Сначала убедиться, что `/` на Rails отвечает перенаправлением на dashboard, а адреса панелей и Mailpit возвращают HTTP 200. Для новой базы Rails печатает ссылку одноразовой настройки администратора в своих логах; тестовые письма просматривать в Mailpit.

## Откат и остановка

Локализация работает в отдельной ветке. Откат к исходному коду выполняется переключением на тег `v6.0.2`; миграции и пользовательские данные рабочего магазина этот стенд не затрагивает. Для временной остановки контейнеров сохранить volumes:

```bash
docker compose -p spree-ru-test \
  -f server/docker-compose.dev.yml -f scripts/docker-compose.edge.yml stop
```

Для полного удаления только тестового проекта (включая тестовые базы и загруженные тестовые файлы):

```bash
docker compose -p spree-ru-test \
  -f server/docker-compose.dev.yml -f scripts/docker-compose.edge.yml down --volumes
```

`down --volumes` предназначена только для проекта `spree-ru-test`: перед выполнением проверить имя проекта у контейнеров. Не запускать общий `server:teardown` из этого окружения, поскольку он работает с обычным именем Compose-проекта.
