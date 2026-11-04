---
id: MOD-{module-slug} # file name: <vault>/07-Modules/MOD-{module-slug}.md
title: "{Module name}"
owner: "{role or person who answers for the module}"
repository: "{repo-identifier}" # repository subdirectory or '.' for single-repo
entry_points: # project-relative files or globs; scripts/vault_lint.py warns (VL015) when one does not exist
  - "{src/Module/ModuleController.cs}"
  - "{src/Module/ModuleService.cs}"
tables: [] # tables, collections or queues the module owns or writes
security_triggers: [] # trigger ids a change here usually touches (auth, schema, pii-logging, ...): workflows/review-qa-and-release.md §4.3
date_verified: "{YYYY-MM-DD}" # the last time someone compared this card with the code
verified_commit: "{sha7}"
tags:
  - module
---

# MOD-{module-slug}: {Module name}

> Read this card before you change the module, and update it in the same change when the module's behaviour,
> data or entry points change (rules: `<vault>/07-Modules/README.md`). When the card and the code disagree, the
> code wins and the card is fixed.

## 1. Purpose
{Two or three sentences: what the module does for users or for other modules, and what it deliberately does not do.}

## 2. Entry Points (files)
One row per path of `entry_points`: what starts there and when to open it.

| File | What starts here |
| :--- | :--- |
| `{src/Module/ModuleController.cs}` | {HTTP routes `/api/v1/module/*`} |
| `{src/Module/ModuleService.cs}` | {business rules called by the routes and the nightly job} |

## 3. Data & Tables
| Table / collection / queue | Written by | Personal data | Notes |
| :--- | :--- | :--- | :--- |
| `{schema.Table}` | `{Service.Method}` | {yes: email, IP / no} | {retention, key indexes, migration that created it} |

## 4. Invariants
Rules that must stay true after every change, each with the place that enforces it and the test that proves it.
- {A user sees only their own records: enforced in `{Repository.Query}`, proven by `{TestName}`.}

## 5. Known Pitfalls
Traps that already cost someone time, and what to do instead.
- {Symptom, cause, the fix that worked (`[[BUG-ID]]`).}

## 6. Related ADRs & Bugs
- ADRs: [[{ADR-ID}]] ({the decision in one line})
- Bugs: [[{BUG-ID}]] ({what it taught})
- Tasks that changed the module: [[{TASK-ID}]]

## 7. Tests
| Test project / file | Covers | Command |
| :--- | :--- | :--- |
| `{tests/Module.Tests}` | {unit: service rules} | `{dotnet test tests/Module.Tests}` |

## 8. Last Verified
{YYYY-MM-DD} at `{sha7}` by {role}: {what was compared with the code: entry points, tables, invariants}. Keep
`date_verified` and `verified_commit` in the frontmatter equal to this line.
