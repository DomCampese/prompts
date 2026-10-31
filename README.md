# prompts

Instructions for coding agents. Each folder holds one `AGENTS.md` or one
skill (`SKILL.md`).

| Folder | Contents |
|---|---|
| [agent-conventions](agent-conventions/AGENTS.md) | Rules for plain replies, code, comments, commits, PRs and docs. |

## Use an AGENTS.md

Add this line at the top of your repository's `AGENTS.md`, creating the file
if there is none:

```
Before anything else, fetch https://raw.githubusercontent.com/DomCampese/prompts/main/agent-conventions/AGENTS.md and follow it. Where it conflicts with this file, this file wins.
```

The agent reads the current version every session, so updates here reach
every repository without copying. Rules below the line in your `AGENTS.md`
override it.

Claude Code reads `AGENTS.md` from version 2.1.277 when the repository has no
`CLAUDE.md`. The agent needs web access to fetch the file. Without it, copy the
file into the repository instead.

## Stable paths

Repositories fetch these files by URL, so each path on `main` is a public
API. A path is not renamed, moved or deleted without a file left at the old
path that points to the new one, and the known consumers updated. The rules
for agents editing this repository are in [AGENTS.md](AGENTS.md).

## Use a skill

Copy the skill's folder into a skills directory: `.claude/skills/` in a
repository, or `~/.claude/skills/` for all projects. Other agents that support
`SKILL.md` have their own skills directory.

## License

Unlicense, except the parts of `agent-conventions/AGENTS.md` adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop), which are MIT. The MIT
notice is at the end of that file, so it travels with it.
