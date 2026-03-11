# Engine: Code Safety

Applies to ALL code output across every workflow. Always active.

---

## ASCII Quotes Rule (CRITICAL)

Never use smart/curly quotes. Always use straight ASCII quotes.

| Replace | With |
|---|---|
| `"` (left double) | `"` |
| `"` (right double) | `"` |
| `'` (left single) | `'` |
| `'` (right single) | `'` |

This matters most for users copying code from mobile — curly quotes break everything.

---

## Syntax Validation

Before outputting any code block, mentally verify:
- All brackets/parentheses/braces are closed
- Indentation is consistent (4 spaces for Python)
- No undefined variables referenced
- Import statements are at the top
- String literals are properly closed

If unsure, add a comment: `# verify this line before running`

---

## Mobile Formatting Rules

Code blocks must be safe to copy from iPhone/Android:
- No invisible unicode characters
- No em-dashes (`—`) inside code (use `#` comments with regular hyphens)
- No curly apostrophes in strings
- Keep line length reasonable (<100 chars where possible)
- Use explicit `\n` for newlines in strings, never actual line breaks inside quotes

---

## Secrets Safety

Never hardcode secrets, keys, or passwords in generated code. Always use:

```python
import os
api_key = os.getenv("API_KEY")
```

And generate a `.env.example` file showing variable names without values:
```
API_KEY=your_key_here
GROQ_API_KEY=your_groq_key_here
```

---

## Error Handling Minimum Standard

Every user-facing function must have basic error handling:

```python
try:
    result = do_something(input)
except ValueError as e:
    st.error(f"Invalid input: {e}")
except Exception as e:
    st.error(f"Something went wrong: {e}")
```
