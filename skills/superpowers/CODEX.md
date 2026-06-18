# Using superpowers with Codex

## In this repository

`.codex-plugin/plugin.json` registers both skills automatically when you install from this repo.

## Add to another project

Install via Codex's plugin system:

```json
{
  "plugin": ["caner-demirkol-skills@git+https://github.com/canerdemirkol/caner-demirkol-skills.git"]
}
```

Or copy `SKILL.md` content directly into your project's `AGENTS.md`:

```bash
curl -o AGENTS.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md
```

## Combining with coding-discipline

```bash
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/coding-discipline/SKILL.md > AGENTS.md
echo "" >> AGENTS.md
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md >> AGENTS.md
```
