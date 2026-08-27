# New Project Workflow

Use for a greenfield project.

1. Inspect workspace and available instructions.
2. Normalize the scope.
3. Confirm stack only when missing or materially ambiguous.
4. Create architecture and task plan.
5. Initialize the project using the correct package manager/tooling.
6. Implement foundation:
   - configuration
   - environment handling
   - shared types/utilities
   - error handling
   - logging
7. Implement core business modules in dependency order.
8. Implement authentication/RBAC if required.
9. Implement UI and responsive states.
10. Add tests.
11. Run typecheck/lint/test/build.
12. Fix failures.
13. Run final requirement and security audit.
14. Update project state.
