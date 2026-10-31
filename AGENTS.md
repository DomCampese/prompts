# prompts

Other repositories fetch files from this one by URL, for example
`https://raw.githubusercontent.com/DomCampese/prompts/main/agent-conventions/AGENTS.md`.
Each file path on `main`, and the `main` branch name, is a public API.

- Do not rename, move or delete a fetched file without saying so to the user
  first.
- If a path has to change, leave a file at the old path that tells the agent
  to fetch the new one, and update the fetch line in each known consumer.
- A change to a file's content reaches every consumer on its next session.
  Say in the commit message what behavior changes for them.

Known consumers: DomCampese/backrooms-game, DomCampese/portfolio.
