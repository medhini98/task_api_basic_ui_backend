# Todo API (Basic FastAPI Backend)

A minimal FastAPI backend that provides a RESTful API for managing todo tasks.
Designed to support a React frontend while keeping the backend simple, explicit, and easy to reason about.

---

## Features
- In-memory task storage (no database dependency)
- RESTful CRUD endpoints
- Input validation using Pydantic models
- Clear HTTP status codes and error handling
- Designed for easy frontend integration

---

## Tech Stack
- FastAPI - API framework
- Pydantic - Data validation and serialization
- Uvicorn - ASGI server
- Python 3.12

---

## API Endpoints

| Method | Endpoint        | Description                   |
|------|-----------------|-------------------------------|
| GET  | /todos/         | Fetch all tasks               |
| POST | /todos/         | Create a new task             |
| GET  | /todos/{id}     | Fetch task by ID              |
| PATCH| /todos/{id}     | Partially update a task       |
| PUT  | /todos/{id}     | Replace an entire task        |
| DELETE | /todos/{id}   | Delete a task                 |

---

Task Model (Simplified)
```json
{
  "id": "uuid",
  "title": "string",
  "description": "string | null",
  "completed": false,
  "created_at": "ISO datetime"
}
```

--- 

## Running the API Locally
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

---

## Design Notes
- Uses an in-memory list to keep focus on API behavior rather than persistence
- Explicit validation for:
- Empty task titles
- Duplicate task titles
- Separation of concerns via:
- Routers
- Pydantic schemas
- Helper functions

---

## Frontend Integration

This API is consumed by a React frontend that supports:
- Task creation
- Completion toggling
- Deletion with confirmation
- Error handling and loading states
