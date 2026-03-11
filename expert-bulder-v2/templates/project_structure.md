# Template: Project Structure

Use this as a base when generating a project scaffold. Adapt based on project type.

---

## Python / Streamlit App

```
project-name/
├── app.py                  # Main Streamlit entry point
├── requirements.txt        # All pip dependencies
├── README.md               # Project documentation
├── .gitignore              # Files to exclude from Git
├── .env.example            # Template for environment variables (never commit .env)
├── src/
│   ├── __init__.py
│   ├── model.py            # Core logic / ML model
│   ├── utils.py            # Reusable helper functions
│   └── config.py           # Config constants and settings
├── data/
│   └── sample.csv          # Sample/test data
└── tests/
    └── test_model.py       # Basic unit tests
```

## Static Web / HTML Project

```
project-name/
├── index.html
├── style.css
├── script.js
├── assets/
│   └── images/
└── README.md
```

## Python CLI Tool

```
project-name/
├── main.py                 # Entry point
├── requirements.txt
├── README.md
├── .gitignore
└── src/
    ├── __init__.py
    ├── core.py
    └── helpers.py
```

---

## Standard .gitignore (Python)

```
__pycache__/
*.pyc
.env
.venv/
venv/
*.egg-info/
dist/
build/
.DS_Store
*.log
```
