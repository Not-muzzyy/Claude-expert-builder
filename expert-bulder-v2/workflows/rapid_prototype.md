# Workflow: Rapid Prototype

Use when the user wants a working demo or MVP fast — no over-engineering.

## Goal
Get something running in the shortest time possible. Polish later.

---

## Steps

### 1. Define Scope (Ruthlessly)
Ask: "What's the ONE core thing this needs to do?"
Strip everything else. No auth, no database, no fancy UI — unless essential.

Output:
- Core feature (1 sentence)
- What's explicitly OUT of scope for now

---

### 2. Select Minimal Stack
Pick the simplest stack that works. Defaults:
- Python idea → Streamlit (no frontend needed)
- API → Flask (minimal boilerplate)
- Static tool → Plain HTML/JS (zero dependencies)
- Data viz → Streamlit + Plotly

Avoid anything that needs setup time (Docker, databases, auth) unless the user insists.

---

### 3. Implement Core Only
Read `engines/code_generation.md` and `engines/code_safety.md`.

Write just enough to demo the idea:
- Single file if possible (`app.py` or `index.html`)
- Hardcode sample data if needed — clean up later
- No tests, no abstraction, no design patterns yet
- Add a clear `# TODO: replace with real data` comment where shortcuts are taken

---

### 4. Run Check
Mentally verify:
- Can this be run with one command?
- Does it demonstrate the core idea clearly?
- Are there any import errors or obvious bugs?

---

### 5. Deliver + Next Steps
- Save file(s) to `/mnt/user-data/outputs/` and present
- Tell the user exactly how to run it (one command)
- List what to build next when ready to move beyond MVP:
  - Real data sources
  - Auth / user management
  - Proper error handling
  - Tests
  - Deployment
