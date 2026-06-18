---
name: superpowers
description: Use when you want a structured, agentic development lifecycle — brainstorming before coding, writing plans, test-driven development, systematic debugging, code review, and branch completion. Replaces ad-hoc problem-solving with composable, ordered workflows.
license: MIT
source: https://github.com/obra/superpowers
---

# Superpowers: Agentic Development Framework

Systematic software development through composable, ordered workflows.

**Core philosophy:** Design first. Test first. Review often. Verify before claiming done.

**Tradeoff:** These workflows add ceremony. For trivial tasks, use `coding-discipline` instead.

---

## The Development Lifecycle

```
Brainstorm → Plan → Execute (with TDD) → Review → Finish
```

Always start with brainstorming for non-trivial work. Skip to planning only for clearly-scoped tasks.

---

## 1. Brainstorming

**HARD GATE: Do NOT write any code until the design is approved.**

1. Explore project context — files, docs, recent commits
2. Ask clarifying questions — one at a time
3. Propose 2–3 approaches with trade-offs and a recommendation
4. Present design in sections; get approval before moving forward
5. Write approved design to `docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md`
6. Self-review spec for placeholders, contradictions, and ambiguity
7. Wait for user approval before invoking `writing-plans`

Applies to all tasks, including "simple" ones. Unexamined assumptions waste more time than a short brainstorm.

---

## 2. Writing Plans

Break the approved design into 2–5 minute, independently-reviewable tasks.

Each task must include:
- Which files change and why
- Exact commands to run
- Expected output
- Real code — no placeholders

Save plans to `docs/superpowers/plans/YYYY-MM-DD-<feature>.md`

After writing, offer two execution paths:
1. **Subagent-driven** (recommended) — fresh subagent per task with review gates
2. **Inline execution** — batch execution with checkpoints

---

## 3. Test-Driven Development

**Iron Law: No production code without a failing test first.**

### RED → GREEN → REFACTOR

1. **RED** — Write a minimal failing test
2. **GREEN** — Write the simplest code to make it pass
3. **REFACTOR** — Clean up while keeping tests green

If code was written before tests: **delete the code. Start over.**

**Common rationalizations to reject:**

| Excuse | Reality |
|--------|---------|
| "Too simple to test" | Simple code breaks. A test takes 30 seconds. |
| "I'll test after" | Tests passing immediately prove nothing. |
| "I manually tested it" | Manual testing doesn't catch regressions. |
| "Tests after achieve the same goal" | Tests-after verify what code does. Tests-first verify what it should do. |

**Verification checklist:**
- Watched each test fail before implementing
- Test failed for the expected reason (missing feature, not a typo)
- All tests pass with clean output
- Tests use real code, not pure mocks

---

## 4. Systematic Debugging

**Rule: NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST.**

Symptom fixes mask problems and lead to repeated failures.

### Four Phases

**Phase 1 — Investigate**
Read error messages carefully. Reproduce the issue consistently. Review recent changes. Gather diagnostic evidence layer by layer.

**Phase 2 — Analyze**
Find a working example. Compare implementations completely. Identify the difference. Understand dependencies.

**Phase 3 — Hypothesize**
Form a specific theory. Test with the minimal possible change. Adjust based on results.

**Phase 4 — Fix**
Write a failing test that reproduces the bug first. Implement the root cause fix. Verify no new problems introduced.

**Escalation:** If 3+ fix attempts fail, question whether the architecture itself is flawed — stop patching symptoms.

**Red flags — return to Phase 1:**
- "Quick fix for now"
- "Just try changing X"
- "I don't fully understand but this might work"

---

## 5. Subagent-Driven Development

For executing multi-task plans with quality gates.

1. **Pre-flight** — Review the plan once for contradictions before Task 1
2. **Per-task cycle:**
   - Dispatch implementer subagent with focused context
   - Receive delivered work + diff
   - Dispatch task reviewer (spec compliance + code quality — both required)
   - For Critical/Important issues: dispatch fix subagent, then re-review
3. **Final review** — Run whole-branch code review after all tasks complete
4. **Progress ledger** — Maintain a ledger file to survive context compaction

Key principle: Fresh subagent per task + task review + final review = high quality, fast iteration.

Never skip task review or accept incomplete verdicts.

---

## 6. Code Review

**Request reviews at:**
- After each task in subagent-driven development
- After completing a major feature
- Before merging to main

**When requesting:** Provide the reviewer with commit range, description, and requirements reference — not your full session history.

**When receiving:**

1. **READ** — complete feedback without reacting
2. **UNDERSTAND** — restate the requirement in your own words
3. **VERIFY** — check against actual codebase
4. **EVALUATE** — assess technical soundness for this specific context
5. **RESPOND** — technical acknowledgment or reasoned pushback
6. **IMPLEMENT** — one item at a time, testing each change

Avoid performative agreement ("You're absolutely right!"). State fixes factually: "Fixed. [Description]."

Push back when suggestions lack context, violate YAGNI, or conflict with established architecture.

---

## 7. Git Worktrees

Use isolated workspaces for every development branch.

1. Check if already in an isolated workspace before creating one
2. Prefer native worktree tools over manual `git worktree add`
3. Verify directory is git-ignored before creating it
4. Run project setup (install, build) in new worktree
5. Verify clean test baseline before starting — report failures and ask before proceeding

---

## 8. Finishing a Development Branch

Before offering options, verify tests pass. If they fail: stop, fix first.

**Present exactly these 4 options:**

```
Implementation complete. What would you like to do?

1. Merge back to <base-branch> locally
2. Push and create a Pull Request
3. Keep the branch as-is (I'll handle it later)
4. Discard this work
```

Never proceed with a merge or PR if tests are failing.
Never delete work without typed confirmation for Option 4.
Only clean up worktrees for Options 1 and 4.

---

## 9. Verification Before Completion

**Rule: Evidence before claims, always.**

Before asserting work is "complete", "fixed", or "passing":

1. Identify the exact command that validates the assertion
2. Run it — fresh, not cached
3. Examine the full output and exit code
4. Confirm results match the claim
5. Only then make the claim

Tentative language ("should work", "probably passes") signals unverified work.

---

## Skill Priority

These workflows take precedence over default behavior.
User instructions always override skill requirements.

When in doubt whether a skill applies: invoke it. A 1% chance of relevance is enough.
