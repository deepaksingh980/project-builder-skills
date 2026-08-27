# Git Intelligence & Commit Standards

## 1. Commit Message Conventions
Follow the Conventional Commits specification:

- `feat(scope)`: New feature implementation
- `fix(scope)`: Bug fix or error resolution
- `docs(scope)`: Documentation or project memory updates
- `style(scope)`: Formatting, missing semi-colons, UI polish
- `refactor(scope)`: Code restructuring without changing behavior
- `test(scope)`: Adding or updating test suites
- `chore(scope)`: Build scripts, package manager updates

**Examples:**
```text
feat(auth): implement JWT authentication & RBAC middleware
fix(booking): resolve date overlap check in booking controller
docs(memory): update task plan and architecture specs
```

## 2. Pre-Commit Verification
Before writing a local git commit:
1. Inspect `git status` and `git diff`.
2. Confirm zero temporary files or hardcoded credentials are included.
3. Verify typecheck and tests pass cleanly.

## 3. Safe Git Protocol (Non-Destructive Rules)
- **Local Commits Only**: `project-builder-v2` creates local commits autonomously after completing coherent tasks.
- **NO Automatic Push**: NEVER execute `git push` without explicit user permission.
- **NO Force Push**: NEVER execute `git push -f` or alter remote commit history.
- **NO Destructive Operations**: NEVER delete branches, reset hard, or stash unstaged changes without user approval.
