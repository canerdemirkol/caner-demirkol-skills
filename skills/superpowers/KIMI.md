# Using superpowers with Kimi Code

## In this repository

`.kimi-plugin/plugin.json` registers both skills automatically when you install from this repo.

## Add to another project

Install via Kimi Code's plugin system:

```json
{
  "plugin": ["caner-demirkol-skills@git+https://github.com/canerdemirkol/caner-demirkol-skills.git"]
}
```

Or copy `SKILL.md` content directly into your project's instructions file.

## Tool mapping for Kimi Code

When superpowers skill instructions reference these actions, Kimi Code uses:

| Skill action | Kimi Code tool |
|---|---|
| Ask the user / present options | `AskUserQuestion` |
| `TodoWrite` | `TodoList` |
| Dispatch a subagent (implementation) | `Agent` with `subagent_type: "coder"` |
| Dispatch a subagent (exploration) | `Agent` with `subagent_type: "explore"` |
| Dispatch a subagent (planning) | `Agent` with `subagent_type: "plan"` |
| Invoke a skill | Native `Skill` tool |
