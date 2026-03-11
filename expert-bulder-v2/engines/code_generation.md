# Engine: Code Generation

Rules and patterns for writing all code output across workflows.

---

## Language Detection

Auto-detect from context:
- User mentions Python, Streamlit, Flask → Python
- User mentions React, Node, Express → JavaScript
- User mentions "script" with no context → Python (default)
- User mentions HTML/CSS only → HTML

Confirm if ambiguous.

---

## Code Quality Rules

Always follow these regardless of language:

- **Self-documenting names** — `user_score` not `x`, `load_model()` not `lm()`
- **Single responsibility** — each function does one thing
- **No magic numbers** — `MAX_RETRIES = 3` not just `3`
- **Constants at top** — define configs and limits before functions
- **Imports at top** — never inside functions unless lazy loading is intentional

---

## Python-Specific Patterns

```python
# Constants
MAX_RETRIES = 3
DEFAULT_MODEL = "llama-3.1-8b-instant"

# Type hints where helpful
def analyze_url(url: str) -> dict:
    ...

# f-strings over .format() or %
message = f"Processing {filename}..."

# Context managers for files
with open("file.txt", "r") as f:
    content = f.read()
```

---

## Streamlit-Specific Patterns

```python
# Session state for persistence
if "history" not in st.session_state:
    st.session_state.history = []

# Secrets (never os.environ in Streamlit Cloud)
api_key = st.secrets["GROQ_API_KEY"]

# Show progress for long operations
with st.spinner("Analyzing..."):
    result = run_analysis(input_data)
```

---

## Output Order

For any new file, always write in this order:
1. Imports (stdlib → third-party → local)
2. Constants / config
3. Helper functions
4. Core logic functions
5. UI / main function
6. Entry point (`if __name__ == "__main__":`)
