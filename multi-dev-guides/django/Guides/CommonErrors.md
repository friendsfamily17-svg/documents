Django — Common Errors & Fixes

Common issues and quick fixes for contributors new to Django projects:

- "ImproperlyConfigured: settings" — ensure `DJANGO_SETTINGS_MODULE` and `.env` values are correct.
- Database connection errors: verify `DATABASE_URL` and that Postgres is running.
- Missing migrations: run `python manage.py makemigrations` and include migration files in PRs.
- Static files missing in production: run `python manage.py collectstatic` and configure your web server to serve static files.
- Local email not sending: configure `EMAIL_BACKEND` and use console backend for dev (`EMAIL_BACKEND=django.core.mail.backends.console.EmailBackend`).
- Permissions and file uploads: check media directory permissions and `MEDIA_ROOT`/`MEDIA_URL` settings.

If a project-specific common error appears often, add it here with repro steps and a fix.
