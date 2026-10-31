# prompts

Instructions for coding agents. Each folder holds one `AGENTS.md` or one
skill (`SKILL.md`).

| Folder | Contents |
|---|---|
| [agent-conventions](agent-conventions/AGENTS.md) | Rules for plain replies, code, comments, commits, PRs and docs. |

## Use an AGENTS.md

Add this line at the top of your repository's `AGENTS.md` or `CLAUDE.md`, or
of your harness's global instructions file:

```
Before anything else, fetch https://raw.githubusercontent.com/DomCampese/prompts/main/agent-conventions/AGENTS.md and follow it. Where it conflicts with this file, this file wins.
```

The agent reads the current version every session, so updates here reach
every repository without copying.

The agent needs web access, and has to act on the line. If it cannot fetch,
copy the file into the repository instead.

| Harness | Global instructions | Docs |
|---|---|---|
| Claude Code | `~/.claude/CLAUDE.md` | [Memory](https://code.claude.com/docs/en/memory) |
| Codex | `~/.codex/AGENTS.md` | [AGENTS.md](https://developers.openai.com/codex/guides/agents-md) |
| Gemini CLI | `~/.gemini/GEMINI.md` | [GEMINI.md](https://geminicli.com/docs/cli/gemini-md) |
| Cursor | User Rules | [Rules](https://cursor.com/docs/context/rules) |

## Use a skill

Copy the skill's folder into a skills directory: `.claude/skills/` in a
repository, or `~/.claude/skills/` for all projects. Other agents that support
`SKILL.md` have their own skills directory.

## License

Unlicense, except the parts of `agent-conventions/AGENTS.md` adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop), which are MIT. The MIT
notice is at the end of that file, so it travels with it.
