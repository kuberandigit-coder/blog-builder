# Git Conventions

## Branch Naming Rules

| Type | Pattern | Example |
|------|---------|---------|
| Feature | `feature/short-description` | `feature/add-image-block` |
| Bug fix | `fix/short-description` | `fix/heading-alignment` |
| Documentation | `docs/short-description` | `docs/update-readme` |
| Experiment | `experiment/short-description` | `experiment/new-toolbar` |

**Rules:**
- Use lowercase and hyphens only (no spaces, no underscores)
- Keep names short but descriptive
- Delete feature branches after merging
- Never commit directly to `master` for significant changes — use a branch

---

## Commit Message Standards

### Format

```
<type>: <short description>

[optional body — explain WHY, not WHAT]
```

### Types

| Type | When to use |
|------|------------|
| `feat` | New feature or functionality |
| `fix` | Bug fix |
| `docs` | Documentation only changes |
| `style` | Formatting, spacing (no logic change) |
| `refactor` | Code restructuring (no feature or fix) |
| `test` | Adding or updating tests |
| `chore` | Build config, tooling, .gitignore |

### Examples

```bash
# Good
git commit -m "feat: add drag-and-drop block reordering"
git commit -m "fix: resolve insert menu closing on outside click"
git commit -m "docs: add Claude Code usage section to README"
git commit -m "style: normalize font sizes across editor blocks"
git commit -m "chore: update .gitignore to exclude .DS_Store"

# Bad (avoid)
git commit -m "Update"
git commit -m "fixed stuff"
git commit -m "changes"
git commit -m "WIP"
```

**Rules:**
- Subject line: max 72 characters
- Use present tense: "add" not "added", "fix" not "fixed"
- No period at the end of the subject line
- Leave a blank line between subject and body (if body is used)

---

## Branch Strategy

```
master  ─────────────────────────────────────────► (stable, deployable)
           │                       │
           └── feature/xyz ───────►│ (merge when complete)
                                   │
           └── fix/abc ────────────►│ (merge when tested)
```

### Recommended Flow

```bash
# 1. Start from master
git checkout master
git pull origin master

# 2. Create a branch
git checkout -b feature/my-new-feature

# 3. Make commits on the branch
git add .
git commit -m "feat: initial implementation"

# 4. When done, merge back
git checkout master
git merge feature/my-new-feature

# 5. Push master
git push origin master

# 6. Delete the feature branch (optional cleanup)
git branch -d feature/my-new-feature
```

---

## Pull Request Guidelines

Since this is currently a solo project, PRs are optional. But if collaborating:

- Title should match commit format: `feat: add image support`
- Include a short description of what changed and why
- Link to any relevant issues
- Request at least one review before merging
- Squash commits when merging to keep history clean

---

## Remotes Reference

| Remote | URL | Purpose |
|--------|-----|---------|
| `origin` | `https://github.com/kuberandigit-coder/blog-builder.git` | Main code repository |
| `aios` | `https://github.com/kuberandigit-coder/aios-kuberan.git` | Daily development log |
