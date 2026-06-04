# caner-demirkol-skills

A collection of Claude Code skills and behavioral guidelines.

## Skills

| Skill | Description | Docs |
|-------|-------------|------|
| [coding-discipline](./skills/coding-discipline/) | Behavioral guidelines to reduce common LLM coding mistakes | [README](./skills/coding-discipline/CLAUDE.md) · [Examples](./skills/coding-discipline/EXAMPLES.md) · [Cursor](./skills/coding-discipline/CURSOR.md) |

## Install (Claude Code Plugin)

```
/plugin marketplace add canerdemirkol/caner-demirkol-skills
/plugin install caner-demirkol-skills@caner-demirkol-skills
```

## Install (per-project CLAUDE.md)

Copy the skill's `CLAUDE.md` into your project:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/coding-discipline/CLAUDE.md
```

## Install (Cursor)

Copy the relevant `.mdc` file into your project's `.cursor/rules/` directory.

## License

MIT
