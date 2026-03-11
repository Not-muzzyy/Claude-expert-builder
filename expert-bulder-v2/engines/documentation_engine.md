# Engine: Documentation Engine

Rules for generating READMEs, docstrings, and architecture docs.

---

## README Quality Rules

- **No placeholder text** — never leave "[Your Name]" or "[Description here]"
- **Specific over generic** — "97% accuracy phishing detector" not "an AI tool"
- **Badges match reality** — only use badges for tech actually in the stack
- **Demo link always included** — if deployed, link it prominently
- **Install steps must be copy-paste ready** — test them mentally

---

## Docstring Format (Python)

For any non-trivial function:

```python
def analyze_url(url: str) -> dict:
    """
    Analyzes a URL for phishing indicators using LLaMA 3.1.

    Args:
        url: The URL string to analyze.

    Returns:
        dict with keys: 'verdict' (str), 'confidence' (float), 'reasons' (list)

    Raises:
        ValueError: If url is empty or not a valid URL format.
    """
```

---

## Architecture Doc Format

When generating architecture docs, always include:
1. **System Overview** — what it does in 2–3 sentences
2. **Component Breakdown** — each part with its purpose
3. **Data Flow** — ASCII diagram
4. **Stack Justification** — why each tech was chosen
5. **Known Limitations** — honest about what it doesn't handle yet

---

## Inline Comment Rules

- Comment the *why*, not the *what*
- Skip obvious comments: `# increment i` on `i += 1` is noise
- Do comment non-obvious logic: `# SHA256 gives consistent short codes for same URL`
- Mark TODOs clearly: `# TODO: replace hardcoded data with DB call`
