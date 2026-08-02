```markdown
# zen-desktop Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns, coding conventions, and workflows used in the `zen-desktop` project. The repository is primarily JavaScript-based, with a modular architecture and no specific framework detected. It emphasizes clear commit patterns, consistent code style, and structured feature development workflows. This guide will help you contribute effectively to `zen-desktop` by following its established conventions.

## Coding Conventions

### File Naming
- **CamelCase** is used for file names.
  - Example: `windowManager.mjs`, `dragAndDropHandler.mjs`

### Import Style
- **Relative imports** are used throughout the codebase.
  - Example:
    ```javascript
    import { getWindowState } from './windowState.mjs';
    ```

### Export Style
- **Named exports** are preferred.
  - Example:
    ```javascript
    // windowManager.mjs
    export function openWindow() { /* ... */ }
    export function closeWindow() { /* ... */ }
    ```

### Commit Patterns
- Commits reference tickets and use a prefix.
- Example commit message:
  ```
  ticket-1234: Add compact mode preference and update window layout logic
  ```

## Workflows

### Feature Module Addition or Extension
**Trigger:** When adding a new capability or major feature to a subsystem (e.g., compact mode, drag-and-drop, window drag) in zen-desktop.  
**Command:** `/new-feature-module`

Follow these steps to implement or extend a feature module:

1. **Update or create preference YAML files**  
   - Location: `prefs/zen/`
   - Example: `prefs/zen/compactMode.yaml`
2. **Add or modify source implementation files**  
   - Location: `src/zen/<module>/`
   - Example: `src/zen/compactMode/compactModeManager.mjs`
3. **Add or update interface definition files (.idl)**  
   - For new APIs or system interfaces.
   - Example: `src/zen/compactMode/compactMode.idl`
4. **Add or update build configuration files**  
   - Files: `moz.build`, `components.conf`
   - Example: `src/zen/compactMode/moz.build`
5. **Add platform-specific implementation files as needed**  
   - Examples: `.cpp`, `.mm`, `.h`
   - Example: `src/zen/compactMode/CompactMode.mm`
6. **Update or create test files and test build configs**  
   - Location: `src/zen/tests/<feature>/`
   - Example: `src/zen/tests/compactMode/compactMode.test.ts`
   - Update `src/zen/tests/moz.build` as needed.
7. **Update the top-level module build file**  
   - File: `src/zen/moz.build`  
   - Ensure your new or changed module is included.

**Example Directory Structure:**
```
prefs/zen/compactMode.yaml
src/zen/compactMode/compactModeManager.mjs
src/zen/compactMode/compactMode.idl
src/zen/compactMode/moz.build
src/zen/compactMode/components.conf
src/zen/tests/compactMode/compactMode.test.ts
src/zen/moz.build
```

## Testing Patterns

- **Test files** use the `.test.ts` pattern.
  - Example: `windowManager.test.ts`
- **Testing framework** is not explicitly detected; check existing tests for conventions.
- Place tests under `src/zen/tests/<feature>/`.

**Example test file:**
```typescript
// src/zen/tests/compactMode/compactMode.test.ts
import { enableCompactMode } from '../../compactMode/compactModeManager.mjs';

test('enables compact mode', () => {
  expect(enableCompactMode()).toBe(true);
});
```

## Commands

| Command              | Purpose                                                        |
|----------------------|----------------------------------------------------------------|
| /new-feature-module  | Scaffold and guide the addition or extension of a feature module|
```
