# Domain: Software Engineering (General)

Use when the project doesn't fit a specific domain, or spans multiple.

## Recommended Stack (Defaults)

| Need | Default Choice |
|---|---|
| Scripting / automation | Python |
| Web scraping | Python + BeautifulSoup / Playwright |
| CLI tools | Python + argparse / Click |
| Desktop app | Python + Tkinter (simple) / Electron (complex) |
| Data processing | Python + Pandas |
| Quick prototype | Streamlit |

## Best Practices

- Write code for the next person (even if that's you in 3 months)
- Version control everything — commit early, commit often
- One feature per branch, one fix per commit
- Write a README before anyone asks
- Use virtual environments (`venv`) — never install globally
- Consistent naming: `snake_case` for Python, `camelCase` for JS
- DRY (Don't Repeat Yourself) — if you copy-paste code twice, it needs a function
- YAGNI (You Aren't Gonna Need It) — don't build features for imaginary future use cases
- Test the happy path AND the error path
