# prompts

Instructions for coding agents. Each folder holds one `AGENTS.md` or one
skill (`SKILL.md`).

| Folder | Contents |
|---|---|
| [agent-conventions](agent-conventions/AGENTS.md) | Rules for plain replies, code, comments, commits, PRs and docs. |

## Use an AGENTS.md

Install it once in your agent harness, so it applies to every project, or
copy it into a repository, so everyone working there gets it. A repository's
own conventions take precedence where they differ.

### Option 1: your harness

Add the file to your harness's global instructions. Keeping a clone of this
repository and importing or linking the file from it means `git pull` updates
it.

| Harness | Global instructions | Docs |
|---|---|---|
| Claude Code | `~/.claude/CLAUDE.md` | [Memory](https://code.claude.com/docs/en/memory) |
| Codex | `~/.codex/AGENTS.md` | [AGENTS.md](https://developers.openai.com/codex/guides/agents-md) |
| Gemini CLI | `~/.gemini/GEMINI.md` | [GEMINI.md](https://geminicli.com/docs/cli/gemini-md) |
| Cursor | User Rules | [Rules](https://cursor.com/docs/context/rules) |

### Option 2: a repository

Use this when collaborators' agents should follow the conventions too.

1. Copy the folder's `AGENTS.md` to the repository root. If the repository
   already has an `AGENTS.md`, append this one to it.
2. For Claude Code, which reads `CLAUDE.md`, add a `CLAUDE.md` at the root
   containing `@AGENTS.md`.

## Use a skill

Copy the skill's folder into a skills directory: `.claude/skills/` in a
repository, or `~/.claude/skills/` for all projects. Other agents that support
`SKILL.md` have their own skills directory.

## License

Unlicense, except the parts of `agent-conventions/AGENTS.md` adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop), which are MIT. The MIT
notice is at the end of that file, so it travels with it.
