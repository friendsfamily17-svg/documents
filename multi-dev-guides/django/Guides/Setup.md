# Django — Setup

Quick start for a Django project:

1. Create and activate a Python virtual environment (recommended Python 3.10+):

- `python -m venv .venv`
- `source .venv/bin/activate`
- `pip install -r requirements.txt`

2. Environment variables: copy `.env.example` to `.env` and fill `DATABASE_URL`, `SECRET_KEY`, etc.

3. Run migrations and start dev server:

- `python manage.py migrate`
- `python manage.py runserver`

4. Static files (for production):

- `python manage.py collectstatic --noinput`

5. Tests:

- `python manage.py test`

6. Docker: use `docker-compose up --build` if the project ships containers.

Notes:

- For Postgres use: `DATABASE_URL=postgres://user:pass@localhost:5432/dbname`.
- The project may use Django ORM migrations; ensure migrations are included in PRs and reviewed.
