---
name: test-generator
description: Generate comprehensive unit, integration, and e2e tests for any function, class, or API endpoint. Covers happy paths, edge cases, and error scenarios.
---

# Test Generator

## When to use

- After writing a new function or class
- When coverage drops below threshold
- Before submitting a pull request
- When adding tests to legacy untested code

## Instructions

1. **Analyze the target code** - understand inputs, outputs, side effects
2. **Generate unit tests** covering:
   - Happy path with typical inputs
   - Boundary values (empty, null, max, min)
   - Error cases (invalid input, exceptions)
   - All branches in conditional logic
3. **Generate integration tests** for:
   - API endpoints with real HTTP calls
   - Database operations with test DB
   - Service-to-service interactions
4. **Generate e2e tests** for:
   - Critical user journeys
   - Using Playwright or Cypress
5. **Mock strategy** - suggest what to mock vs. use real implementations
6. **Framework detection** - output for Jest, Vitest, pytest, Go test, JUnit

## Output format

```typescript
describe('UserService', () => {
  describe('createUser', () => {
    it('should create user with valid data', async () => { ... });
    it('should throw when email already exists', async () => { ... });
    it('should throw when email is invalid', async () => { ... });
  });
});
```
