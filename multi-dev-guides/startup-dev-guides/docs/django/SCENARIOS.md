Django — SCENARIOS

Example scenarios for hands-on learning:

1) Add an API endpoint and serializer
   - Define serializer, view, URL, and tests.
   - Include migration if new models are required.

2) Safe DB migration with backfill
   - Add migration; write backfill as management command; test on a copy of the DB.

3) Deploying static assets and media
   - Ensure `collectstatic` runs in CI and that S3 / CDN is configured for media.

Reference templates in `../../templates/` and local setup in `../../../django/Guides/Setup.md`.
