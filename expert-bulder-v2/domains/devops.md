# Domain: DevOps

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| Containerization | Docker | Standard, works everywhere |
| Orchestration | Docker Compose (small) / Kubernetes (large) | Compose for dev/small prod |
| CI/CD | GitHub Actions | Free for public repos, easy to set up |
| Hosting | Render / Railway / VPS | Free tiers available |
| Monitoring | Uptime Robot (free) | Basic uptime alerts |
| Secrets | GitHub Secrets / .env | Never in code |
| Reverse proxy | Nginx | Standard for production |

## Best Practices

- One service per container — don't cram everything in one Docker image
- Use `.dockerignore` like `.gitignore` — keep images small
- Multi-stage builds to reduce final image size
- Never run containers as root in production
- Pin dependency versions in `requirements.txt` — `flask==3.0.0` not `flask`
- Health check endpoints (`/health`) for every service
- Automate everything that runs more than twice
- Read `templates/docker_deployment.md` for Dockerfile and compose templates
