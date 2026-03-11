# Engine: Debugging Engine

Core logic for analyzing errors and generating fixes.

---

## Error Type Reference

| Error | Common Cause | First Thing to Check |
|---|---|---|
| `SyntaxError` | Typo, missing colon, bad indent | Line number in traceback |
| `IndentationError` | Mixed tabs/spaces | Use spaces only (4 per level) |
| `NameError` | Variable used before defined | Check spelling and scope |
| `TypeError` | Wrong type passed to function | Check what the function expects |
| `AttributeError` | Called method on None or wrong type | Print the variable before using it |
| `KeyError` | Dict key doesn't exist | Use `.get(key)` or check `if key in dict` |
| `IndexError` | List index out of range | Check list length before accessing |
| `ImportError` | Package not installed or wrong name | `pip install package-name` |
| `FileNotFoundError` | Path is wrong or file doesn't exist | Print the full path being used |
| `ValueError` | Right type, wrong value | Validate input before passing |
| `ConnectionError` | API/network issue | Check internet, API key, endpoint URL |
| `JSONDecodeError` | Response wasn't valid JSON | Print raw response first |

---

## Traceback Reading Guide

Read from the bottom up:
1. **Last line** = error type and message (most important)
2. **Line above** = exact file and line number where it crashed
3. **Stack above that** = call chain that led there

---

## Fix Verification Checklist

Before presenting a fix, verify:
- [ ] The fix actually addresses the root cause (not just silencing the error)
- [ ] No new bugs introduced
- [ ] ASCII quotes used
- [ ] Error handling added if input could be invalid
- [ ] Fix doesn't break other parts of the code
