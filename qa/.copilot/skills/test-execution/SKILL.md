# QA Agent Skill: Test Execution

## Intent
Support the management of test runs and logging of test results.

## Capabilities
- Structuring test run summaries for specific sprints or releases.
- Generating templates for individual test case results.
- Aggregating result metrics (e.g., pass/fail rates).

## Usage
Triggered when working in the `qa/03_test-execution/` directory.

## Best Practices
- Every test result must reference the specific test case ID it corresponds to.
- Clearly document blocking issues when a test fails.