```markdown
# ohmyzsh Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the core development patterns and conventions used in the `ohmyzsh` repository, which is primarily written in TypeScript. It outlines file naming, import/export styles, commit message conventions, and testing patterns. This guide will help you contribute code that aligns with the project's standards and maintain consistency across the codebase.

## Coding Conventions

### File Naming
- **Style:** kebab-case
- **Example:**  
  ```
  user-profile.ts
  utils/helpers.ts
  ```

### Import Style
- **Style:** Relative imports
- **Example:**
  ```typescript
  import { getUser } from './user-utils';
  import { calculateSum } from '../math/calc';
  ```

### Export Style
- **Style:** Named exports
- **Example:**
  ```typescript
  // In user-utils.ts
  export function getUser(id: string) { ... }
  export const DEFAULT_USER = { ... };

  // Importing
  import { getUser, DEFAULT_USER } from './user-utils';
  ```

### Commit Message Conventions
- **Type:** Conventional Commits
- **Common Prefixes:** `chore`
- **Average Length:** ~42 characters
- **Example:**
  ```
  chore: update dependencies to latest versions
  ```

## Workflows

### Code Contribution
**Trigger:** When adding new features, fixing bugs, or making changes  
**Command:** `/contribute`

1. Create a new branch from `main`
2. Make your code changes following the coding conventions
3. Write or update tests as needed (see Testing Patterns)
4. Commit your changes using the conventional commit format
5. Push your branch and open a pull request

### Dependency Maintenance
**Trigger:** When updating or maintaining dependencies  
**Command:** `/update-deps`

1. Run the package manager to update dependencies
2. Test the codebase to ensure nothing is broken
3. Commit with a message like `chore: update dependencies`
4. Push and create a pull request

## Testing Patterns

- **Test File Pattern:** Files end with `.test.*` (e.g., `user-utils.test.ts`)
- **Testing Framework:** Not explicitly detected; follow standard TypeScript testing practices
- **Example Test File:**
  ```typescript
  // user-utils.test.ts
  import { getUser } from './user-utils';

  describe('getUser', () => {
    it('should return the correct user', () => {
      expect(getUser('123')).toEqual({ id: '123', name: 'Alice' });
    });
  });
  ```

## Commands

| Command        | Purpose                                      |
|----------------|----------------------------------------------|
| /contribute    | Start a new code contribution workflow       |
| /update-deps   | Update dependencies and commit changes       |
```
