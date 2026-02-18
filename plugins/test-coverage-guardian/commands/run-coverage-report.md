---
name: run-coverage-report
description: Run the full test suite with coverage and generate a detailed report identifying untested code paths.
---

# Run Coverage Report

Execute tests with coverage collection and generate actionable report.

## Steps

1. Run test suite with coverage flags:
   - Jest: `npx jest --coverage --coverageReporters=lcov,text`
   - pytest: `pytest --cov=src --cov-report=html --cov-report=term`
   - Go: `go test ./... -coverprofile=coverage.out`
2. Parse coverage output
3. Identify files below threshold
4. List top uncovered functions by risk
5. Generate test stubs for critical gaps
6. Output summary report to `coverage-report.md`
7. Fail if overall coverage below configured threshold
