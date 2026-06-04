# Using coding-discipline with Cursor

This project includes a **Cursor project rule** so the behavioral guidelines apply automatically when you work here.

## In this repository

1. Open the folder in Cursor.
2. The rule [`.cursor/rules/coding-discipline.mdc`](../../.cursor/rules/coding-discipline.mdc) is committed with `alwaysApply: true`, so you do not need extra installation steps.
3. In Cursor, you can confirm it under **Settings → Rules**, where `coding-discipline` should appear.

## Use the same guidelines in another project

**Cursor (recommended):** Copy `.cursor/rules/coding-discipline.mdc` into that project's `.cursor/rules/` directory (create the folders if needed).

**Other tools:** Copy [`CLAUDE.md`](CLAUDE.md) into that project instead (or merge its contents into your existing instructions).

## Optional: personal Agent Skills

Copy [`SKILL.md`](SKILL.md) into your `~/.cursor/skills/coding-discipline/` directory.

## For contributors

When you change the four principles, keep [`CLAUDE.md`](CLAUDE.md) and [`.cursor/rules/coding-discipline.mdc`](../../.cursor/rules/coding-discipline.mdc) in sync. Update [`SKILL.md`](SKILL.md) as well.
