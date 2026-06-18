# GitHub Copilot Instructions

<!-- Source: skills/superpowers/COPILOT.md and skills/coding-discipline/SKILL.md — update both when content changes -->

This project includes two complementary skill sets. Apply whichever fits the current task:

---

## coding-discipline (lightweight, always-on)

Behavioral guidelines to reduce common LLM coding mistakes.

- **Think Before Coding** — State assumptions, surface trade-offs, ask when unclear, propose approach before implementing
- **Simplicity First** — Minimum code that solves the problem. No speculative features, no unnecessary abstractions
- **Surgical Changes** — Touch only what you must. Match existing style. Don't improve adjacent code
- **Goal-Driven Execution** — Transform tasks into verifiable goals. State a brief plan for multi-step work
- **Security by Default** — Validate all inputs at system boundaries. Never hardcode secrets
- **Dependency Minimalism** — Don't add a package for what 5 lines of code can do
- **Algorithmic Complexity** — Flag O(n²) and N+1 queries before they ship
- **Explicit Error Handling** — No silent failures. Handle or propagate; never swallow exceptions
- **Constants over Magic Values** — Named constants, not raw numbers or strings
- **Code Style** — English only. Descriptive names. Comments explain why, not what
- **Git Safety** — Only read-only git commands (`diff`, `log`, `status`, `show`, `blame`) without explicit instruction

---

## superpowers (structured, agentic workflow)

Use when starting a feature, fixing a complex bug, or when correctness matters more than speed.

**Lifecycle:** Brainstorm → Plan → Execute (with TDD) → Review → Finish

1. **Brainstorming** — HARD GATE: no code until design is approved. One clarifying question at a time. Propose 2–3 approaches with trade-offs.

2. **Writing Plans** — Break work into 2–5 minute tasks. Every task has exact commands, real code, no placeholders.

3. **Test-Driven Development** — Iron Law: no production code without a failing test first. RED → GREEN → REFACTOR. If you wrote code before tests: delete it, start over.

4. **Systematic Debugging** — NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST. Four phases: Investigate → Analyze → Hypothesize → Fix.

5. **Code Review** — Request after each major task and before merging. When receiving: read fully, verify against codebase, respond technically.

6. **Finishing a Branch** — Verify tests pass first. Present exactly 4 options: merge locally / create PR / keep as-is / discard.

7. **Verification** — Evidence before claims, always. Run the command, examine the full output, then make the claim.

---

Full documentation: https://github.com/canerdemirkol/caner-demirkol-skills
