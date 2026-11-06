# Инвентаризация русской пользовательской документации Spree 6.x

**Состояние:** выполнена сверка навигации и исходников; контент русский ещё не создан.  
**Дата сверки:** 2026-11-06  
**Источник навигации:** [`docs/docs.json`](../docs.json), `navigation.versions[v6.x].tabs[User Guide]`.  
**Метод:** все страницы User Guide v6.x извлечены из навигации; наличие исходного `.mdx` проверено. Изображения посчитаны по Markdown/HTML ссылкам, локальные пути проверены на диске. Внутренние ссылки посчитаны по Markdown-ссылкам вида `[текст](путь)`; метрики служат указателем для редакторской проверки, не заменяют просмотр страницы.

## Итог

- В User Guide v6.x: **80 навигационных страниц**; для каждой найден исходный `docs/<page>.mdx` (**80/80**).
- Первая очередь: **63 страницы** — настройка (24), заполнение каталога (16), ведение магазина и маркетплейса (23). Целевой путь: `docs/ru/<исходный путь>.mdx`.
- Отложено до следующей очереди: **17 страниц**, перечислены ниже. Это решение по приоритету первой русской версии, а не оценка актуальности функций.
- В `docs/user/` обнаружено **86 MDX-файлов**; шесть не включены в текущую навигацию. Четыре относятся к старым настройкам, два — к оптовому ценообразованию и имеют ссылки из текущих страниц (проверить отдельно).
- Скриншоты: **245 ссылок на изображения** на **56 страницах** первой очереди; недостающих локальных файлов по проверке путей: **0**. Каждый скриншот, показывающий интерфейс или текст шага, требует решения: переснять на русском либо обосновать повторное использование.

## Первая очередь страниц

| Раздел исходной навигации | Исходная страница | Заголовок EN | Поток | Медиа | Внутренние ссылки | RU destination |
|---|---|---|---|---:|---:|---|
| Manage / Introduction | `user/what-is-spree-commerce` | What is Spree Commerce | Настройка | 0 | 0 | `docs/ru/user/what-is-spree-commerce.mdx` |
| Manage / Introduction | `user/using-spree` | Using Spree Commerce | Настройка | 0 | 0 | `docs/ru/user/using-spree.mdx` |
| Manage / Introduction | `user/user-quickstart-guide` | User Quickstart | Настройка | 7 | 2 | `docs/ru/user/user-quickstart-guide.mdx` |
| Manage / Settings / Store | `user/settings/store-details` | Store Details | Настройка | 7 | 4 | `docs/ru/user/settings/store-details.mdx` |
| Manage / Settings / Selling | `user/settings/markets` | Markets | Настройка | 2 | 7 | `docs/ru/user/settings/markets.mdx` |
| Manage / Settings / Store | `user/settings/sales-channels` | Sales Channels | Настройка | 6 | 1 | `docs/ru/user/settings/sales-channels.mdx` |
| Manage / Settings / Marketplace | `user/settings/marketplace` | Marketplace Settings | Настройка | 5 | 6 | `docs/ru/user/settings/marketplace.mdx` |
| Manage / Settings / Marketplace | `user/settings/seller-requirements` | Seller Requirements | Настройка | 1 | 7 | `docs/ru/user/settings/seller-requirements.mdx` |
| Manage / Settings / Users & permissions | `user/settings/staff` | Staff | Настройка | 3 | 4 | `docs/ru/user/settings/staff.mdx` |
| Manage / Settings / Users & permissions | `user/settings/roles` | Roles | Настройка | 3 | 3 | `docs/ru/user/settings/roles.mdx` |
| Manage / Settings / Selling | `user/settings/payments` | Payment Methods | Настройка | 3 | 3 | `docs/ru/user/settings/payments.mdx` |
| Manage / Settings / Selling | `user/settings/taxes` | Taxes | Настройка | 0 | 10 | `docs/ru/user/settings/taxes.mdx` |
| Manage / Settings / Selling | `user/settings/tax-categories` | Tax Categories | Настройка | 2 | 6 | `docs/ru/user/settings/tax-categories.mdx` |
| Manage / Settings / Selling | `user/settings/tax-rates` | Tax Rates | Настройка | 2 | 7 | `docs/ru/user/settings/tax-rates.mdx` |
| Manage / Settings / Shipping & delivery | `user/settings/delivery-profiles` | Delivery Profiles | Настройка | 6 | 3 | `docs/ru/user/settings/delivery-profiles.mdx` |
| Manage / Settings / Shipping & delivery | `user/settings/locations` | Stock Locations | Настройка | 4 | 7 | `docs/ru/user/settings/locations.mdx` |
| Manage / Settings / Store | `user/settings/emails` | Emails | Настройка | 2 | 2 | `docs/ru/user/settings/emails.mdx` |
| Manage / Settings / Store | `user/settings/policies` | Policies | Настройка | 2 | 3 | `docs/ru/user/settings/policies.mdx` |
| Manage / Settings / Shipping & delivery | `user/settings/package-types` | Package Types | Настройка | 2 | 3 | `docs/ru/user/settings/package-types.mdx` |
| Manage / Settings / Shipping & delivery | `user/settings/returns-and-reasons` | Returns & Reasons | Настройка | 1 | 5 | `docs/ru/user/settings/returns-and-reasons.mdx` |
| Manage / How-to Guides | `user/how-to/multiple-languages` | Set Up Multiple Languages | Настройка | 8 | 0 | `docs/ru/user/how-to/multiple-languages.mdx` |
| Manage / How-to Guides | `user/how-to/multi-currency-pricing` | Set Up Multi-Currency Pricing | Настройка | 7 | 0 | `docs/ru/user/how-to/multi-currency-pricing.mdx` |
| Manage / How-to Guides | `user/how-to/multi-region-pricing` | Set Up Multi-Region Pricing | Настройка | 7 | 0 | `docs/ru/user/how-to/multi-region-pricing.mdx` |
| Manage / Security | `user/security` | Enterprise Edition Security Overview | Настройка | 0 | 0 | `docs/ru/user/security.mdx` |
| Manage / Products | `user/products/products` | Products | Каталог | 4 | 14 | `docs/ru/user/products/products.mdx` |
| Manage / Products | `user/products/adding-products` | Adding Products | Каталог | 12 | 23 | `docs/ru/user/products/adding-products.mdx` |
| Manage / Products | `user/products/categories` | Categories | Каталог | 3 | 7 | `docs/ru/user/products/categories.mdx` |
| Manage / Products | `user/products/variants` | Variants | Каталог | 4 | 9 | `docs/ru/user/products/variants.mdx` |
| Manage / Products | `user/products/options` | Options | Каталог | 5 | 4 | `docs/ru/user/products/options.mdx` |
| Manage / Products | `user/products/media` | Media | Каталог | 3 | 5 | `docs/ru/user/products/media.mdx` |
| Manage / Products | `user/products/collections` | Collections | Каталог | 3 | 5 | `docs/ru/user/products/collections.mdx` |
| Manage / Products | `user/products/custom-product-fields` | Custom Product Fields | Каталог | 3 | 7 | `docs/ru/user/products/custom-product-fields.mdx` |
| Manage / Products | `user/products/import-and-export` | Import & Export | Каталог | 2 | 8 | `docs/ru/user/products/import-and-export.mdx` |
| Manage / Products | `user/products/import-template` | Import Template | Каталог | 1 | 5 | `docs/ru/user/products/import-template.mdx` |
| Manage / Settings / Shipping & delivery | `user/settings/product-types` | Product Types | Каталог | 2 | 6 | `docs/ru/user/settings/product-types.mdx` |
| Manage / Settings / Store | `user/settings/custom-fields` | Custom Fields | Каталог | 3 | 4 | `docs/ru/user/settings/custom-fields.mdx` |
| Manage / Translations | `user/translations/translations` | Translations | Каталог | 3 | 6 | `docs/ru/user/translations/translations.mdx` |
| Manage / Catalogs | `user/catalogs/catalogs` | Catalogs | Каталог | 9 | 8 | `docs/ru/user/catalogs/catalogs.mdx` |
| Manage / Pricing | `user/pricing/price-lists` | Price Lists | Каталог | 5 | 9 | `docs/ru/user/pricing/price-lists.mdx` |
| Manage / Inventory | `user/inventory/stock-levels` | Inventory | Каталог | 2 | 7 | `docs/ru/user/inventory/stock-levels.mdx` |
| Manage / Orders | `user/orders/orders` | Orders | Операции | 2 | 11 | `docs/ru/user/orders/orders.mdx` |
| Manage / Orders | `user/orders/processing-orders` | Processing Orders | Операции | 12 | 18 | `docs/ru/user/orders/processing-orders.mdx` |
| Manage / Orders | `user/orders/draft-orders` | Draft Orders | Операции | 6 | 9 | `docs/ru/user/orders/draft-orders.mdx` |
| Manage / Orders | `user/orders/returns` | Returns | Операции | 5 | 9 | `docs/ru/user/orders/returns.mdx` |
| Manage / Orders | `user/orders/exchanges` | Exchanges | Операции | 4 | 9 | `docs/ru/user/orders/exchanges.mdx` |
| Manage / Orders | `user/orders/claims` | Claims | Операции | 3 | 10 | `docs/ru/user/orders/claims.mdx` |
| Manage / Inventory | `user/inventory/stock-transfers` | Stock Transfers | Операции | 7 | 5 | `docs/ru/user/inventory/stock-transfers.mdx` |
| Manage / Inventory | `user/inventory/purchase-orders` | Purchase Orders | Операции | 6 | 7 | `docs/ru/user/inventory/purchase-orders.mdx` |
| Manage / Inventory | `user/inventory/suppliers` | Suppliers | Операции | 1 | 3 | `docs/ru/user/inventory/suppliers.mdx` |
| Manage / Sellers | `user/sellers/sellers` | Sellers | Операции | 5 | 17 | `docs/ru/user/sellers/sellers.mdx` |
| Manage / Sellers | `user/sellers/onboarding` | Onboarding | Операции | 6 | 25 | `docs/ru/user/sellers/onboarding.mdx` |
| Manage / Sellers | `user/sellers/seller-panel` | Seller Panel | Операции | 5 | 15 | `docs/ru/user/sellers/seller-panel.mdx` |
| Manage / Sellers | `user/sellers/products` | Seller Products | Операции | 5 | 11 | `docs/ru/user/sellers/products.mdx` |
| Manage / Sellers | `user/sellers/orders` | Marketplace Orders | Операции | 5 | 12 | `docs/ru/user/sellers/orders.mdx` |
| Manage / Sellers | `user/sellers/commission-rates` | Commission Rates | Операции | 3 | 6 | `docs/ru/user/sellers/commission-rates.mdx` |
| Manage / Sellers | `user/sellers/transfers` | Seller Transfers | Операции | 2 | 8 | `docs/ru/user/sellers/transfers.mdx` |
| Manage / Sellers | `user/sellers/payouts` | Payouts | Операции | 5 | 11 | `docs/ru/user/sellers/payouts.mdx` |
| Manage / Reports | `user/reports/reports` | Reports | Операции | 0 | 3 | `docs/ru/user/reports/reports.mdx` |
| Manage / Customers | `user/customers/customers` | Customers | Операции | 4 | 7 | `docs/ru/user/customers/customers.mdx` |
| Manage / Customers | `user/customers/customer-profile` | Customer Profiles | Операции | 8 | 12 | `docs/ru/user/customers/customer-profile.mdx` |
| Manage / Promotions | `user/promotions/create-a-promotion` | Create a Promotion | Операции | 7 | 0 | `docs/ru/user/promotions/create-a-promotion.mdx` |
| Manage / Promotions | `user/promotions/promotion-rules` | Promotion Rules | Операции | 0 | 0 | `docs/ru/user/promotions/promotion-rules.mdx` |
| Manage / Promotions | `user/promotions/promotion-actions` | Promotion Actions | Операции | 0 | 0 | `docs/ru/user/promotions/promotion-actions.mdx` |

### Отложено из текущей v6.x навигации

| Исходная страница | Причина приоритета позже |
|---|---|
| `user/ai-agents/ai-agents` | Инструкции подключения AI-агентов; не входят в первичный рабочий путь настройки/каталога/операций. |
| `user/ai-agents/connect-chatgpt` | Инструкции подключения AI-агентов; не входят в первичный рабочий путь настройки/каталога/операций. |
| `user/ai-agents/connect-claude` | Инструкции подключения AI-агентов; не входят в первичный рабочий путь настройки/каталога/операций. |
| `user/customers/companies` | Расширенное управление B2B-клиентами; сначала нужно согласовать целевой сценарий и термины. |
| `user/customers/customer-groups` | Расширенное управление B2B-клиентами; сначала нужно согласовать целевой сценарий и термины. |
| `user/how-to/regional-volume` | Продвинутые сценарии оптового и объёмного ценообразования. |
| `user/how-to/schedule-sale-pricing` | Не входит в утверждённые приоритеты первой очереди; повторно оценить перед расширением. |
| `user/how-to/selling-to-businesses` | Отдельный B2B-сценарий; оставить кандидатом на последующее расширение. |
| `user/how-to/volume-pricing` | Продвинутые сценарии оптового и объёмного ценообразования. |
| `user/loyalty/gift-cards` | Лояльность; отдельный функциональный блок. |
| `user/loyalty/store-credits` | Лояльность; отдельный функциональный блок. |
| `user/migration/migrate-from-shopify` | Импортирующий сценарий для миграции с конкретной платформы. |
| `user/settings/allowed-origins` | Технические настройки, не нужны для обычной работы продавца или оператора. |
| `user/settings/api-keys` | Технические настройки, не нужны для обычной работы продавца или оператора. |
| `user/settings/imports` | Технические настройки, не нужны для обычной работы продавца или оператора. |
| `user/settings/integrations` | Настройка интеграций; объём зависит от подключённых расширений. |
| `user/settings/webhooks` | Технические настройки, не нужны для обычной работы продавца или оператора. |

## Файлы вне навигации

| Файл | Наблюдение | Решение для первой очереди |
|---|---|---|
| `user/how-to/regional-wholesale` | Есть исходные ссылки из `regional-volume`; точная проверка ссылок должна учитывать абсолютные URL на docs-домене. | Отдельно проверить актуальность и согласовать добавление в навигацию; не переводить молча как часть навигационной очереди. |
| `user/how-to/wholesale-pricing` | Упоминается текущими руководствами по объёмным/региональным продажам и customer groups. | Проверить свежесть и навигационный статус; до решения сохранить ссылки на английский источник. |
| `user/settings/metafields` | Старое название функции; актуальная навигация ведёт на `settings/custom-fields`. | Не переводить как отдельную страницу; можно перенести полезные детали только после сверки с актуальной страницей. |
| `user/settings/returns-configuration` | Файл отсутствует в текущем v6.x User Guide; v6.x использует `settings/returns-and-reasons`. | Не включать; проверить исходящие ссылки и архивность при последующем техдолге. |
| `user/settings/shipping-methods` | Вне текущей навигации; основная настройка доставки описана в `settings/delivery-profiles`. | Не включать без подтверждения, что отдельный поток остаётся актуальным. |
| `user/settings/zones` | Вне навигации; текущая модель настройки доставки описана страницами v6.x. | Не включать как самостоятельную инструкцию; проверить ссылки и актуальность понятий. |

## Подготовка строк интерфейса и снимков

На большинстве пошаговых страниц названия действий и полей выделены жирным, а скриншоты иллюстрируют конкретные состояния панели. При переводе нужно пройти страницу рядом с соответствующей версией панели и выписать точные названия элементов управления в отдельный редакторский checklist. Число медиа и ссылок в таблице — автоматическая подсказка о сложности проверки; оно не измеряет объём текста и не подтверждает, что интерфейсный термин актуален.

Для скриншотов применять правила основного плана: изображения с существенными для шага англоязычными элементами переснимать в русской панели; нейтральные схемы, фотографии и диаграммы можно оставить после проверки подписи и alt-текста. Русские скриншоты размещать в `docs/images/ru/user/...`, сохраняя соответствие источнику.

## Очередность

1. **Настройка (24):** обзор и quickstart, затем сведения магазина, рынки/каналы, marketplace и продавцы, платежи/налоги, доставка, сотрудники/роли, политики и локаль/валюта.
2. **Каталог (16):** создание и наполнение товаров, медиа/варианты/категории, импорты, типы и поля, переводы, каталоги, цены и остатки.
3. **Операции (23):** заказы и возвраты, закупка/перемещения, кабинеты продавцов и выплаты, отчёты, профиль клиента и промоакции.

Внутренние ссылки с исходных страниц на страницы первой очереди направлять на соответствующий `docs/ru/...` маршрут после публикации русской страницы. Ссылки на отложенные страницы оставить на английском и проверить, чтобы пользователь понимал смену языка.

## Ограничения результата

- Инвентаризация фиксирует источник и приоритет, но не переводит контент и не меняет `docs.json`.
- Текущий статус пользовательского docs site — Mintlify-навигация v6.x; русская ветка навигации ещё не заведена.
- Два не включённых в навигацию руководства по оптовым ценам связаны с текущими страницами. Перед включением русских ссылок владелец документации должен решить: добавить их в пользовательскую навигацию и локализовать либо обновить ссылки/содержание.
