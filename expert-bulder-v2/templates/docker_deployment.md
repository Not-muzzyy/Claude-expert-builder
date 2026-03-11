# Template: Docker Deployment + GitHub Actions CI/CD

## Dockerfile (Python app)

```dockerfile
# Use slim image to keep size small
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy and install dependencies first (layer caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy rest of app
COPY . .

# Never run as root
RUN useradd -m appuser
USER appuser

# Expose port
EXPOSE 8501

# Run app (adjust for Flask: use gunicorn)
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

## docker-compose.yml

```yaml
version: "3.9"

services:
  app:
    build: .
    ports:
      - "8501:8501"
    environment:
      - GROQ_API_KEY=${GROQ_API_KEY}
    restart: unless-stopped
    volumes:
      - ./data:/app/data

  # Optional: add a database service
  db:
    image: postgres:15
    environment:
      POSTGRES_DB: appdb
      POSTGRES_USER: appuser
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

## .dockerignore

```
__pycache__/
*.pyc
.env
.venv/
venv/
.git/
*.egg-info/
.DS_Store
*.log
```

## GitHub Actions CI/CD (.github/workflows/deploy.yml)

```yaml
name: Deploy

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.11"
      - run: pip install -r requirements.txt
      - run: python -m pytest tests/ -v

  deploy:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Deploy to Render
        run: |
          curl -X POST ${{ secrets.RENDER_DEPLOY_HOOK }}
```

## GitHub Actions — Lint Only (simpler)

```yaml
name: Lint

on: [push, pull_request]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.11"
      - run: pip install flake8
      - run: flake8 . --max-line-length=100 --exclude=venv,__pycache__
```

## Quick Docker Commands

```bash
# Build image
docker build -t my-app .

# Run container
docker run -p 8501:8501 --env-file .env my-app

# Run with compose
docker compose up --build

# Stop everything
docker compose down

# View logs
docker compose logs -f app
```
