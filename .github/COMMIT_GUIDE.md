# 🧾 ZenAI Commit Guide

This guide helps you write clear, consistent, and structured commit messages — especially if you're using **GitHub Desktop** or any tool that doesn’t support `.gitmessage` templates.

We follow the **Conventional Commits** standard:

```
<type>(<scope>): <short, clear summary>
```

---

## 🧠 Commit Types

| Type       | Purpose                                |
|------------|----------------------------------------|
| `feat`     | New feature                            |
| `fix`      | Bug fix                                |
| `docs`     | Documentation changes only             |
| `style`    | Code formatting (no behavior change)   |
| `refactor` | Code refactor (no new features/fixes)  |
| `test`     | Adding or updating tests               |
| `chore`    | Setup, scaffolding, or config changes  |
| `ci`       | Continuous integration workflows       |

---

## 🔎 Scope Examples

Use lowercase, short, and relevant words to describe the area you're touching:

- `prompt_framework`
- `projectplan`
- `validation`
- `milestone_0`
- `cursor_rules`
- `readme`
- `security`
- `repo`
- `checklist`
- `init`

---

## 🧪 Commit Examples

```bash
feat(projectplan): add initial milestone structure with checklist
fix(validation): prevent task completion without checklist pass
docs(readme): add GitHub usage overview and folder tree
chore(init): scaffold ZenAI rituals folder and rules
refactor(cursor_rules): simplify feedback loop enforcement
```

---

## ✍️ Commit Template (Manual Copy for GitHub Desktop)

```plaintext
<type>(<scope>): <commit summary>

# Optional body (wrap at 72 chars):
# - Why was this change made?
# - What trade-offs or structure decisions were involved?
# - What files, behaviors, or systems are affected?
```

> _“Think before you commit. Structure reflects clarity.”_ – Zen