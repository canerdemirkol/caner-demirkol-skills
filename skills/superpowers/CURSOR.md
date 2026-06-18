# Using superpowers with Cursor

## In this repository

1. Open the folder in Cursor.
2. The rule [`.cursor/rules/superpowers.mdc`](../../.cursor/rules/superpowers.mdc) is committed with `alwaysApply: false` — it is an on-demand workflow, not a passive always-on guideline.
3. To activate it in a conversation, reference it directly: `@superpowers` or mention "use the superpowers workflow."
4. In Cursor Settings → Rules, `superpowers` should appear alongside `coding-discipline`.

## Use in another project

**Cursor (recommended):** Copy `.cursor/rules/superpowers.mdc` into that project's `.cursor/rules/` directory.

```bash
curl -o .cursor/rules/superpowers.mdc \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/.cursor/rules/superpowers.mdc
```

**Other tools:** Copy [`SKILL.md`](SKILL.md) into that project or merge it into your existing instructions file.

## coding-discipline vs superpowers in Cursor

| | `coding-discipline` | `superpowers` |
|---|---|---|
| `alwaysApply` | `true` — always loaded | `false` — invoked on demand |
| Style | Passive behavioral guidelines | Active development workflow |
| Best for | Everyday coding sessions | Features, complex bugs, production work |

Both rules can be active at the same time. `coding-discipline` sets behavioral defaults; `superpowers` provides the structured workflow when you start a task.

## For contributors

When you change the workflow content, keep [`SKILL.md`](SKILL.md) and [`.cursor/rules/superpowers.mdc`](../../.cursor/rules/superpowers.mdc) in sync.
