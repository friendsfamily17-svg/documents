# Laravel — Setup

Short description
-----------------
Environment and common setup steps for Laravel projects used in startups.

## Requirements

- PHP 8.x, Composer, and a local DB (MySQL/Postgres).
- Install dependencies: `composer install`.

## Local dev

- Copy `.env.example` to `.env` and configure local DB credentials.
- Generate app key: `php artisan key:generate`.

## Common commands

```
php artisan migrate
php artisan serve
php artisan queue:work
```

## Troubleshooting

- If composer dependencies fail, run `composer update --lock` or check platform packages (ext-*).
