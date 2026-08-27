# Project Builder Skill

A production-oriented Antigravity CLI skill for turning natural-language software scopes into structured, verified implementations.

## Install

Workspace-specific:

```bash
mkdir -p .agents/skills
cp -R project-builder .agents/skills/
```

Global for Antigravity CLI:

```bash
mkdir -p ~/.gemini/antigravity-cli/skills
cp -R project-builder ~/.gemini/antigravity-cli/skills/
```

Antigravity's official docs define `.agents/skills/<skill>/SKILL.md` as the workspace skill location; global configuration is also supported. Verify your installed CLI's global path if your version differs.

## Use

Give the agent a natural-language scope such as:

> Use the project-builder skill. Build a multi-vendor food ordering platform with customer, vendor, delivery partner, and admin roles. Use Next.js, NestJS, PostgreSQL and Tailwind. Make it production-ready.

For an existing project:

> Use project-builder. Continue the project from the current state and implement the remaining modules.

Other modes can be inferred from requests such as:
- plan this project
- add this feature
- fix this bug
- audit this project
- show project status

## Design

The skill keeps durable project state in `.antigravity/` so work can resume across sessions without relying only on chat history.
