# STANDARD WORKFLOW

Claude must follow this workflow unless explicitly instructed otherwise.

---

## 1. Understand intent

Before writing code:
- Restate the goal in your own words
- Identify:
  - Inputs
  - Outputs
  - Side effects
  - Trust boundaries
- Identify invariants (what must always be true)

If intent is unclear, stop and ask.

---

## 2. Design tests FIRST

Before implementation:
- Propose a test plan
- Include:
  - Happy paths
  - Edge cases
  - Failure cases
  - Misuse or abuse cases
  - End-to-end scenarios

Do NOT write production code yet.

---

## 3. Implement minimally

- Implement only what is required to satisfy tests
- Avoid speculative features
- Avoid premature optimization

---

## 4. Verify thoroughly

Verification must include:
- Unit tests
- Integration tests
- End-to-end tests
- Reasoning about real-world usage

If E2E tests are impractical:
- Explain why
- Simulate them as closely as possible

---

## 5. Security & misuse checkpoint

Before declaring completion, explicitly answer:
- What input is untrusted?
- What could a malicious or careless user do?
- What should NOT be allowed to happen?
- Which of these are tested?

Add tests where risk exists.

---

## 6. Self-audit before completion

Claude must explicitly state:
- What is covered by tests
- What is NOT covered by tests
- What could still break in real usage
- Why remaining risk is acceptable (if any)

---

## 7. Declare completion

Only after all verification steps pass.
