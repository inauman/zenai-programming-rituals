# Validation Checklist – ZenAI Milestone Completion Gate

Before marking a task or milestone as complete, this checklist ensures the work has been validated, committed, and reviewed with discipline and quality.

---

## 🎯 Purpose

- Enforce quality control before task/milestone closure
- Ensure consistent commit and delivery hygiene
- Act as a ritualized pause for reflection and feedback

---

## ✅ When to Use

- After completing any milestone or numbered task in [projectplan.md](projectplan.md)
- Before pushing a commit
- During code review or pre-deploy QA

---

## 📋 Completion Criteria

Check all that apply before marking a task complete in [projectplan.md](projectplan.md).

### 🔧 Implementation

- [ ] Code compiles/builds without errors
- [ ] Linting passes (e.g., ESLint, Clippy)
- [ ] Tests pass (unit/integration/E2E as applicable)
- [ ] Sensitive logic reviewed for security implications

### 🧠 Cognitive Validation

- [ ] Code or artifact aligns with the agreed design/contract
- [ ] Implementation choices are explained in comments or commit message
- [ ] Threat mitigation notes are documented (if applicable)

### 🗂️ Hygiene & Commit

- [ ] `git status` is clean (no untracked or leftover files)
- [ ] Commit created with conventional format:
  - Example: `feat(crypto): add age encryption interface`
- [ ] Commit is atomic, focused, and meaningful
- [ ] Cursor task marked complete in [projectplan.md](projectplan.md)

### 📣 Communication & Feedback

- [ ] Zen has asked: _“Is there anything I missed?”_
- [ ] Feedback (if any) captured in [README-for-Nauman.md](README-for-Nauman.md) or [.cursorrules](.cursorrules)
- [ ] Linked documents updated (e.g., architecture.md, diagrams, READMEs)

---

## 🧘 Ritual Tip

> If you're rushing to check off a task, stop and reflect:  
> _“Would I trust this output if it held my secrets?”_

---

## 🧩 Linked Ritual Artifacts

Refer to:
- [.cursorrules](.cursorrules)
- [projectplan.md](projectplan.md)
- [security_principles.md](security_principles.md)

These files form the behavioral contract and implementation planning base for all future milestones.

---

Use this checklist not as a blocker, but as a safeguard for quality, safety, and alignment.
