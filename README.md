# caner-demirkol-skills

A collection of AI coding skills and behavioral guidelines. Two approaches, one plugin — works with Claude Code, Cursor, GitHub Copilot, Gemini CLI, and Codex.

## Skills

| Skill | Style | Best for |
|-------|-------|----------|
| [coding-discipline](./skills/coding-discipline/) | Passive, always-on guidelines | Quick tasks, everyday coding, guardrails without ceremony |
| [superpowers](./skills/superpowers/) | Active, agentic workflow | Features, complex bugs, production-quality development |

### Which one should I use?

**`coding-discipline`** — Lightweight behavioral rules. No ceremony.
Think before coding, simplicity first, surgical changes, security defaults, git safety.
Use when you just want the model to behave better.

**`superpowers`** — Full development lifecycle. Structured and review-gated.
Brainstorm → Plan → TDD → Subagent execution → Code review → Branch finish.
Every claim verified. Every task reviewed. No code before tests.
Based on [obra/superpowers](https://github.com/obra/superpowers) (MIT).

> You can activate both at the same time. `coding-discipline` sets behavioral defaults; `superpowers` provides the workflow to invoke when you start a task.

---

## Using Both Skills Together

### Yöntem 1: Plugin (en kolay — tüm projelerde çalışır)

```
/plugin marketplace add canerdemirkol/caner-demirkol-skills
/plugin install caner-demirkol-skills@caner-demirkol-skills
```

Kurulduktan sonra konuşma başında her ikisini birden aktif et:

```
Use both the coding-discipline and superpowers skills
```

### Yöntem 2: CLAUDE.md (proje bazlı, kalıcı)

Projenin root'unda ikisini tek dosyaya birleştir:

```bash
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/coding-discipline/SKILL.md > CLAUDE.md
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md >> CLAUDE.md
```

`CLAUDE.md` her session başında otomatik yüklenir — bir şey söylemene gerek kalmaz.

### Pratikte nasıl birlikte çalışır?

```
Sen: "Login feature ekleyelim"

Claude (coding-discipline aktif):
  → Önce soru sorar, varsayım yapmaz
  → Basit tutmayı önerir

Claude (superpowers aktif):
  → "Önce brainstorming yapayım, tasarım onaylanmadan kod yazmam"
  → Plan yazar: 2-5 dakikalık tasklar
  → Her task için önce test yazar (TDD)
  → Her major değişiklik sonrası code review ister
```

`coding-discipline` pasif filtre gibi çalışır — her zaman arka planda aktif.
`superpowers` aktif workflow'dur — ciddi bir iş yaparken devreye girer.

İkisi çatışmaz, birbirini tamamlar.

---

## Platform Support

| Platform | Plugin file | Skill docs |
|----------|-------------|------------|
| **Claude Code** | `.claude-plugin/` | [SKILL.md](./skills/superpowers/SKILL.md) |
| **Cursor** | `.cursor-plugin/` + `.cursor/rules/` | [CURSOR.md](./skills/superpowers/CURSOR.md) |
| **Kimi Code** | `.kimi-plugin/` | [KIMI.md](./skills/superpowers/KIMI.md) |
| **Codex** | `.codex-plugin/` | [CODEX.md](./skills/superpowers/CODEX.md) |
| **OpenCode** | `.opencode/plugins/` | [OPENCODE.md](./skills/superpowers/OPENCODE.md) |
| **GitHub Copilot** | `.github/copilot-instructions.md` | [COPILOT.md](./skills/superpowers/COPILOT.md) |
| **Gemini CLI** | `GEMINI.md` | [GEMINI.md](./skills/superpowers/GEMINI.md) |
| **Codex / agents** | `AGENTS.md` | [AGENTS.md](./skills/superpowers/AGENTS.md) |

---

## Claude Code

### Install via plugin marketplace

```
/plugin marketplace add canerdemirkol/caner-demirkol-skills
/plugin install caner-demirkol-skills@caner-demirkol-skills
```

Both skills are included. After installing, reference them by name in any conversation:
- `"Use the coding-discipline skill"` — loads behavioral guidelines
- `"Use the superpowers skill"` — loads the full development workflow

### Install via CLAUDE.md (per-project)

```bash
# coding-discipline
curl -o CLAUDE.md https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/coding-discipline/SKILL.md

# superpowers
curl -o CLAUDE.md https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/skills/superpowers/SKILL.md
```

---

## Cursor

### Install via Cursor plugin

Add `.cursor-plugin/plugin.json` is included — Cursor will discover both skills automatically when you open this folder.

### Install rules in another project

```bash
# coding-discipline (alwaysApply: true)
curl -o .cursor/rules/coding-discipline.mdc \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/.cursor/rules/coding-discipline.mdc

# superpowers (alwaysApply: false — invoke on demand)
curl -o .cursor/rules/superpowers.mdc \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/.cursor/rules/superpowers.mdc
```

Confirm under **Cursor Settings → Rules** that both rules appear.

---

## GitHub Copilot

Copy `.github/copilot-instructions.md` into your project:

```bash
mkdir -p .github
curl -o .github/copilot-instructions.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/.github/copilot-instructions.md
```

Both skills are included in one file. Copilot will use these instructions automatically in VS Code and github.com.

---

## Gemini CLI

`GEMINI.md` is already in the repo root — Gemini CLI picks it up automatically when you run it from this directory. For another project:

```bash
curl -o GEMINI.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/GEMINI.md
```

---

## Codex / Other Agents

`AGENTS.md` is in the repo root. For another project:

```bash
curl -o AGENTS.md \
  https://raw.githubusercontent.com/canerdemirkol/caner-demirkol-skills/main/AGENTS.md
```

---

## License

MIT
