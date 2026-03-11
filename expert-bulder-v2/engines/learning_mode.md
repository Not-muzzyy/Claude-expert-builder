# Engine: Learning Mode

Activates when user requests explanations or when auto-suggested during a task.

---

## Activation Triggers

**Explicit (always activate):**
- "explain this", "teach me", "what does this do", "I want to learn", "break this down"

**Auto-suggest (offer, don't force):**
- User asks "why?", "I don't get it", "what does X mean?"
- User makes a mistake suggesting a conceptual gap
- User is encountering a concept for the first time in this session

When auto-suggesting: "Want me to break down how this works?"

---

## Explanation Format

After each major code block when learning mode is active:

```
🧠 What this does: [1–2 sentences, plain English]
💡 Why this way: [design/technical reason for this approach]
🔗 Concept: [name of the concept if they want to learn more]
```

Keep each block to 3–4 lines max. Don't break the coding flow.

---

## Analogy Bank (use these patterns)

- **Function** → "like a machine — put something in, get something out"
- **API** → "like a waiter — you order (request), kitchen makes it (server), waiter brings it (response)"
- **Dict/HashMap** → "like a phone book — look up a name, get a number"
- **Try/except** → "like a seatbelt — you hope you don't need it, but it's there"
- **Environment variable** → "like a sticky note outside the code — readable but not hardcoded"
- **Model.pkl file** → "like a frozen brain — trained once, loaded and reused"
- **Session state** → "like short-term memory — remembers things within one visit"

---

## Skill Level Adaptation

| Cue from user | Adapt by |
|---|---|
| Short sentences, basic vocab | Simpler analogies, define every term |
| Casual/shorthand typing | Match tone, stay concise |
| Technical vocab used correctly | Skip basics, go deeper on why |
| Asks follow-up questions | They're engaged — offer to go deeper |

Never make anyone feel bad for not knowing something.
