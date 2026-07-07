```markdown
# CARD-PRESS Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and conventions used in the CARD-PRESS TypeScript codebase. It covers file organization, code style, import/export patterns, and testing approaches, providing practical examples and suggested commands for common workflows. The repository does not use a specific framework, focusing on clean, modular TypeScript code.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `cardUtils.ts`, `userProfile.ts`

### Imports
- Use **relative imports** for referencing other modules.
  - Example:
    ```typescript
    import { getCard } from './cardUtils';
    ```

### Exports
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // cardUtils.ts
    export function getCard(id: string) { ... }
    export const CARD_TYPE = 'standard';
    ```

### Commit Messages
- Freeform, no enforced prefixes.
- Average commit message length: ~24 characters.

## Workflows

### Add a New Module
**Trigger:** When you need to add new functionality as a separate module.
**Command:** `/add-module`

1. Create a new file using camelCase (e.g., `featureName.ts`).
2. Implement your functions or constants.
3. Use named exports for all public APIs.
    ```typescript
    // featureName.ts
    export function doSomething() { ... }
    ```
4. Import your module in other files using a relative path.
    ```typescript
    import { doSomething } from './featureName';
    ```

### Write a Test
**Trigger:** When you add or update a module and want to ensure correctness.
**Command:** `/write-test`

1. Create a test file with the pattern `*.test.ts` (e.g., `featureName.test.ts`).
2. Write your test cases using your preferred testing framework.
    ```typescript
    // featureName.test.ts
    import { doSomething } from './featureName';

    test('doSomething works', () => {
      expect(doSomething()).toBe(true);
    });
    ```
3. Run your tests using the project's test runner.

### Refactor an Import
**Trigger:** When reorganizing files or cleaning up imports.
**Command:** `/refactor-import`

1. Update import statements to use relative paths.
    ```typescript
    // Before
    import { getCard } from 'cardUtils';
    // After
    import { getCard } from './cardUtils';
    ```
2. Ensure all imports are updated across affected files.

## Testing Patterns

- Test files follow the `*.test.ts` naming convention and are placed alongside or near the modules they test.
- The specific testing framework is not detected, but typical test structure applies:
    ```typescript
    // example.test.ts
    import { exampleFunction } from './example';

    test('exampleFunction returns correct value', () => {
      expect(exampleFunction()).toBe('expected');
    });
    ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /add-module     | Scaffold a new module with proper conventions|
| /write-test     | Create a test file for a module              |
| /refactor-import| Update import statements to be relative      |
```