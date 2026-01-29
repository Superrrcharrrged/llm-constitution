# LLM Constitution

This repository defines the canonical rules for how Claude must design,
test, implement, and validate code.

The goals of this ruleset are:

- Prevent false confidence from passing tests
- Enforce thorough verification (unit, integration, E2E)
- Reduce bugs discovered only during manual testing
- Encourage explicit reasoning about correctness and risk
- Maintain velocity without sacrificing safety

These rules are intended to be:
- Vendored into projects (e.g. `.llm/`)
- Auto-loaded via `claude.md` when using Claude Projects
- Explicitly authoritative over default model behavior
