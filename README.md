# B2B SaaS

A small B2B task board application (Kanban-style) with a FastAPI backend and a React + Vite frontend. This repository contains a minimal, extensible starter for building a task/kanban product with Clerk authentication and Svix webhooks.

---

## 🚀 Quick overview

- **Backend:** FastAPI, SQLAlchemy, Svix (webhooks), Clerk for auth
- **Frontend:** React, Vite, Clerk React
- **Database:** SQLite by default (configurable via `DATABASE_URL`)
- **Local ports:** Backend — `http://localhost:8000`, Frontend — `http://localhost:5173`

---

## 🧭 Project structure

- `/backend` — FastAPI app
  - `start.py` — quick entrypoint for running the backend
  - `app/` — application package (routers, core, models, schemas)
  - `example.env` — example env file (copy to `.env`)
- `/frontend` — React + Vite SPA
  - `src/` — components, pages, services
- `README.md` — this file

---

## ⚙️ Local setup

Prerequisites:

- Python 3.13+
- Node 18+ / npm
- Git

Backend

1. Open a terminal and change into the backend directory:

   ```bash
   cd backend
   ```

2. Create and activate a virtual environment:

   Windows (PowerShell):

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   macOS / Linux / WSL:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies from `pyproject.toml`:

   ```bash
   python -m pip install --upgrade pip
   python -m pip install -e .
   ```

4. Copy `example.env` to `.env` and fill in secrets (e.g., Clerk keys, webhook secret):

   ```bash
   cp example.env .env
   ```

   Important env vars to set:

   - `CLERK_SECRET_KEY`, `CLERK_PUBLISHABLE_KEY`, `CLERK_JWKS_URL`, `CLERK_WEBHOOK_SECRET`
   - `DATABASE_URL` (default: `sqlite:///./taskboard.db`)
   - `FRONTEND_URL` (pointing to your frontend dev URL e.g. `http://localhost:5173`)

5. Run the backend:

   ```bash
   python start.py
   ```

   Open the automatic docs at: `http://localhost:8000/docs` (Swagger UI).

Frontend

1. In a separate terminal, change into the frontend folder:

   ```bash
   cd frontend
   npm install
   npm run dev
   ```

2. Open the app at `http://localhost:5173`.

---

## 🧪 Development tips

- Frontend linting: `cd frontend && npm run lint`
- Backend DB: By default this project uses SQLite for quick local dev; to use another DB, set `DATABASE_URL` and run migrations if you add them.
- Webhooks: Svix is used to receive external events — ensure `CLERK_WEBHOOK_SECRET` is set to validate payloads.

---

## 🧩 Contributing

- Fork, create a feature branch, and open a PR with a clear description.
- Add tests and update docs for new features.

---

## 📄 License

Add a `LICENSE` file to this repository. If none is present, assume "No license" — contact the maintainer to confirm.


