# GitHub Copilot Chat Agent Guide - QA Role

## Repository intent
This directory contains the workflows, templates, and agent tools for the **Quality Assurance (QA)** role within the Effex.dev toolkit hub. It focuses on ensuring quality through systematic test planning, design, execution, defect management, and automation.

## What QA agents should do
- Assist in developing comprehensive test strategies and plans.
- Generate test scenarios and detailed test cases based on requirements and user stories.
- Help structure test execution runs and log results effectively.
- Streamline defect reporting, ensuring all necessary details (reproduction steps, logs, expected vs actual) are captured.
- Provide guidance on test automation framework setup and script generation.
- Maintain traceability from requirements to test cases to defects.

## Key artifact locations
- `.copilot/agents/` — Copilot agent guidance and example use cases for QA.
- `.copilot/skills/` — Skill descriptions that help Copilot understand QA-specific tasks (e.g., test design, bug triage).
- `.copilot/tools/` — Tool descriptions or helper scripts that support QA workflows.
- `01_test-planning/` — High-level test strategies and plans.
- `02_test-design/` — Test scenarios and detailed test cases.
- `03_test-execution/` — Test runs and execution results.
- `04_defect-management/` — Bug reports and triage logs.
- `05_test-automation/` — Automation scripts and framework docs.

## Execution notes
- Follow the naming conventions defined in `PROJECT_FOLDER_STRUCTURE.md`.
- Ensure all test artifacts maintain traceability via YAML headers.

## Important caution
- Do not expose sensitive test data or credentials in test cases or bug reports.
- Use mock data for all examples and templates.
