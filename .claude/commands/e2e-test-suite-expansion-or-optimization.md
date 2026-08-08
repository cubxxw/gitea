---
name: e2e-test-suite-expansion-or-optimization
description: Workflow command scaffold for e2e-test-suite-expansion-or-optimization in gitea.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /e2e-test-suite-expansion-or-optimization

Use this workflow when working on **e2e-test-suite-expansion-or-optimization** in `gitea`.

## Goal

Add new end-to-end (e2e) tests and/or optimize the test suite for speed and coverage.

## Common Files

- `tests/e2e/**/*.test.ts`
- `tests/e2e/utils.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or edit multiple files in tests/e2e/ to add new test cases or optimize existing ones.
- Optionally update test utilities in tests/e2e/utils.ts.
- Document or comment on test changes for clarity.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.