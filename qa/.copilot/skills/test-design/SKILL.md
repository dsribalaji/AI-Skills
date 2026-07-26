# QA Agent Skill: Test Design

## Intent
Assist in translating requirements into high-level test scenarios and detailed test cases.

## Capabilities
- Extracting testable conditions from User Stories and Use Cases.
- Generating step-by-step test cases with expected results.
- Recommending appropriate test data sets (valid, invalid, boundary).

## Usage
Triggered when working in the `qa/02_test-design/` directory.

## Best Practices
- Ensure all test cases have YAML frontmatter tracing back to specific requirements (e.g., `traces: [US-###]`).
- Focus on positive, negative, and edge-case scenarios.