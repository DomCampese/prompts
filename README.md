# prompts

Instructions for coding agents. Each folder is one entry and works with any
agent that reads `AGENTS.md`. Claude Code and other tools that read
`SKILL.md` can also load it as a skill.

| Entry | What it does |
|---|---|
| [plain-writing](plain-writing/) | Plain, brief code, comments, commits, PRs, docs and replies. |

## Use an entry in a repository

Using `plain-writing` as the example:

1. Copy `writing.md` and `patterns.md` into the repository's `docs/`.
2. Copy `AGENTS.md` to the repository root as is. If the repository already
   has an `AGENTS.md`, paste this one's contents into it instead. It contains
   the core rules and points to `docs/writing.md`.
3. For Claude Code, add a `CLAUDE.md` containing:

   ```
   @AGENTS.md
   @docs/writing.md
   ```

   `@` inlines the file at load time. Other tools follow the link in
   `AGENTS.md` instead, so the core rules are written out there in case the
   link is not read.

## Install as a skill

Copy the folder into a skills directory:

```sh
git clone https://github.com/DomCampese/prompts
cp -r prompts/plain-writing ~/.claude/skills/          # all projects
cp -r prompts/plain-writing your-repo/.claude/skills/  # one repository
```

A skill loads only when the agent decides a task matches its description.
For rules that should always apply, use the `AGENTS.md` route above.

## Licence

Unlicense, except where an entry's `NOTICE` says otherwise.
`plain-writing` includes material from
[stop-slop](https://github.com/hardikpandya/stop-slop) (MIT).
