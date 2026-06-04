# CLAUDE.md

Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

## 5. Security by Default

**Treat every input as untrusted. Every code path as exploitable.**

- Validate and sanitize all inputs at system boundaries (user input, API responses, file reads).
- Never hardcode secrets, tokens, or credentials — not even in comments.
- Flag SQL queries, shell commands, and file paths that use unsanitized input.
- Security applies to all code, not just user-facing surfaces.

## 6. Dependency Minimalism

**Don't add a package for what 5 lines of code can do.**

Before adding a dependency:
- Can this be done with the standard library or existing dependencies?
- Is the package actively maintained? What is its CVE surface?
- If a package is justified, pin the version.

## 7. Algorithmic Complexity

**Flag complexity before it ships, not after it scales.**

- State the time/space complexity of non-trivial algorithms.
- Prefer O(n) over O(n²) when input size is unknown or unbounded.
- Flag N+1 queries, nested loops over large collections, and unbounded recursion.

## 8. Explicit Error Handling

**No silent failures. Errors must be handled or explicitly propagated.**

- Never swallow exceptions silently (empty catch blocks, bare `except:`).
- Either handle the error meaningfully or let it propagate to the caller.
- Log with context: what failed and what the inputs were.

## 9. Constants over Magic Values

**Named constants, not raw numbers or strings.**

- Replace magic numbers and strings with named constants.
- Place constants near the code that uses them, not in a global dump.
- Names should explain the *why*, not just the *what* (`MAX_RETRY_ATTEMPTS` not `THREE`).

---

**These guidelines are working if:** fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, clarifying questions come before implementation, and security/performance issues are caught before review.
