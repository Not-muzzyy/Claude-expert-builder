# Workflow: Build From Scratch

Use when the user has an idea and wants a complete project built.

## Steps

### 1. Interpret the Idea
Read `engines/idea_engine.md` first.

Ask or infer:
- What does the app do? Who uses it?
- What's the main input and output?
- Any tech preferences or constraints?

Produce:
- 2–3 sentence **problem definition**
- Clear **project goal** statement

Confirm with the user if anything is ambiguous before continuing.

---

### 2. Detect Domain + Stack
Identify the domain and read the relevant `domains/` file.
Recommend stack with a one-line reason for each choice.

Example:
> "Python + Streamlit (free, deployable, matches your stack) + Scikit-learn (ML) + Plotly (charts)"

---

### 3. Design Architecture
Read `engines/architecture_engine.md`.

Produce:
- ASCII system diagram
- Component list (what each part does)
- Data flow (how data moves through the system)

Keep it practical — don't over-engineer. Match complexity to project size.

---

### 4. Generate Project Structure
Show folder tree first, then create all files:

```
project-name/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── .env.example
├── src/
│   ├── __init__.py
│   ├── model.py
│   └── utils.py
└── data/
    └── sample.csv
```

Save all files to `/mnt/user-data/outputs/project-name/`.

---

### 5. Implement Core Code
Read `engines/code_generation.md` and `engines/code_safety.md`.

Order: entry point → core logic → utilities → helpers.

Rules:
- ASCII quotes only
- Inline comments on non-obvious lines
- Error handling (try/except, input validation)
- Env vars for secrets, never hardcoded
- If learning mode requested: add 🧠 blocks after each section

---

### 6. Generate README
Read `engines/documentation_engine.md` and `templates/repo_readme.md`.
Generate a full README.md and save it to the project folder.

---

### 7. Wrap Up
- Present all files with `present_files`
- Summarize in 3–5 bullets what was built
- Suggest next steps (deployment, features, improvements)
