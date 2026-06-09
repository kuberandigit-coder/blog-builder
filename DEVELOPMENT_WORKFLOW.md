# Development Workflow

## Daily Development Process

### Morning: Start of Day

```bash
# 1. Pull latest changes from GitHub
git checkout master
git pull origin master

# 2. Check status
git status

# 3. Create or switch to a working branch (recommended)
git checkout -b feature/todays-task-name
# OR continue on master for small single-file edits
```

### During the Day: Making Changes

```bash
# After editing index.html (or any file)
# 1. Check what changed
git diff

# 2. Stage changes
git add index.html

# 3. Commit with a clear message
git commit -m "feat: add image block insertion to blog editor"
```

### End of Day: Push and Log

```bash
# Push code changes to blog-builder repo
git push origin master

# Then tell Claude Code:
# "push everything done today"
# → Claude will create 2026-06-09.md and push to aios-kuberan
```

---

## Requirements Gathering Process

When starting a new feature or task:

1. Write a prompt for Claude Code using this structure:

```
CONTEXT     — What project, what stack, what already exists
TASK        — What needs to be done
REQUIREMENTS — Constraints, what must/must not happen
DELIVERABLES — Exact files or outputs expected
```

2. Save complex requirements as a `requirements.md` file if the task spans multiple sessions.

3. Reference the requirements file at the start of each Claude Code session:
   > "Here are my requirements: [paste or attach requirements.md]"

---

## Claude Code Usage Process

| Step | Action |
|------|--------|
| 1 | Open Claude Code (CLI or IDE extension) |
| 2 | Provide CONTEXT + TASK prompt |
| 3 | Review Claude's plan before it executes |
| 4 | Approve file writes/edits one by one |
| 5 | Test changes in browser |
| 6 | Commit and push after validation |

**Rules for Claude Code sessions:**
- Never allow Claude to push to GitHub without your explicit instruction
- Always review diffs before committing
- Use "push everything done today" only at end of day
- Claude Code does not store session state — re-provide context each time

---

## Testing and Validation Process

Since this project is a single HTML file, testing is manual:

```
1. Open index.html in Chrome/Firefox/Edge
2. Test the specific feature or change you made
3. Test existing features to check for regressions
4. Check browser console for errors (F12 → Console)
5. Confirm layout on different window sizes
6. Only commit after passing all checks
```

**Pre-commit checklist:**
- [ ] Feature works as expected in browser
- [ ] No console errors
- [ ] No credentials or secrets in code
- [ ] `git diff` reviewed — no unintended changes

---

## Git Commit and Push Process

```bash
# Stage only the files you changed
git add index.html

# Write a commit message (see GIT_CONVENTIONS.md for format)
git commit -m "fix: correct heading alignment in preview mode"

# Push to GitHub
git push origin master
```

> **IMPORTANT:** Never use `git push --force` unless you know exactly why.  
> Never commit `.env`, tokens, or passwords.

---

## Folder Structure

```
blog-builder/
├── index.html              ← Main application (entire app lives here)
├── README.md               ← Project overview and setup
├── .gitignore              ← Files excluded from Git tracking
├── DEVELOPMENT_WORKFLOW.md ← This file
├── GIT_CONVENTIONS.md      ← Branch and commit standards
└── REPOSITORY_AUDIT.md     ← Audit findings and recommendations
```
