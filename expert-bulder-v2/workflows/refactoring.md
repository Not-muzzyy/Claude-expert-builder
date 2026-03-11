# Workflow: Refactoring

Use when the user wants to clean up, improve, or restructure existing code.

---

## Steps

### 1. Analyze the Code
Ask for the code if not already shared. Scan for:

**Structure issues:**
- Functions doing too many things (should be split)
- Repeated code blocks (should be extracted to helpers)
- Missing error handling
- Hardcoded values that should be constants or env vars

**Readability issues:**
- Unclear variable/function names
- Missing or outdated comments
- Inconsistent formatting or indentation

**Performance issues:**
- Unnecessary loops or repeated computations
- Loading data inside loops
- Missing caching where applicable

---

### 2. Prioritize Improvements
Group findings into:
- 🔴 **Critical** — bugs waiting to happen (hardcoded secrets, no error handling)
- 🟡 **Important** — hurts readability or maintainability
- 🟢 **Nice to have** — style, minor optimizations

Ask the user which priority to tackle first if list is long.

---

### 3. Produce Refactored Code
Read `engines/code_generation.md` and `engines/code_safety.md`.

Show before/after for each significant change:

```python
# ❌ Before — hardcoded API key
api_key = "sk-abc123"

# ✅ After — loaded from environment
import os
api_key = os.getenv("API_KEY")
```

Rules:
- Don't change behavior, only structure
- Keep the user's logic intact unless it's clearly broken
- ASCII quotes only
- Add comments explaining *why* a change was made, not just what

---

### 4. Summarize Changes
List what was changed and why in plain language:
- "Extracted URL validator into its own function — easier to test and reuse"
- "Moved API key to env var — never hardcode secrets"
- "Renamed `x` to `user_score` — self-documenting code"

---

### 5. Offer Next Steps
- Run it together to verify nothing broke
- Write basic tests for the refactored functions
- Deploy the cleaned version
