# Production deployment: Russian localization for Spree 6.0.2

Date: 2026-11-06

## Release

- Spree backend/operator/seller/API/email image: `spree-ru:6.0.2-ru-orders-20261106`.
- Buyer storefront image: `spree-storefront-ru:6.0.2-20261106-r2` (`sha256:173813765f7d9c2579f8c87c9f29793e6c67ac2ed9bdd5990d2b1ccf3649d912`).
- Storefront URL: `https://spree.za100lompro.ru/shop`; `/shop` redirects to `/shop/ru/ru`.
- Existing operator and seller panels remain at `/dashboard` and `/sellers`.
- Caddy routes `/shop/*` to a loopback-only storefront service on port `43179`; the Spree API remains the default route.

## Verification

- Storefront build completed with `STOREFRONT_BASE_PATH=/shop` and the production Russian Market.
- Locale parity check passed for `de`, `es`, `fr`, `pl`, and `ru`.
- Storefront middleware tests passed: 23 tests across the middleware and proxy test files.
- Chromium checks returned HTTP 200 for the Russian home, catalog, cart, and anonymous account sign-in. The catalog title is `Все товары | Магазин Spree`; its empty state is in Russian. No browser JavaScript errors were observed.
- Production operator orders page shows `Новый заказ` once and `New Order` zero times.
- Production `/up`, `/dashboard`, `/sellers`, `/shop/ru/ru`, `/shop/ru/ru/products`, and `/shop/ru/ru/cart` returned HTTP 200. `/shop` returned the expected HTTP 302 redirect.
- PostgreSQL remained healthy. No production database migration or product mutation was performed.
- Backup `/opt/spree/backups/automatic/20261106T121144Z-965586` passed checksum and `pg_restore -l` checks.

## Rollback

- Storefront release files, source checksums, previous Caddy configuration, image metadata, and rollback script are in `/opt/spree-storefront/releases/ru-6.0.2-20261106/`.
- Run `/opt/spree-storefront/releases/ru-6.0.2-20261106/rollback.sh` to remove the storefront service and restore the previous Caddy configuration.
- Backend rollback remains at `/opt/spree/releases/ru-6.0.2-20261106-orders/rollback.sh`.

## Current catalog state

The production default Market is Russia, but it currently has zero active products. The buyer-facing catalog therefore displays its translated empty state; product discovery through checkout and a real purchase could not be exercised without published products and payment configuration.
