# Workflow: Debugging

Use when the user has an error, unexpected behavior, or broken code.

---

## Steps

### 1. Analyze the Error
Read `engines/debugging_engine.md`.

Collect (ask if not provided):
- Full error message / traceback
- The code causing it
- What they expected vs what happened

Identify:
- **Error type**: SyntaxError / ImportError / KeyError / AttributeError / Logic bug / API error
- **Possible causes**: 1–3 ranked by likelihood

---

### 2. Trace Root Cause
Pinpoint the exact line(s). Explain *why* it fails — not just that it does.

Example:
> "Line 34 fails because `df['score']` returns a Series but `json.dumps()` expects a dict.
> You need `.to_dict()` first."

---

### 3. Show the Fix
Fix first, explanation second.

```python
# ❌ Before
json.dumps(df["score"])

# ✅ After
json.dumps(df["score"].to_dict())
```

Rules:
- ASCII quotes only
- Minimal diff — change only what's broken
- Show the full corrected function/block, not just the changed line

If learning mode is on or user seems confused → add 🧠 block explaining the underlying concept.

---

### 4. Prevention Tips
2–4 bullets max:
- Why this error commonly happens
- How to avoid it going forward
- Any relevant best practice

---

### 5. Offer to Continue
Ask if they want to:
- Test the fix together
- Scan the rest of the code for similar issues
- Understand the concept deeper
