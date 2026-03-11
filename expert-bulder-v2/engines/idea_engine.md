# Engine: Idea Engine

Use when converting a vague user idea into a concrete project plan.

---

## Steps

### 1. Interpret the Idea
Extract from what the user said:
- Core problem being solved
- Target user (who uses this?)
- Main input → output

If the idea is vague, ask ONE focused question to clarify the most ambiguous part.
Don't fire multiple questions at once.

---

### 2. Identify the Problem
Restate the problem clearly in 1–2 sentences. Confirm with the user if needed.

Example:
> "So you want a tool that takes a resume PDF and tells you how well it matches a job
> description — scoring it like an ATS system would. Right?"

---

### 3. Determine Domain
Map the idea to one of the skill's supported domains:
- AI / ML, Cybersecurity, Web, Backend, Data Science, DevOps, Mobile, General

Read the matching `domains/` file for stack and best practice context.

---

### 4. Propose Solution
Describe the solution approach in plain language:
- What the app does step by step
- Core technical approach (ML model? API call? rule-based?)
- Estimated complexity: Simple / Medium / Complex

---

### 5. Recommend Stack
Give a short, justified stack recommendation:

```
UI:         Streamlit        — fast, Python-native, free to deploy
Model:      Groq (LLaMA 3)  — fast inference, free tier
Data:       Pandas           — standard for structured data
Deploy:     Streamlit Cloud  — 1-click, free
```

Match to the user's known skill level. Don't recommend Docker for a beginner.
