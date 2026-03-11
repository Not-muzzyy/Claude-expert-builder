# Workflow: Learning Guidance

Use when the user wants to understand a concept, get a learning path, or asks "how does X work".

Also auto-suggest this workflow when:
- User seems confused (asks "why", "I don't get it", "what does this mean")
- User is new to a concept being used in the current task
- User makes a mistake that suggests a gap in understanding

When auto-suggesting, offer gently: "Want me to break down how this works?" — never force it.

---

## Step 1: Identify What They Need

- **Concept explanation** — "What is an API?", "How does RAG work?"
- **Learning path** — "How do I get into cybersecurity?", "What should I learn after Python?"
- **Code walkthrough** — "Explain what this code does line by line"
- **Resource recommendation** — "What should I use to learn ML?"

Read `knowledge/learning_paths.md` for structured paths.

---

## Step 2: Explain the Concept

Use this format for concept explanations:

**1. Simple definition** (1 sentence, no jargon)
**2. Real-world analogy** (makes it stick)
**3. How it works** (2–4 steps, plain English)
**4. Code example** (if applicable, with 🧠 annotation)
**5. Where to go deeper** (1–2 resources max)

Example:
> **What is a decorator in Python?**
> It's a function that wraps another function to add behavior without changing it.
> 🏠 Analogy: like a security guard at a building — the building (function) is the same,
> but the guard adds a check before you enter.

---

## Step 3: Suggest Next Steps

Based on what they're learning, suggest:
- What to build to practice it
- What concept to learn next
- Which certification covers it (read `knowledge/certifications.md`)
- Where to practice (TryHackMe, LeetCode, Kaggle, HuggingFace, etc.)

---

## Teaching Mode Format (for use in other workflows too)

When learning mode is active during a build/debug task, add after each code block:

```
🧠 What this does: [plain English explanation]
💡 Why this way: [design decision rationale]
🔗 Learn more: [concept name to Google / resource]
```

Keep it concise — 2–4 lines per block. Never interrupt flow.
