# Blog Builder

A browser-based blog content creation tool built as a single-file HTML application.

---

## Project Overview

Blog Builder is a standalone `index.html` application that provides a rich editing interface for creating, structuring, and formatting blog content. No build step required — open in any browser and it works.

**Repository:** `kuberandigit-coder/blog-builder`  
**Daily Log Repo:** `kuberandigit-coder/aios-kuberan`  
**Stack:** HTML · CSS · JavaScript · Git · GitHub · Claude Code

---

## Setup Instructions

### Prerequisites

- [Git](https://git-scm.com/) installed
- [Git Bash](https://gitforwindows.org/) (Windows)
- [Claude Code](https://claude.ai/code) CLI installed
- A GitHub account

### Clone the Repository

```bash
git clone https://github.com/kuberandigit-coder/blog-builder.git
cd blog-builder
```

### Add the Daily Log Remote

```bash
git remote add aios https://github.com/kuberandigit-coder/aios-kuberan.git
```

### Verify Remotes

```bash
git remote -v
# origin  https://github.com/kuberandigit-coder/blog-builder.git
# aios    https://github.com/kuberandigit-coder/aios-kuberan.git
```

---

## Development Workflow

1. Open `index.html` in a browser to test changes
2. Edit using your preferred code editor or Claude Code
3. Commit changes with a descriptive message (see [GIT_CONVENTIONS.md](GIT_CONVENTIONS.md))
4. Push to `origin` (blog-builder) for code changes
5. At end of day, tell Claude Code: **"push everything done today"** to log to `aios-kuberan`

See [DEVELOPMENT_WORKFLOW.md](DEVELOPMENT_WORKFLOW.md) for the full daily process.

---

## Claude Code Workflow

Claude Code reads task prompts and context you provide directly in the chat.

**How to structure a task prompt:**

```
CONTEXT
[Describe the project, stack, and current state]

TASK
[Describe what you need Claude to do]

REQUIREMENTS
[List constraints, rules, what must/must not happen]

DELIVERABLES
[List the exact files or outputs expected]
```

Claude Code will:
- Audit existing files before making changes
- Create or edit only what the task requires
- Follow Git conventions
- Never push without your explicit instruction

---

## Git Workflow

| Branch | Purpose |
|--------|---------|
| `master` | Stable production code |
| `dev` | Active development (recommended to create) |
| `feature/name` | Isolated feature work |

```bash
# Start a new feature
git checkout -b feature/your-feature-name

# Commit work
git add index.html
git commit -m "feat: describe what changed"

# Merge back to master when done
git checkout master
git merge feature/your-feature-name
```

---

## Contribution Guidelines

- One logical change per commit
- Use the commit message format in [GIT_CONVENTIONS.md](GIT_CONVENTIONS.md)
- Never commit secrets, tokens, or API keys
- Test in browser before committing
- All changes should be reversible
