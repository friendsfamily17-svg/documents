Node.js (Express) — Common Errors & Fixes

This file lists common issues new contributors encounter and quick troubleshooting steps.

- "EACCES / permission denied" when installing global packages: use `nvm` or avoid `sudo` for npm installs.
- "Port already in use": change `PORT` env var or kill the process (e.g. `lsof -i :3000` then `kill`).
- Missing environment variables: copy `.env.example` -> `.env` and verify all required keys are set.
- Database connection errors: verify DB URL, credentials, and that the database service is running (Postgres container or local instance).
- CORS errors: ensure CORS middleware is configured or allow required origins in dev.
- Migration failures: check migration tool logs (knex/sequelize/typeorm) and run migrations in a clean DB or rollback first.
- TypeScript build errors: run `npm run build` to see compiler messages; ensure `tsconfig.json` matches project structure.

If you discover a recurring, project-specific error, add it here with the fix steps.
