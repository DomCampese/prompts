# prompts

Instructions for coding agents. Each folder holds one `AGENTS.md` or one
skill (`SKILL.md`).

| Folder | Contents |
|---|---|
| [agent-conventions](agent-conventions/AGENTS.md) | Rules for plain replies, code, comments, commits, PRs and docs. |

## Use an AGENTS.md

1. Copy the folder's `AGENTS.md` to the repository root. If the repository
   already has an `AGENTS.md`, append this one to it.
2. For Claude Code, which reads `CLAUDE.md`, add a `CLAUDE.md` at the root
   containing `@AGENTS.md`.

Where the repository's own conventions differ, they take precedence.

## Use a skill

Copy the skill's folder into a skills directory: `.claude/skills/` in a
repository, or `~/.claude/skills/` for all projects. Other agents that support
`SKILL.md` have their own skills directory.

## License

Unlicense, except the parts of `agent-conventions/AGENTS.md` adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop), which are MIT. The MIT
notice is at the end of that file, so it travels with it.
