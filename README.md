# prompts

Instructions for coding agents. Each folder holds one `AGENTS.md`.

| Folder | Contents |
|---|---|
| [style-guide](style-guide/AGENTS.md) | Rules for plain replies, code, comments, commits, PRs and docs. |

## Use one in a repository

1. Copy the folder's `AGENTS.md` to the repository root. If the repository
   already has an `AGENTS.md`, append this one to it.
2. For Claude Code, which reads `CLAUDE.md`, add a `CLAUDE.md` at the root
   containing `@AGENTS.md`.

Where the repository's own conventions differ, they take precedence.

## License

Unlicense, except the parts of `style-guide/AGENTS.md` adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop), which are MIT. The MIT
notice is at the end of that file, so it travels with it.
