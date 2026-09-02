---
name: feature-module-addition-or-extension
description: Workflow command scaffold for feature-module-addition-or-extension in zen-desktop.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-module-addition-or-extension

Use this workflow when working on **feature-module-addition-or-extension** in `zen-desktop`.

## Goal

Implements a new feature or extends an existing one by creating or modifying a set of related source files, interface definitions, build configurations, preferences, and tests for a specific module or subsystem.

## Common Files

- `prefs/zen/*.yaml`
- `src/zen/<module>/*.mjs`
- `src/zen/<module>/*.cpp`
- `src/zen/<module>/*.h`
- `src/zen/<module>/*.mm`
- `src/zen/<module>/*.idl`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update or create relevant preference YAML files under prefs/zen/
- Add or modify source implementation files in a dedicated module directory under src/zen/
- Add or update interface definition files (.idl) for new APIs or system interfaces
- Add or update build configuration files (moz.build, components.conf) for the module
- Add platform-specific implementation files as needed (e.g., .cpp, .mm, .h)

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.