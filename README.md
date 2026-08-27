# Project Builder Skills Repository

Welcome to the **Project Builder Skills** repository — a collection of AI engineering skills for **Antigravity CLI** and **Antigravity IDE**.

This repository houses both the original **V1 skill** (`project-builder-v1`) and the upgraded **V2 AI Software Factory skill** (`project-builder-v2`).

---

## 📂 Repository Layout

```text
project-builder-skills/
├── README.md                 # Root repository documentation (this file)
│
├── project-builder-v1/       # Legacy V1 Skill (Preserved & Functional)
│   ├── SKILL.md              # V1 skill manifest
│   ├── README.md             # V1 documentation
│   ├── roles/                # V1 role definitions
│   ├── standards/            # V1 coding standards
│   ├── templates/            # V1 project templates
│   └── workflows/            # V1 operational workflows
│
└── project-builder-v2/       # V2 AI Software Factory Skill (Latest & Advanced)
    ├── SKILL.md              # Main V2 skill manifest & 29-phase execution guide
    ├── README.md             # Detailed V2 user guide
    ├── workflows/            # 7 Specialized execution workflows
    ├── roles/                # 9 Domain expert agent roles
    ├── standards/            # 7 Universal engineering standards
    ├── templates/            # 11 Project memory templates (.antigravity/)
    └── examples/             # 4 End-to-end reference implementation guides
```

---

## ⚡ Quick Comparison: V1 vs V2

| Feature | `project-builder-v1` | `project-builder-v2` (AI Software Factory) |
| :--- | :--- | :--- |
| **Status** | Stable Legacy V1 | Active Production V2 |
| **Scope Parsing** | Standard English | Multi-Lingual (English, Hindi, Hinglish, informal client speak) |
| **Agent Roles** | 5 Core Roles | 9 Specialized Roles (PM, Architect, Backend, Frontend, DB, QA, Security, DevOps, Code Reviewer) |
| **Project Memory** | Basic `project-state.md` | 13 Structured Artifacts in `.antigravity/` for zero-context-loss state recovery |
| **UI/UX System** | Basic responsive rules | Design Token System + 5 UI States (Default, Loading, Empty, Error, Disabled) |
| **Database Safety** | Standard schema generation | Non-Destructive Engine, Migration Scripts & Data Preservation |
| **Security Audit** | Standard Checklist | Full OWASP Top 10 Security Gate with Server-Side RBAC Verification |
| **Readiness Gate** | Basic Build Checks | 20-Point Production Readiness Gate Checklist |
| **Slash Commands** | Standard modes | `/build`, `/plan`, `/continue`, `/feature`, `/fix`, `/audit`, `/status`, `/test`, `/review` |

---

## 🚀 Installation & Setup

### 1. Global Installation (Recommended)
Installing globally allows Antigravity CLI and Antigravity IDE to recognize `project-builder-v2` across any project folder on your system.

#### Windows (PowerShell):
```powershell
# Install V2 globally
Copy-Item -Recurse -Force "d:\project-builder-skills\project-builder-v2" "$env:USERPROFILE\.gemini\config\skills\project-builder-v2"

# (Optional) Install V1 globally
Copy-Item -Recurse -Force "d:\project-builder-skills\project-builder-v1" "$env:USERPROFILE\.gemini\config\skills\project-builder-v1"
```

#### macOS / Linux (Bash):
```bash
# Install V2 globally
cp -r d:/project-builder-skills/project-builder-v2 ~/.gemini/config/skills/project-builder-v2

# (Optional) Install V1 globally
cp -r d:/project-builder-skills/project-builder-v1 ~/.gemini/config/skills/project-builder-v1
```

---

### 2. Project-Level Installation
To use `project-builder-v2` inside a specific project repository:

```powershell
# Create the local skills directory if it doesn't exist
New-Item -ItemType Directory -Force -Path ".agents\skills"

# Copy V2 to local workspace skills
Copy-Item -Recurse -Force "d:\project-builder-skills\project-builder-v2" ".agents\skills\project-builder-v2"
```

---

## 🛠️ How to Use `project-builder-v2`

### Mode 1: Full Autonomous Project Creation (`/build`)
Give a raw natural-language project scope. V2 will analyze requirements, select stack, design database schemas, write API contracts, build responsive UI components, execute self-fix error recovery, and audit the application.

```text
/build "Build a rental platform where owners list properties, renters book them, monthly subscriptions are managed, and admins review listings."
```

---

### Mode 2: Resume Interrupted Work (`/continue`)
If execution was stopped, CLI restarted, or terminal closed, resume seamlessly from `.antigravity/` project memory.

```text
/continue
```
*Natural language alternative:* `"continue project"` or `"resume implementation"`

---

### Mode 3: Add New Feature (`/feature`)
Add a new module to an existing application without breaking existing code.

```text
/feature "Add instant chat messaging between renters and property owners."
```

---

### Mode 4: Diagnose & Self-Fix Bugs (`/fix`)
Pass a bug description or failing log. V2 isolates root causes, makes minimal robust fixes, and adds regression tests.

```text
/fix "Booking checkout throws a 500 error when rental dates overlap."
```

---

### Mode 5: 10-Point Project Audit (`/audit`)
Perform an architecture, code quality, security, and performance review without making code changes unless explicitly asked.

```text
/audit
```

---

### Mode 6: Status & Progress Check (`/status`)
View completion percentage, active tasks, blocked items, and next recommended actions.

```text
/status
```

---

## 🧠 Project Memory System (`.antigravity/`)

`project-builder-v2` maintains project memory inside `.antigravity/` to survive session restarts:

| File Path | Description |
| :--- | :--- |
| `.antigravity/project-profile.md` | Stack selection, business domain, auth, infrastructure, constraints |
| `.antigravity/project-state.md` | Current mode, active task, task statuses, completion % |
| `.antigravity/requirements.md` | Requirement matrix (Explicit vs Assumptions vs Critical Unknowns) |
| `.antigravity/architecture.md` | System boundaries, layer hierarchy, component flow diagrams |
| `.antigravity/database.md` | ER diagrams, tables, fields, indexes, foreign keys, migration history |
| `.antigravity/api-contracts.md` | REST/GraphQL endpoint specs, request/response bodies, error schemas |
| `.antigravity/ui-plan.md` | Routes, responsive breakpoints, design tokens, 5 UI states |
| `.antigravity/task-plan.md` | Dependency-aware task queue (`PENDING`, `IN_PROGRESS`, `COMPLETED`) |
| `.antigravity/qa-report.md` | Test execution results & Requirement Traceability Matrix |
| `.antigravity/security-report.md` | OWASP Top 10 security audit results & RBAC verification |
| `.antigravity/production-audit.md` | 20-Point Production Readiness Gate Checklist |
| `.antigravity/decisions.md` | Architecture Decision Records (ADRs) and safe default choices |
| `.antigravity/changelog.md` | Versioned record of completed tasks and local git commits |

---

## 🛡️ Safe Autonomy Policy

`project-builder-v2` runs autonomously for safe engineering tasks while gating high-stakes actions behind explicit user approval:

✅ **Autonomous**:
- Writing source code, components, services, and tests
- Running build commands, linters, typecheckers, and test runners
- Writing local conventional Git commits
- Managing local `.antigravity/` project state files

🔒 **Explicit Approval Required**:
- Production database drops, truncations, or un-tested migrations
- Executing `git push`, `force-push`, or branch deletion
- Cloud infrastructure creation or deployment to production servers
- Modifying production environment variables or secret keys
- Triggering irreversible external paid APIs (e.g. sending real SMS/Emails, charging real credit cards)

---

## 📌 Maintenance & Support

- **V1 Folder**: [`project-builder-v1/`](file:///d:/project-builder-skills/project-builder-v1) is preserved for backwards compatibility.
- **V2 Folder**: [`project-builder-v2/`](file:///d:/project-builder-skills/project-builder-v2) is the active, full-featured AI Software Factory skill.
