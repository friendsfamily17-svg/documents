# Python — Setup

Short description
-----------------
Environment setup for Python backend development, dependency management and common commands.

## Environment

- Install Python 3.10+ (use pyenv if needed).
- Create a virtual environment: `python -m venv .venv` and `source .venv/bin/activate`.

## Dependency management

- Use `requirements.txt` or `poetry`/`pipenv` for reproducible installs.
- Install: `pip install -r requirements.txt` or `poetry install`.

## Common commands

```
pytest
flake8
black .
python -m myapp
```

## Databases & Migrations

- Follow DB migration steps documented in the project (Alembic, Django migrations).

## Troubleshooting

- If imports fail, check your virtualenv activation and PYTHONPATH.
- If tests are failing due to flaky behavior, isolate and run with `-k` to debug.
