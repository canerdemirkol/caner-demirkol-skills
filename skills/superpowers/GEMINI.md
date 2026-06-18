# Using superpowers with Gemini CLI

## In this repository

`GEMINI.md` at the repo root loads this skill automatically when you run Gemini CLI from this directory.

## Add to another project

Create a `GEMINI.md` in your project root with an `@` import:

```
@./skills/superpowers/SKILL.md
```

Or copy the skill content directly:

```bash
curl -o GEMINI.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md
```

## Combining with coding-discipline

To use both skills in the same project:

```
@./skills/coding-discipline/SKILL.md
@./skills/superpowers/SKILL.md
```
