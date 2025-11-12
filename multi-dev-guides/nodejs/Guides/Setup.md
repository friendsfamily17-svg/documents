Node.js (Express) — Setup

Minimum sensible quick start (assumptions: Unix-like dev environment):

1. Install Node (recommended LTS, e.g., 18+). Use nvm to manage versions: `nvm install --lts` and `nvm use --lts`.

2. Clone the repo and install dependencies:

   - `git clone <repo>`
   - `cd <project>`
   - `npm install`

3. Environment variables: copy `.env.example` to `.env` and fill database / API keys.

4. Start local development server (typical npm scripts): `npm run dev` or `npm run start:dev`. Run tests with `npm test`.

5. Databases & migrations (Postgres example): create the DB (e.g. `createdb myapp_dev`) and run migration script (project may use knex/sequelize/typeorm; run the npm script provided, e.g. `npm run db:migrate`).

6. Docker (optional): use `docker-compose up --build` if service is containerized.

Notes:

- Use the templates in `../../startup-dev-guides/templates/` for PRD, SDD, and deployment checklists.
- If the project uses TypeScript, ensure `tsconfig.json` and `npm run build` steps are present.
