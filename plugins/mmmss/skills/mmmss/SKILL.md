---
name: mmmss
description: Use when about to change code, content, config or infrastructure in a git repo - features, refactors, restructures, migrations, renames, multi-part requests, or anything the user calls "quick" or wants "in one go".
---

# Many More Much Smaller Steps

Walk a path of small steps, each from **ready** to **ready**. Edits with the check broken in between are one big step, however small each edit is. The user has authorised one local commit per step (current branch, no push).

1. **Define ready:** the check command (tests/build/lint) must pass and nothing user-visible gets worse. Run it first.
2. **List the steps** before editing. Each is ~15 min (max 1 h), one commit subject without "and", ends ready. No-value preparatory steps are fine.
3. **Per step:** edit → check → green: stage only this step's files, commit → adjust remaining steps.
4. **Red and not quickly fixed:** restore to the last commit, split smaller.
5. **Restructures:** add new beside old → move callers/data over → delete old last. Refactor and behaviour change in separate steps.

| Thought | Reality |
|---|---|
| "Create all files, then test" | One big step. Add one, stay green, commit. |
| "User said 'in one go'" | That's the destination, not the stride. |
| "Too small for steps" | Then it's one step — still check and commit. |

Never commit the user's pre-existing changes. Don't squash unless asked; offer at the end.
