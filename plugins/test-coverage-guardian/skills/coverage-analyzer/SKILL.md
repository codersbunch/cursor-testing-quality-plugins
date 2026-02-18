---
name: coverage-analyzer
description: Analyze test coverage reports to identify untested code paths, uncovered branches, and prioritize what to test next.
---

# Coverage Analyzer

## When to use

- After running test suite to find gaps
- During code review to verify coverage
- When planning testing sprints
- Before production deployments

## Instructions

1. **Parse coverage report** (lcov, Istanbul, coverage.xml)
2. **Identify uncovered lines** and group by file/module
3. **Find uncovered branches** - if/else paths never executed
4. **Prioritize by risk**:
   - Business-critical code first
   - Error handling paths
   - Security-sensitive functions
   - Recently changed code
5. **Generate test stubs** for top uncovered functions
6. **Calculate coverage delta** from previous run
7. **Block PR** if coverage drops below threshold

## Output

- Coverage summary table by module
- Top 10 highest-risk uncovered functions
- Generated test stubs ready to fill in
- Coverage trend over last 5 runs
