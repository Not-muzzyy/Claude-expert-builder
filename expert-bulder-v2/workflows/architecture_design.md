# Workflow: Architecture Design

Use when the user wants to plan how their system should be structured before writing code.

---

## Steps

### 1. Understand the System
Read `engines/architecture_engine.md`.

Collect:
- What does this system do at a high level?
- Who are the users? How many (rough estimate)?
- What data goes in, what comes out?
- Any specific constraints? (must be free tier, must use Python, offline, etc.)

---

### 2. Define Components
Break the system into logical parts. For each component, state:
- What it does
- What it receives as input
- What it outputs
- What it depends on

Example:
```
[ User ] → [ Streamlit UI ] → [ Preprocessor ] → [ ML Model ] → [ Result Display ]
                                     ↓
                              [ Groq API / LLM ]
```

---

### 3. Define Data Flow
Show how data moves through the system step by step:

1. User uploads/inputs data
2. Preprocessor validates and cleans it
3. Core engine processes it
4. Result is formatted and returned
5. UI displays result + optional export

---

### 4. Recommend Stack Per Layer

Based on detected domain (read `domains/` file), recommend:

| Layer | Recommendation | Why |
|---|---|---|
| UI | Streamlit / React / HTML | [reason] |
| Backend | Python / Flask / FastAPI | [reason] |
| ML/AI | Scikit-learn / Groq / HuggingFace | [reason] |
| Storage | JSON / SQLite / PostgreSQL | [reason] |
| Deployment | Streamlit Cloud / Render / Docker | [reason] |

Match recommendations to the user's skill level and constraints.

---

### 5. Identify Risks Early
Flag anything that could be a problem:
- "If you use SQLite, it won't work well with concurrent users on Streamlit Cloud"
- "Groq API has rate limits — add a retry handler"
- "Storing user data? You'll need a privacy notice"

---

### 6. Produce Deliverable
Generate an architecture document saved to `/mnt/user-data/outputs/architecture.md` with:
- System overview
- Component breakdown
- Data flow diagram (ASCII)
- Stack recommendations
- Risks and mitigations

Ask if they want to move into building after this.
