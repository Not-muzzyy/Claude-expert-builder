# Domain: Backend Development

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| Simple API | Flask | Minimal boilerplate, quick to build |
| Production API | FastAPI | Async, auto-docs, type-safe |
| Database ORM | SQLAlchemy | Works with SQLite, Postgres, MySQL |
| Lightweight DB | SQLite | Zero config, great for single-user apps |
| Production DB | PostgreSQL | Robust, free on Render/Railway |
| Task queue | Celery + Redis | For background jobs |
| Auth | JWT (PyJWT) | Stateless, scalable |
| API testing | Postman / httpie | Manual testing of endpoints |
| Environment | python-dotenv | Loads `.env` file for local dev |

## Best Practices

- Always version your API: `/api/v1/endpoint`
- Return consistent JSON: always include `status`, `data`, `message` fields
- Use HTTP status codes correctly: 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Server Error
- Validate and sanitize all incoming request data
- Never expose internal errors to the client — log them, return generic messages
- Use connection pooling for database connections in production
- Paginate list endpoints — never return unlimited results
- Rate limit public endpoints to prevent abuse
- Write at least basic integration tests for each endpoint
