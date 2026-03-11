# Domain: Web Development

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| Static site | HTML + CSS + Vanilla JS | Zero dependencies, fastest to deploy |
| Interactive UI | React (if needed) | Industry standard for dynamic UIs |
| Styling | Tailwind CSS | Utility-first, fast to write |
| Backend (simple) | Flask | Lightweight, Python-native |
| Backend (full) | FastAPI | Modern, async, auto-docs |
| Database | SQLite (dev) / PostgreSQL (prod) | SQLite for local, Postgres for production |
| Auth | Flask-Login / JWT | Simple session vs stateless tokens |
| Hosting (static) | GitHub Pages / Netlify | Free, deploy from GitHub |
| Hosting (full-stack) | Render / Railway | Free tier, auto-deploy |

## Best Practices

- Mobile-first design — test on small screen first
- Use semantic HTML (`<nav>`, `<main>`, `<section>`) not just `<div>` everywhere
- CSS variables for colors and fonts — makes theming easy
- Never put sensitive logic in frontend JS — always validate on the server too
- Use HTTPS everywhere — Render/Netlify handle this automatically
- Add a `.gitignore` — never commit `node_modules/` or `.env`
- For Flask: use `app.config` for settings, not hardcoded values
- Input validation on both client (UX) and server (security)
- Add loading states for async operations — users shouldn't stare at a blank screen
