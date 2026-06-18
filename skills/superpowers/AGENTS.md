# Using superpowers with Codex and other agents

## In this repository

`AGENTS.md` at the repo root loads this skill automatically for tools that read it (Codex, OpenAI Agents, etc.).

## Add to another project

Create an `AGENTS.md` in your project root:

```
@./skills/superpowers/SKILL.md
```

Or copy the skill content directly:

```bash
curl -o AGENTS.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md
```

## Combining with coding-discipline

```
@./skills/coding-discipline/SKILL.md
@./skills/superpowers/SKILL.md
```
