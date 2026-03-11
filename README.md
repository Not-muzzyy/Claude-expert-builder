# Claude Expert Builder Skill

> A production-grade Claude skill that transforms ideas into working software — with clean code, solid architecture, and mentor-level guidance.

![Claude](https://img.shields.io/badge/Claude-Skill-8B0000?style=flat-square&logo=anthropic&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

---

## What This Is

**Expert Builder** is a Claude skill — a structured system prompt + knowledge base that turns Claude into a senior software engineer and mentor. Drop it into any Claude-compatible environment and it instantly upgrades Claude's ability to plan, build, debug, document, and deploy real software.

Built for developers who want production-ready output, not just working code.

---

## What It Can Do

| Task | How to Trigger |
|---|---|
| Build a project from scratch | "Build me X", "I have an idea for an app" |
| Rapid MVP / prototype | "Quick demo", "MVP", "prototype fast" |
| Debug broken code | "Error", "not working", "broken" |
| Refactor and clean up code | "Clean this up", "refactor", "improve my code" |
| Design system architecture | "Design my system", "how should I structure this" |
| Deploy to cloud | "Deploy", "host", "Streamlit Cloud", "Docker" |
| Generate READMEs | "Write a README", "GitHub docs" |
| Learning guidance | "Explain", "teach me", "how does X work" |

---

## Skill Structure

```
Claude-expert-builder/
├── SKILL.md                  # Core skill definition (entry point)
├── workflows/
│   ├── build_from_scratch.md
│   ├── rapid_prototype.md
│   ├── debugging.md
│   ├── refactoring.md
│   ├── architecture_design.md
│   ├── deployment.md
│   ├── readme_generation.md
│   └── learning_guidance.md
├── domains/
│   ├── ai_ml.md
│   ├── cybersecurity.md
│   ├── web_development.md
│   ├── backend_development.md
│   ├── data_science.md
│   └── devops.md
├── engines/
│   ├── idea_engine.md
│   ├── architecture_engine.md
│   ├── code_generation.md
│   ├── code_safety.md
│   ├── debugging_engine.md
│   ├── documentation_engine.md
│   └── learning_mode.md
├── templates/
│   ├── repo_readme.md
│   └── profile_readme.md
└── knowledge/
    ├── certifications.md
    ├── learning_paths.md
    ├── developer_best_practices.md
    └── open_source_projects.md
```

---

## How to Use

### In Claude.ai (Projects)
1. Open a Claude Project
2. Paste `SKILL.md` content into the **Project Instructions** field
3. Claude will now behave as Expert Builder in every conversation in that project

### With Claude API
```python
import anthropic

with open("SKILL.md", "r") as f:
    skill_prompt = f.read()

client = anthropic.Anthropic()
response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=4096,
    system=skill_prompt,
    messages=[
        {"role": "user", "content": "Build me a Streamlit app that detects phishing URLs using ML"}
    ]
)
print(response.content[0].text)
```

### With Claude Code
```bash
# Add as a system prompt file
claude --system-prompt SKILL.md "Build me a REST API for user authentication"
```

---

## Design Principles

- **Copy-paste safe code** — ASCII-only quotes, mobile-safe output
- **Explain on request** — teaching mode activates when you ask; silent by default
- **Domain-aware** — different stacks, best practices, and patterns per domain
- **Real deliverables** — always produces downloadable files, not just chat text
- **Meets you where you are** — reads your skill level and adapts accordingly

---

## Example Output

**Input:** `"Build me a phishing detector using ML and Streamlit"`

**Expert Builder delivers:**
- Complete project file tree
- `app.py` with Streamlit UI + session state handling
- `model.py` with scikit-learn pipeline (TF-IDF + Logistic Regression)
- `requirements.txt`
- Deployment instructions for Streamlit Cloud
- README for the generated project

---

## Built By

**Muzzammil C** — BCA Final Year | Cybersecurity & ML  
[LinkedIn](https://linkedin.com/in/muzzammilc7) · [GitHub](https://github.com/Not-muzzyy)

---

## License

MIT License — use it, fork it, improve it.
