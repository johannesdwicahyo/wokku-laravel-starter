# wokku-laravel-starter

Bare-bones Laravel 11 app on SQLite, configured to one-click-deploy on [Wokku](https://wokku.cloud).

## Deploy

Click → pick a tier → live at `https://<your-app>.wokku.cloud` in ~90 seconds.

## After first deploy

Set `APP_KEY` and `APP_URL` via the Wokku dashboard:

```
wokku config:set APP_KEY=base64:$(openssl rand -base64 32) APP_URL=https://<your-app>.wokku.cloud
```

## Local development

```bash
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
# open http://127.0.0.1:8000
```

## What's inside

- Laravel 11 default scaffold.
- SQLite for storage (`database/database.sqlite`). Swap to Postgres later by adding the `pg` driver and a Postgres addon.
- Heroku PHP buildpack with Apache serving `public/`.
- `release` Procfile command runs `php artisan migrate --force` on every deploy.

Runtime: PHP 8.3+ (from `composer.json` `require`; buildpack selects the latest supported 8.x).
