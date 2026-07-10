# Issue Tracker API

A lightweight REST API for managing issues, built with [FastAPI](https://fastapi.tiangolo.com/). Issues are stored in a JSON file and exposed through versioned CRUD endpoints.

## Live Demo

| Resource | URL |
|----------|-----|
| List all issues | [https://issue-tracker-fastapi-bjyv.onrender.com/api/v1/issues/](https://issue-tracker-fastapi-bjyv.onrender.com/api/v1/issues/) |
| Interactive API docs | [https://issue-tracker-fastapi-bjyv.onrender.com/docs](https://issue-tracker-fastapi-bjyv.onrender.com/docs) |

Use the Swagger UI at `/docs` to create, update, and delete issues without writing any client code.

## API Endpoints

All routes are prefixed with `/api/v1/issues`.

| Method | Path | Description |
|--------|------|-------------|
| `GET` | `/` | List all issues |
| `POST` | `/` | Create a new issue |
| `GET` | `/{issue_id}` | Get an issue by ID |
| `PUT` | `/{issue_id}` | Update an issue |
| `DELETE` | `/{issue_id}` | Delete an issue |

### Issue fields

- **title** — 3–100 characters
- **description** — 5–1000 characters
- **priority** — `low`, `medium`, or `high` (default: `medium`)
- **status** — `open`, `in_progress`, or `closed` (default: `open` on create)

## Local Setup

```bash
# Clone and enter the project
git clone <repo-url>
cd issue-tracker-fastapi

# Create a virtual environment and install dependencies
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Run the dev server
uvicorn main:app --reload
```

The API will be available at `http://127.0.0.1:8000`. Local docs are at `http://127.0.0.1:8000/docs`.

## Tech Stack

- **FastAPI** — API framework
- **Pydantic** — request/response validation
- **Uvicorn** — ASGI server
- **JSON file storage** — simple persistence via `data/issues.json`
