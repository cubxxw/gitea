---
name: refactor-backend-feature-or-endpoint
description: Workflow command scaffold for refactor-backend-feature-or-endpoint in gitea.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /refactor-backend-feature-or-endpoint

Use this workflow when working on **refactor-backend-feature-or-endpoint** in `gitea`.

## Goal

Refactor or improve backend logic for a feature or endpoint, often splitting functions, improving structure, or changing how data is prepared and served.

## Common Files

- `modules/**/*.go`
- `routers/**/*.go`
- `services/**/*.go`
- `templates/**/*.tmpl`
- `tests/integration/**/*.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit Go source files in modules/, routers/, or services/ to refactor logic or split functions.
- Update related templates if output or data structure changes.
- Update or add tests in tests/integration/ or modules/ to cover the refactored logic.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.