# ZenAI Project Plan

This is a living milestone & task tracker used throughout the project lifecycle.  
It supports **design-first planning**, **validation-driven task tracking**, and **retrospective learning**.

---

## 🧠 Guidelines

- Use this file to define **milestones** and **numbered tasks**.
- Each task must include:
  - Status (`[ ]` = incomplete, `[x]` = complete)
  - Clear description
  - Optional links to implementation files or specs
- Tasks are only marked complete after:
  - Validation (lint/tests pass, behavior confirmed)
  - Commit is made with conventional message
  - Status updated here
- This file can be `.md` or `.mdc` depending on context (Cursor can choose intelligently).

---

## 🗂️ Example Milestone Template

### Milestone 1 – Core Feature X

| #    | Task Description                          | Status | Owner    | Notes                        |
|------|-------------------------------------------|--------|----------|------------------------------|
| 1.1  | Define module layout & interfaces         | [x]    | Zen      | Done in milestone_0          |
| 1.2  | Implement encryption module               | [ ]    | Zen      | Awaiting interface sign-off |
| 1.3  | Write integration tests                   | [ ]    | Zen      | Depends on 1.2               |
| 1.4  | Validate outputs & update docs            | [ ]    | Nauman   |                              |
| 1.5  | Finalize commit + update checklist        | [ ]    | Zen      |                              |

---

## ✅ Task Completion Criteria

Each task must meet the following before being marked complete:

- [ ] Feature/code validated
- [ ] Git status clean
- [ ] Commit created (`type(scope): description`)
- [ ] [validation_checklist.md](zenai/validation_checklist.md) run
- [ ] Feedback loop completed (if applicable)

---

## 🔄 Feedback Loop Points

- End of each milestone:
  - Zen asks: _“Is there anything I missed?”_
  - Nauman adds feedback here or in retro files
- Mid-milestone reviews optional, encouraged for long phases

---

## 🔗 Related Files

- [milestone_0_sprint_planning.md](zenai/milestone_0_sprint_planning.md)
- [validation_checklist.md](zenai/validation_checklist.md)
- [.cursorrules](zenai/.cursorrules)

---

> _“Plan clearly. Validate thoroughly. Commit mindfully.”_ – ZenAI Philosophy
