# TESTING & VERIFICATION RULES

This file defines what “working” actually means.

---

## Definition of "working"

Code is considered working ONLY if:

1. Unit tests pass
2. Integration tests pass
3. End-to-end behavior is verified
4. Manual usage would not reveal obvious failures

Passing unit tests alone is NOT sufficient.

---

## Test layers (all required)

### 1. Unit tests

Purpose:
- Validate pure logic
- Validate edge cases
- Provide fast feedback

Rules:
- No reliance on internal structure
- No mocking the unit under test
- Tests must fail if logic changes incorrectly

---

### 2. Integration tests

Purpose:
- Validate interaction between components
- Validate real data flow and boundaries

Rules:
- Prefer real modules over mocks
- Validate assumptions between layers

Examples:
- API + persistence
- Service + external adapter
- Multiple internal modules together

---

### 3. End-to-end (E2E) tests (REQUIRED)

Purpose:
- Validate behavior as a real user would experience it

Rules:
- Exercise the system from entry point to final output
- Simulate real usage
- Fail if deployment-time or wiring issues exist

Examples:
- HTTP request → response
- CLI command → output
- UI action → state change

If E2E tests are skipped:
- Explain explicitly why
- Describe what could break as a result

---

## Negative & adversarial testing (MANDATORY)

For any externally accessible behavior, tests must include:
- Invalid inputs
- Unauthorized attempts
- Out-of-order actions
- Duplicate or replayed actions
- Boundary violations

If a test passes but real usage fails:
- The test is wrong
- Fix the test first

---

## Bug discipline

When a bug is found:
1. Write a test that reproduces the bug
2. Verify the test fails
3. Fix the code
4. Verify all tests pass

Never fix bugs without tests.

---

## Final mandatory question

Before declaring completion, Claude must answer:

> “If I ran this manually or in production, what might still go wrong?”

If the answer is “nothing obvious”, explain why.
