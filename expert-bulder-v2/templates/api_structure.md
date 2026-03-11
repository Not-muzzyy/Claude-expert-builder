# Template: API Structure (Flask / FastAPI)

## Flask Layout

```
api-project/
├── app.py                  # App factory + route registration
├── requirements.txt
├── .env.example
├── .gitignore
├── README.md
├── config.py               # App config (dev/prod settings)
├── routes/
│   ├── __init__.py
│   ├── auth.py             # /auth/login, /auth/register
│   └── api.py              # /api/v1/...
├── models/
│   ├── __init__.py
│   └── user.py             # Database models
├── services/
│   ├── __init__.py
│   └── analyzer.py         # Business logic (keep out of routes)
└── tests/
    └── test_routes.py
```

## Flask Starter (app.py)

```python
from flask import Flask, jsonify, request
from config import Config
import os

app = Flask(__name__)
app.config.from_object(Config)

@app.route("/health")
def health():
    return jsonify({"status": "ok"})

@app.route("/api/v1/analyze", methods=["POST"])
def analyze():
    data = request.get_json()
    if not data or "text" not in data:
        return jsonify({"status": "error", "message": "Missing 'text' field"}), 400
    # process data here
    result = {"status": "ok", "data": {"result": "processed"}}
    return jsonify(result), 200

if __name__ == "__main__":
    app.run(debug=os.getenv("DEBUG", "false").lower() == "true")
```

## FastAPI Layout

```
api-project/
├── main.py                 # FastAPI app entry point
├── requirements.txt
├── .env.example
├── routers/
│   ├── auth.py
│   └── analyze.py
├── models/
│   └── schemas.py          # Pydantic request/response models
├── services/
│   └── core.py
└── tests/
    └── test_main.py
```

## FastAPI Starter (main.py)

```python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel
import os

app = FastAPI(title="My API", version="1.0.0")

class AnalyzeRequest(BaseModel):
    text: str

class AnalyzeResponse(BaseModel):
    status: str
    result: str

@app.get("/health")
def health():
    return {"status": "ok"}

@app.post("/api/v1/analyze", response_model=AnalyzeResponse)
def analyze(req: AnalyzeRequest):
    if not req.text.strip():
        raise HTTPException(status_code=400, detail="Text cannot be empty")
    return AnalyzeResponse(status="ok", result="processed")
```

## Standard Response Format

Always return consistent JSON:
```json
{
  "status": "ok",
  "data": {},
  "message": "optional message"
}
```

Error responses:
```json
{
  "status": "error",
  "message": "What went wrong (user-safe description)"
}
```
