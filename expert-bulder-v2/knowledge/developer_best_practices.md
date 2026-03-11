# Knowledge: Developer Best Practices

## Git & Version Control

- Commit often, push regularly — don't lose work
- Write meaningful commit messages: `fix: handle empty URL input` not `update`
- One feature per branch: `feature/phishing-detector`, `fix/session-state-bug`
- Never commit `.env` files — add to `.gitignore` immediately
- Tag releases: `git tag v1.0.0` before major deploys
- Use `git stash` to save work-in-progress before switching branches

## Code Quality

- Run your code before calling it done
- Read your own code like a stranger would — would they understand it?
- Functions should be short enough to fit on one screen
- If you need to scroll to understand a function, split it
- Dead code = delete it. Version control has the history

## Project Structure

- Every project needs: `README.md`, `requirements.txt`, `.gitignore`, `.env.example`
- Keep secrets in `.env`, never in code
- `src/` for source code, `tests/` for tests, `data/` for data files
- Name files what they do: `phishing_detector.py` not `model2_final_v3.py`

## Professional GitHub Habits

- Pin your top 4–6 projects on your profile
- Every repo needs a README with: what it does, how to run it, demo link
- Use topics/tags on repos (e.g. `python`, `streamlit`, `cybersecurity`) — helps with discovery
- Stars and forks matter — build things people find useful
- Commit regularly — green contribution graph matters to recruiters

## Deployment Checklist

Before going live:
- [ ] No hardcoded secrets in code
- [ ] `requirements.txt` is up to date (`pip freeze > requirements.txt`)
- [ ] README has accurate install steps
- [ ] App handles empty/bad input gracefully
- [ ] Tested on a clean environment (not just your own machine)
- [ ] `.env.example` shows all required env variables

## Code Review Mindset (even solo)

Before submitting / pushing, ask:
- Does this actually work? (run it)
- Is it readable? (would a junior dev understand it?)
- Is it secure? (no hardcoded creds, no exposed endpoints)
- Is it efficient? (no obvious bottlenecks)
- Is it tested? (at least one happy path test)
