# Workflow: README Generation

Use when the user wants a README for a project repo or their GitHub profile.

---

## Step 1: Identify Type

- **Repo README** — for a specific project (code, features, install steps)
- **Profile README** — for their GitHub profile page (about them, skills, projects)
- **GitHub Actions / CI README** — for workflow documentation (rare)

---

## Step 2: Gather Info

For **repo README**, collect:
- Project name and what it does
- Tech stack
- Install and run steps
- Live demo link (if any)
- Key features

For **profile README**, collect:
- Name, role/title
- Skills and tools
- Top 2–3 featured projects
- Current learning goals
- Certifications
- Social/contact links

Extract from conversation context first — don't ask for things already known.

---

## Step 3: Generate

Read the appropriate template:
- Repo → `templates/repo_readme.md`
- Profile → `templates/profile_readme.md`

Rules:
- Fill every section with real, specific content
- Never leave placeholder text like "[Your Name]" — ask if unknown
- Keep descriptions punchy and specific
- Badges must reflect the actual stack used
- Profile READMEs: personal and specific, not a generic template dump

---

## Step 4: Save & Present

Save as `README.md` to `/mnt/user-data/outputs/` and present with `present_files`.

Then ask:
- "Want to adjust tone or any section?"
- "Should I add a demo GIF placeholder or architecture diagram?"
