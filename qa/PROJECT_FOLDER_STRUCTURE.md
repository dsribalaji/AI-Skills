# QA Project Folder Structure
**Governs:** All outputs from the QA agent suite
**Principle:** Folder = phase. File = artifact. Name = findable without opening it.

---

## Root Layout

```
PROJECT_NAME/
│
├── .copilot/                   ← skills, agent prompts, tools (your toolkit)
├── 01_test-planning/           ← Agent 1 — Test Strategy and Planning
├── 02_test-design/             ← Agent 2 — Test Cases and Scenarios
├── 03_test-execution/          ← Agent 3 — Test Runs and Results
├── 04_defect-management/       ← Agent 4 — Bug Tracking and Triage
├── 05_test-automation/         ← Agent 5 — Automation Scripts and Frameworks
├── _admin/                     ← decisions log, glossary, README
└── project_references/         ← reference documents and assets
```

---

## .copilot/ — Your Toolkit

```
.copilot/
├── skills/
│   ├── test-planning/
│   │   └── SKILL.md
│   ├── test-design/
│   │   └── SKILL.md
│   ├── test-execution/
│   │   └── SKILL.md
│   ├── defect-management/
│   │   └── SKILL.md
│   └── test-automation/
│       └── SKILL.md
│
├── agents/
│   ├── AGENT_test-planning.md
│   ├── AGENT_test-design.md
│   ├── AGENT_test-execution.md
│   ├── AGENT_defect-management.md
│   └── AGENT_test-automation.md
│
└── tools/                      ← helpers and scripts
```

> This folder never holds project-specific content. It is your reusable toolkit, identical across projects.

---

## 01_test-planning/ — Strategy and Plans

```
01_test-planning/
├── test-strategy.md            ← overarching strategy: scope, approach, environments, tools
├── test-plan.md                ← detailed plan per release/sprint: resources, schedule, risks
└── risk-assessment.md          ← identified risks and mitigation strategies
```

**Naming convention:** Flat files — stable documents for the project or sprint.

**Done signal:** Test strategy and plan approved by stakeholders.

---

## 02_test-design/ — Test Cases and Scenarios

```
02_test-design/
├── scenarios/
│   ├── TS-001_[FeatureName]_scenarios.md    ← high-level test scenarios
│   └── TS-002_[FeatureName]_scenarios.md
│
└── cases/
    ├── TC-001_[ScenarioName]_case.md        ← detailed steps, expected results, test data
    └── TC-002_[ScenarioName]_case.md
```

**Naming convention:** Type prefix + sequence + feature/scenario name.

**Done signal:** All scenarios and cases are documented and mapped to requirements (BRD/Use Cases).

---

## 03_test-execution/ — Test Runs and Results

```
03_test-execution/
├── runs/
│   ├── TR-001_[Release/Sprint]_[YYYY-MM-DD].md  ← test run summary and scope
│   └── TR-002_[Release/Sprint]_[YYYY-MM-DD].md
│
└── results/
    ├── RES-001_[TestCaseID]_[Status].md         ← individual test case execution result
    └── RES-002_[TestCaseID]_[Status].md
```

**Naming convention:** Prefix + sequence + context + date/status.

**Done signal:** All planned test cases executed, results logged.

---

## 04_defect-management/ — Bug Tracking and Triage

```
04_defect-management/
├── bugs/
│   ├── BUG-001_[Short_Description].md       ← detailed bug report: steps to reproduce, logs
│   └── BUG-002_[Short_Description].md
│
└── triage-log.md                            ← log of bug triage meetings and decisions
```

**Naming convention:** Prefix + sequence + description.

**Done signal:** All defects are logged, prioritized, and linked to test cases/requirements.

---

## 05_test-automation/ — Automation Scripts and Frameworks

```
05_test-automation/
├── scripts/
│   ├── AUTO-001_[FeatureName].md            ← automation script specification or code
│   └── AUTO-002_[FeatureName].md
│
└── framework-setup.md                       ← documentation on automation framework setup
```

**Naming convention:** Prefix + sequence + feature.

**Done signal:** Automated tests passing and integrated into CI/CD (if applicable).

---

## _admin/ — Cross-Cutting Files

```
_admin/
├── README.md                   ← QA project overview, current phase, next action
├── decisions-log.md            ← decisions related to QA tools, environments, etc.
└── glossary.md                 ← QA-specific terminology
```

---

## File Naming Rules — The Full System

| Prefix | Type | Phase | Example |
|--------|------|-------|---------|
| `TS-###` | Test Scenario | 02 | `TS-001_Login_scenarios.md` |
| `TC-###` | Test Case | 02 | `TC-012_ValidLogin_case.md` |
| `TR-###` | Test Run | 03 | `TR-001_Sprint1_2025-06-01.md` |
| `RES-###`| Test Result | 03 | `RES-012_TC-012_Passed.md` |
| `BUG-###`| Bug Report | 04 | `BUG-005_LoginCrash.md` |
| `AUTO-###`| Automation | 05 | `AUTO-001_Login_UI.md` |

**Four rules for all filenames:**
1. Prefix first — enables sorting by type in any file explorer
2. Sequence number zero-padded to three digits — 001, 012, 100
3. Descriptive slug in kebab-case — readable without opening the file
4. No dates in TS, TC, BUG files — versions/status go in the file header

---

## Status Tracking — Use File Headers

Every artifact file opens with a status block:

```yaml
---
id:       TC-012
name:     Valid Login Test
status:   APPROVED          # DRAFT | UNDER_REVIEW | APPROVED | DEPRECATED
version:  1.0
traces:   [US-023, BRD-v1.0]
updated:  2025-06-19
verdict:  READY             # READY | NEEDS_WORK
---
```

## The Traceability Chain

Ensure every test case links back to a requirement or user story. Ensure every bug links back to a test case or test run.
