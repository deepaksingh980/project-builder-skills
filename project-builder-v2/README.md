# Project Builder V2 — Autonomous AI Software Factory Skill

`project-builder-v2` is an advanced AI Software Factory skill for **Antigravity CLI** and **Antigravity IDE**. It transforms raw, informal, or incomplete natural-language project scopes into fully planned, engineered, tested, audited, and production-ready applications with high discipline and safe autonomy.

---

## 🌟 What's New in V2 vs V1

| Feature | Project Builder V1 | Project Builder V2 (Software Factory) |
| :--- | :--- | :--- |
| **Scope Parsing** | Standard English technical text | Multi-lingual (English, Hindi, Hinglish, informal client text) |
| **Role Modeling** | General engineering mindset | 9 Specialized Roles (PM, Architect, DB, Backend, Frontend, QA, Security, DevOps, Code Reviewer) |
| **Project Memory** | Basic `project-state.md` | 13 Structured Artifacts in `.antigravity/` for zero-context-loss state recovery |
| **Architecture Gate**| Implicit checks | Explicit coherence gate checking circular dependencies & RBAC flow |
| **Database Safety** | Standard schema creation | Non-destructive schema engine, data preservation, & migration strategy |
| **UI/UX System** | Basic responsive checks | Design token enforcement & 5-State UI (Default, Loading, Empty, Error, Disabled) |
| **Security Review** | Basic checklist | Full OWASP Top 10 Security Gate with server-side RBAC verification |
| **Traceability** | Partial | Complete Requirement $\rightarrow$ Acceptance Criterion $\rightarrow$ Code $\rightarrow$ Test Matrix |
| **Production Gate** | Standard verification | 20-Point Production Readiness Checklist & Audit Engine |

---

## 🚀 Installation

### Option 1: Global Installation (Recommended)
To make `project-builder-v2` available across all projects on your system:

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse -Force "d:\project-builder-skills\project-builder-v2" "$env:USERPROFILE\.gemini\config\skills\project-builder-v2"
```

**macOS / Linux (Bash):**
```bash
cp -r d:/project-builder-skills/project-builder-v2 ~/.gemini/config/skills/project-builder-v2
```

### Option 2: Project-Level Installation
To install `project-builder-v2` specifically for the current project:

```powershell
New-Item -ItemType Directory -Force -Path ".agents\skills"
Copy-Item -Recurse -Force "d:\project-builder-skills\project-builder-v2" ".agents\skills\project-builder-v2"
```

---

## 💻 Supported Commands & Modes

You can invoke `project-builder-v2` using natural language or slash command aliases:

### 1. Build Mode (`/build`)
Full end-to-end project creation from raw scope.
```text
/build "Build a rental platform where owners list properties, renters book them, admins review listings, and monthly subscription plans are handled."
```
*Natural language alternative:* `"Build a rental app with owners, renters, and subscription billing."`

### 2. Continue Mode (`/continue`)
Resume work on an existing project after CLI restart or context loss.
```text
/continue
```
*Natural language alternative:* `"continue project"` or `"resume implementation"`

### 3. Feature Mode (`/feature`)
Add a new feature to an existing project without breaking current functionality.
```text
/feature "Add instant chat messaging between renters and property owners."
```
*Natural language alternative:* `"Add instant chat module between renters and owners."`

### 4. Fix Mode (`/fix`)
Diagnose and fix bugs, build failures, runtime exceptions, or failing tests.
```text
/fix "The rental booking checkout throws a 500 internal server error when dates overlap."
```

### 5. Audit Mode (`/audit`)
Perform a 10-point architecture, code quality, security, and performance review.
```text
/audit
```

### 6. Status Mode (`/status`)
Check project progress, completed modules, active tasks, and blockers.
```text
/status
```

---

## 🛡️ Safe Autonomy Policy

`project-builder-v2` operates with autonomous execution for standard development work, while enforcing strict explicit user approval gates for high-stakes actions:

✅ **Autonomous Execution Allowed**:
- Creating and modifying code files, components, and services
- Setting up databases, writing schemas, and generating migrations locally
- Writing and running unit, integration, and E2E tests
- Installing dependencies and running builds, typechecks, and linters
- Fixing local build/test failures and updating project memory (`.antigravity/`)
- Writing conventional local Git commits

🔒 **Explicit User Approval Required**:
- Production database drops, truncations, or un-tested migrations
- Git `push`, `force-push`, or branch deletion
- Cloud infrastructure creation or deployment to production
- Modifying production environment variables or secret keys
- Executing external paid API operations (e.g. sending real SMS/Emails, charging real credit cards)

---

## 📁 Skill Architecture & Directory Layout

```
project-builder-v2/
├── SKILL.md                 # Main skill manifest & 29-phase execution guide
├── README.md                # Skill documentation & user manual
│
├── workflows/               # Specialized execution workflows
│   ├── new-project.md       # Greenfield project lifecycle
│   ├── existing-project.md  # Brownfield project onboarding
│   ├── feature-development.md # Feature engineering pipeline
│   ├── bug-fix.md           # Root-cause debugging workflow
│   ├── continue.md          # State reconciliation continuation
│   ├── audit.md             # 10-point audit execution
│   └── production-readiness.md # 20-point production gating
│
├── roles/                   # Specialized agent domain expert roles
│   ├── requirements-analyst.md
│   ├── architect.md
│   ├── backend-engineer.md
│   ├── frontend-engineer.md
│   ├── database-engineer.md
│   ├── qa-engineer.md
│   ├── security-engineer.md
│   ├── devops-engineer.md
│   └── code-reviewer.md
│
├── standards/               # Universal engineering standards
│   ├── coding.md
│   ├── api.md
│   ├── database.md
│   ├── frontend.md
│   ├── security.md
│   ├── testing.md
│   └── git.md
│
├── templates/               # Project memory templates (.antigravity/)
│   ├── project-profile.md
│   ├── project-state.md
│   ├── requirements.md
│   ├── architecture.md
│   ├── database.md
│   ├── api-contracts.md
│   ├── ui-plan.md
│   ├── task-plan.md
│   ├── qa-report.md
│   ├── security-report.md
│   └── production-audit.md
│
└── examples/                # Reference implementations & prompt walk-throughs
    ├── simple-crud.md
    ├── saas-platform.md
    ├── ecommerce.md
    └── rental-platform.md
```

---

## 🛡️ V1 Compatibility Guarantee

`project-builder-v2` is completely decoupled from `project-builder-v1`. Installing and using V2 will not alter, move, overwrite, or affect V1 files in any way. Both skills can coexist peacefully in your environment.
