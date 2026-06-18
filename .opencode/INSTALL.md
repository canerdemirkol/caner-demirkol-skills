# Installing caner-demirkol-skills for OpenCode

## Prerequisites

- [OpenCode.ai](https://opencode.ai) installed

## Installation

Add to the `plugin` array in your `opencode.json` (global or project-level):

```json
{
  "plugin": ["caner-demirkol-skills@git+https://github.com/canerdemirkol/caner-demirkol-skills.git"]
}
```

Restart OpenCode. Both skills (`coding-discipline` and `superpowers`) will be registered automatically.

## Usage

Use OpenCode's native `skill` tool:

```
use skill tool to list skills
use skill tool to load superpowers
use skill tool to load coding-discipline
```

## Skills

| Skill | When to use |
|-------|-------------|
| `coding-discipline` | Everyday coding — lightweight behavioral guidelines |
| `superpowers` | Features, complex bugs — full agentic workflow with TDD, planning, code review |
