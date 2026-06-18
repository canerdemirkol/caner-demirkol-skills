# Using superpowers with GitHub Copilot

## In this repository

`.github/copilot-instructions.md` at the repo root loads both skills automatically for Copilot in VS Code and github.com.

## Add to another project

GitHub Copilot requires inline content — it cannot import files with `@`. Copy the skill content directly into `.github/copilot-instructions.md`:

```bash
mkdir -p .github
curl -o .github/copilot-instructions.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md
```

## Combining with coding-discipline

Concatenate both into a single `.github/copilot-instructions.md`:

```bash
mkdir -p .github
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/coding-discipline/SKILL.md > .github/copilot-instructions.md
echo "" >> .github/copilot-instructions.md
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md >> .github/copilot-instructions.md
```

## Note

When this skill's content changes, update `.github/copilot-instructions.md` manually — Copilot has no live import mechanism.
