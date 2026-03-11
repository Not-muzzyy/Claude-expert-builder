# Workflow: Deployment

Use when the user wants to host or go live with their project.

---

## Steps

### 1. Identify Runtime & Dependencies
Determine:
- Language/framework (Python/Streamlit, Flask, static HTML, etc.)
- Dependencies file exists? (requirements.txt, package.json)
- Secrets/API keys needed?

If `requirements.txt` is missing, generate it.

---

### 2. Select Platform

| Project Type | Best Free Option | Notes |
|---|---|---|
| Streamlit app | Streamlit Community Cloud | Easiest, 1-click from GitHub |
| Static site / HTML | GitHub Pages | Free, custom domain support |
| Python API / Flask | Render | Free tier, auto-deploy from GitHub |
| Full-stack web app | Railway or Render | Free tier available |
| ML model API | Hugging Face Spaces | Free, great for demos |
| Containerized app | Render + Docker | Free tier, reads Dockerfile |

Always recommend free tier unless user specifies otherwise.

---

### 3. Generate Config Files
Read `templates/docker_deployment.md` if Docker is involved.

Create required files:
- **Streamlit Cloud**: `requirements.txt` + `.streamlit/config.toml` (optional)
- **GitHub Pages**: nothing for static; `_config.yml` for Jekyll
- **Render**: `render.yaml` or start command
- **Docker**: `Dockerfile` + `docker-compose.yml`
- **Hugging Face**: README with YAML frontmatter + `requirements.txt`

Save to `/mnt/user-data/outputs/` and present.

---

### 4. Step-by-Step Deploy Commands
Give exact steps — no vague instructions. Example for Streamlit Cloud:

```
1. Push code to GitHub (public repo)
2. Go to share.streamlit.io → New app
3. Select repo, branch, main file (app.py)
4. Add secrets: Settings → Secrets (TOML format):
   GROQ_API_KEY = "your_key_here"
5. Click Deploy
```

---

### 5. Verify Deployment
After deploying, tell them what to check:
- App loads without errors?
- Secrets loading correctly? (test with a simple `st.write(bool(os.getenv("KEY")))`)
- Any platform-specific gotchas?

Offer to help debug if deploy fails.
