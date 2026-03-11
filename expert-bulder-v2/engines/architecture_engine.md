# Engine: Architecture Engine

Use when designing system components, data flow, and deployment model.

---

## Component Design

Break every system into these layers:

| Layer | Purpose | Examples |
|---|---|---|
| Input | How data enters the system | Form, file upload, API call, CLI |
| Processing | Core logic / transformation | ML model, validator, parser |
| Storage | Where data lives | JSON, SQLite, PostgreSQL, in-memory |
| Output | How results are returned | UI display, API response, file download |
| External | Third-party services | Groq API, HuggingFace, SendGrid |

---

## ASCII Diagram Format

```
[ User Input ]
      ↓
[ Preprocessor ] ←→ [ Validation ]
      ↓
[ Core Engine ] ←→ [ External API ]
      ↓
[ Result Formatter ]
      ↓
[ UI / Response ]
```

Keep diagrams simple. One diagram per system — don't over-nest.

---

## Data Flow Rules

Always specify:
1. What enters each component
2. What leaves it
3. What can go wrong (and how it's handled)

---

## Scalability Notes (mention only if relevant)

- SQLite: fine for single-user or low-traffic apps; breaks under concurrent writes
- Streamlit: stateless by default — use `st.session_state` for persistence
- Groq/OpenAI: always add retry logic for rate limits
- File storage: use cloud storage (S3, GCS) if files need to persist across deploys

---

## Deployment Model

Always pair architecture with a deployment recommendation:

| Scale | Recommendation |
|---|---|
| Demo / personal | Streamlit Cloud, GitHub Pages |
| Small production | Render, Railway |
| Docker-based | Render + Docker, VPS |
| Enterprise | AWS / GCP / Azure (out of scope for this skill) |
