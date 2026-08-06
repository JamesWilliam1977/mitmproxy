```markdown
# mitmproxy Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the development patterns and conventions used in the `mitmproxy` TypeScript codebase. You'll learn how to structure files, write imports and exports, follow commit message practices, and understand the testing approach. This guide is ideal for contributors aiming to maintain consistency and quality in the codebase.

## Coding Conventions

### File Naming
- Use **PascalCase** for file names.
  - Example: `MyComponent.ts`, `UserProfile.ts`

### Import Style
- Use **relative imports** for referencing other modules.
  - Example:
    ```typescript
    import { Helper } from './Helper';
    ```

### Export Style
- Both **named** and **default exports** are used.
  - Named export:
    ```typescript
    export function processData() { ... }
    ```
  - Default export:
    ```typescript
    export default class User { ... }
    ```

### Commit Messages
- Freeform style, sometimes prefixed with `web`.
- Average commit message length: ~42 characters.
  - Example:
    ```
    web: fix header parsing in proxy handler
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new feature or component.
**Command:** `/add-feature`

1. Create a new file using PascalCase (e.g., `NewFeature.ts`).
2. Use relative imports to include dependencies.
3. Export your feature using named or default export as appropriate.
4. Write corresponding tests in a `.test.ts` file.
5. Commit changes with a descriptive message, optionally prefixed with `web`.

### Fixing a Bug
**Trigger:** When resolving a bug in the codebase.
**Command:** `/fix-bug`

1. Locate the relevant file(s) and make necessary changes.
2. Ensure imports remain relative and exports follow conventions.
3. Update or add tests to cover the bug fix.
4. Commit with a clear, concise message (e.g., `web: fix bug in request parser`).

### Writing and Running Tests
**Trigger:** When validating code functionality.
**Command:** `/run-tests`

1. Write tests in files matching the pattern `*.test.ts`.
2. Use the project's preferred testing framework (unspecified; check project docs or package.json).
3. Run tests using the project's test runner (e.g., `npm test` or similar).

## Testing Patterns

- All tests are written in TypeScript files ending with `.test.ts`.
- The specific testing framework is not detected; refer to project documentation for details.
- Example test file:
  ```typescript
  import { processData } from './ProcessData';

  test('should process data correctly', () => {
    expect(processData([1, 2, 3])).toEqual([2, 3, 4]);
  });
  ```

## Commands
| Command      | Purpose                                      |
|--------------|----------------------------------------------|
| /add-feature | Start workflow for adding a new feature      |
| /fix-bug     | Begin workflow for fixing a bug              |
| /run-tests   | Run all tests in the codebase                |
```