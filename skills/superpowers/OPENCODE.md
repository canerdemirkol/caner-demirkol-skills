# Using superpowers with OpenCode

## In this repository

`.opencode/plugins/skills.js` and `.opencode/INSTALL.md` handle the integration.

## Add to another project

Add to your `opencode.json`:

```json
{
  "plugin": ["caner-demirkol-skills@git+https://github.com/canerdemirkol/caner-demirkol-skills.git"]
}
```

Restart OpenCode. Both skills are registered automatically.

## Usage

```
use skill tool to list skills
use skill tool to load superpowers
use skill tool to load coding-discipline
```

## Tool mapping for OpenCode

| Skill action | OpenCode tool |
|---|---|
| `TodoWrite` | `todowrite` |
| Dispatch a subagent | `task` with `subagent_type: "general"` |
| Invoke a skill | Native `skill` tool |
| Read a file | `read` |
| Create / edit / delete a file | `apply_patch` |
| Run a shell command | `bash` |
| Search file contents | `grep` |
| Find files by path | `glob` |
| Fetch a URL | `webfetch` |

See [`.opencode/INSTALL.md`](../../.opencode/INSTALL.md) for full install and troubleshooting steps.
