# MBPT Project Specification

This document summarizes the backend and frontend specifications and provides installation steps for each component.

**Backend Specification**

- Stack: Node.js with NestJS 11, TypeScript 5.7, TypeORM 0.3, PostgreSQL.
- API: Global prefix `/api`, default port `3000`, CORS enabled for `http://localhost:5173`, validation via global `ValidationPipe` (whitelist).
- Modules: `introduction`, `question`, `result`, `result-profile`, `email`, `pdf`.
- Data access: TypeORM with `autoLoadEntities`, migrations and seeds via npm scripts.
- Utilities: `nodemailer` for SMTP email, `pdfkit` for PDF generation.
- Tooling: Jest for tests, ESLint + Prettier for lint/format, Nest CLI for build and dev.

**Backend Installation**

Requirements: Node.js (LTS recommended), npm, PostgreSQL.

```bash
cd backend
npm install
```

Create or update `backend/.env`:

```
DATABASE_URL=postgres://<user>:<pass>@<host>:<port>/<db>
SMTP_HOST=<smtp_host>
SMTP_PORT=<smtp_port>
SMTP_USER=<smtp_user>
SMTP_PASS=<smtp_pass>
```

Run locally:

```bash
npm run start:dev
```

Optional database scripts:

```bash
npm run migration:run
npm run migration:seed
```
