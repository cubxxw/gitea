```markdown
# gitea Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the `gitea` codebase, focusing on TypeScript development patterns, coding conventions, and common workflows. It covers code style, file organization, testing, and step-by-step instructions for frequent tasks such as backend refactoring, e2e test expansion, and frontend cleanup.

## Coding Conventions

- **File Naming:**  
  Use camelCase for file names.  
  _Example:_  
  ```
  pullRequestView.ts
  assetManager.ts
  ```

- **Import Style:**  
  Use relative imports for modules.  
  _Example:_  
  ```typescript
  import { fetchData } from './apiUtils';
  import { renderHeader } from '../components/header';
  ```

- **Export Style:**  
  Use named exports.  
  _Example:_  
  ```typescript
  // In utils.ts
  export function parseDate(str: string): Date { ... }
  export function formatUser(user: User): string { ... }

  // In another file
  import { parseDate, formatUser } from './utils';
  ```

- **Commit Messages:**  
  - Use freeform messages, often prefixed with `feat` or `refactor`.
  - Keep messages concise (~50 characters).
  _Examples:_  
  ```
  feat: add new asset upload endpoint
  refactor: split pull request logic into modules
  ```

## Workflows

### Refactor Backend Feature or Endpoint
**Trigger:** When you need to refactor or improve backend logic for a feature or endpoint (e.g., pull request views, asset serving).  
**Command:** `/refactor-backend`

1. Edit Go source files in `modules/`, `routers/`, or `services/` to refactor logic or split functions.
2. Update related templates in `templates/` if output or data structure changes.
3. Update or add tests in `tests/integration/` or `modules/` to cover the refactored logic.

_Example:_  
```go
// Before: modules/pullRequest.go
func HandlePullRequest(...) {
  // monolithic logic
}

// After: modules/pullRequest.go
func PreparePullRequestData(...) { ... }
func RenderPullRequestView(...) { ... }
```

### E2E Test Suite Expansion or Optimization
**Trigger:** When you want to add new end-to-end (e2e) test cases or optimize the test suite for speed and coverage.  
**Command:** `/add-e2e-test`

1. Create or edit files in `tests/e2e/` to add new test cases or optimize existing ones.
2. Optionally update test utilities in `tests/e2e/utils.ts`.
3. Document or comment on test changes for clarity.

_Example:_  
```typescript
// tests/e2e/pullRequest.test.ts
import { setupUser, createPR } from './utils';

test('user can create a pull request', async () => {
  const user = await setupUser();
  const pr = await createPR(user, { ... });
  expect(pr.status).toBe('open');
});
```

### Frontend Style or JS Cleanup
**Trigger:** When you want to remove unused CSS or JavaScript/TypeScript code, especially for UI components or helpers.  
**Command:** `/cleanup-frontend`

1. Identify unused CSS or JS/TS files or code blocks.
2. Remove or refactor the identified code in `web_src/css/modules/`, `web_src/js/modules/`, `web_src/js/features/`, and related files.
3. Cross-check for runtime or template usages before deletion.

_Example:_  
```typescript
// web_src/js/modules/obsoleteHelper.ts
// Remove this file if no longer used in any templates or runtime code.
```

## Testing Patterns

- **Framework:**  
  Use [Jest](https://jestjs.io/) for testing TypeScript code.

- **File Pattern:**  
  Test files are named with the `.test.ts` suffix and are placed alongside the code or in dedicated test directories.  
  _Example:_  
  ```
  tests/e2e/pullRequest.test.ts
  web_src/js/modules/assetManager.test.ts
  ```

- **Test Example:**  
  ```typescript
  // assetManager.test.ts
  import { uploadAsset } from './assetManager';

  test('uploads asset successfully', async () => {
    const result = await uploadAsset(mockFile);
    expect(result.success).toBe(true);
  });
  ```

## Commands

| Command            | Purpose                                                      |
|--------------------|--------------------------------------------------------------|
| /refactor-backend  | Refactor or improve backend logic for a feature or endpoint  |
| /add-e2e-test      | Add or optimize end-to-end test cases                        |
| /cleanup-frontend  | Remove unused frontend CSS or JS/TS code                     |
```