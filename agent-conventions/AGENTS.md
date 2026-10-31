# Agent conventions

Prefer clear, easy-to-understand signal over fluff. The other rules here
follow from this one. When none of them covers a case, apply this one.

These rules apply to any agent working in the repository: code, comments,
commit messages, PR descriptions, docs and replies. Where the repository's own
conventions differ, follow the repository.

## Replies

- Answer first. Then give only the detail needed to act on it.
- Report what was done and how it was checked. If something failed or was
  skipped, say so.
- Give one recommendation. Do not list options you will not pursue.
- Do not repeat the request back or restate what the diff already shows.
- No praise of the question or idea. No closing offer of more help. Ask a
  question only when you need a decision to continue.
- Do not announce what you are about to do ("Let me walk you through...",
  "Here's what I found:"). Do it.
- No reassurance ("And that's okay"), softening or hand-holding.

## Code

- Do not reformat code you are not otherwise changing. Mixing format changes
  with code changes makes the code changes harder to review.
- A name says what the thing is, with units where it helps (`timeoutMs`,
  `widthPx`). Short names are fine when they are local and conventional in
  that code.
- Each function does one thing. If a block needs a comment to say what it
  does, move it into a function with that name.
- No dead code, no commented-out code, no unused parameters kept "for later".
- Give a meaningful number a named constant. A number used in two places gets
  one definition that both read.
- Prefer a table of per-case values to a chain of `if`s.
- Follow the project's existing layering and conventions.
- If a change is meant to leave behavior the same, prove it with the cheapest
  check that works: identical output from the same inputs, identical build
  output for code that only moved, before and after screenshots, then the test
  suite. Say which checks you ran in the commit message.

## Comments

- Assume the reader understands code. Do not explain what code does.
- Comment only where something is non-obvious, and say why. Non-obvious
  includes domain knowledge: formulas, protocol rules, values defined by a
  technical standard such as an RFC or a file format. For example:
  `// Safari ignores the CSS value, so set the meta tag directly.`
- Warn about a footgun only when an edit would break something the code does
  not show. This should be rare:
  `// Must match PANEL_HALF, or the highlight is the wrong size.`
- Workaround notes are fine. Say what is being worked around, and link the
  upstream bug report (browser, library, OS) if there is one, so the workaround can be removed once it is
  fixed:
  `// Works around Safari not firing resize on rotation: https://bugs.webkit.org/...`
- Doc comments (`@param`, `@returns`) only on code that is called from many
  places or by other teams, such as a shared utility or a library API. Not on
  code with one or two callers.
- No TODOs, no section dividers. Report known gaps in the PR description or
  an issue.
- No ticket numbers, acceptance criteria or requirement IDs. Those belong in
  the commit message or PR.
- One line, rarely more than two. Match the file's existing case and
  punctuation.
- Put history and reasoning that needs more space in the commit message.
- No first person, no "we", no addressing the reader.
- Jokes are rare: most codebases should have a handful at most. When one
  fits, it is appreciated. It adds to a fact the comment already states:
  - A yes or no to the question the reader will ask, with the reason:
    `// No, this can't be a Set. Order matters for the undo stack.`
  - Understatement after a fact:
    `// The cache is eventually consistent. Eventually.`
  - A well-known reference that explains the idea:
    `// Schrödinger's flag: unset until the first read, so check before using it.`
- In names, a metaphor is fine if it still says what the thing does
  (`Janitor` for a class that deletes temp files). No slang, memes or
  references in names (`yeet`, `bobbyTables`, `theAnswer`).
- Snark at vendors, browsers and specs is fine when it comes with the
  behavior:
  `// The vendor's docs are wrong. In practice it returns 404 for an empty list.`
  "Thanks, IE" alone says nothing. No snark at people, including
  coworkers and past authors of the code.
- No memes ("one does not simply").
- A joke never replaces the reason. No "here be dragons", "it works, don't
  ask", or "don't touch this" without saying why.

## Commits, PRs and docs

- Commit subject: imperative, under 72 characters, naming the area:
  `auth: split token refresh out of the client`. The body says what changed,
  why, and how it was verified.
- A PR says what changed, how it was verified and what to check. It does not
  say why the change is exciting.
- Docs lead each section with the rule or the fact. Use a table to compare
  things. Give a measured number with how it was measured. Record a failure
  mode the code does not make obvious as: rule, symptom, reason.

## Plain language

- Write full sentences a newcomer can parse: subject, verb, condition,
  result. Do not drop articles and lean on an unusual verb to sound sharp.
  "B at a ledge lets you mantle" becomes "Press B while facing a ledge to
  climb onto it."
- Name the actor. Code, data and decisions do not act on their own. "The
  retry loop hides the error", not "the error gets swallowed".
- Prefer active voice. Passive is fine when the actor is unknown or does not
  matter.
- Be specific. "The implications are significant" says nothing. Name the
  implication. Use "always", "never" and "every" only when they are true.
- Real engineering terms are fine: *race condition, idempotent, footgun, blast
  radius, happy path*. Do not invent a name for a problem ("the dual-source
  problem") and then use it as if the reader knows it. Describe the problem.
- No figurative or atmospheric language. No selling.

## Patterns to cut

Each entry: the pattern, then a fix.

**Filler words.** *very, really, just, simply, actually, basically,
genuinely, honestly, literally, crucially, importantly, essentially,
fundamentally, quite, arguably.* Delete them.

**Throat-clearing.** *Here's the thing, it turns out, the truth is, the
reality is, let me be clear, great question, at its core, when it comes to,
at the end of the day.* Start with the content.

**Signposting.** *Note that, it's worth noting, keep in mind, the key
insight, in other words, as we'll see.* Delete them.

**Emphasis crutches.** *Full stop, let that sink in, make no mistake, this
matters because.* Delete them.

**Business jargon.**

| Avoid | Use |
|---|---|
| leverage, utilize | use |
| facilitate | help, let |
| navigate, unpack | handle, explain |
| deep dive | look at |
| robust | the property: "handles X", "tested against Y" |
| seamless | what no longer needs a manual step |
| the ask, the unlock, the win | the request, what it enables, the result |
| ensure that | so, to |

**"Not X, but Y".** State Y. A plain negative is fine: "The cache does not
persist across restarts."

| Before | After |
|---|---|
| "X isn't the problem. Y is." | "The problem is Y." |
| "Not because X. Because Y." | "Because Y." |
| "Not a X. Not a Y. A Z." | "Z." |
| "not just X but also Y" | "X and Y." |

**Slick lines.** Mirrored sentences, clever comparisons and lines built to be
quoted. Write the fact they hint at.

| Before | After |
|---|---|
| "Cheap to add, expensive to remove." | "Removing it later means migrating every stored record." |
| "A cache bug wearing a network costume." | "The timeout comes from a stale cache entry." |
| "That 'usually' is doing a lot of work." | "It fails when the file is over 2 MB." |
| "Retries paper over the 503s." | "The client retries 503 responses, so they never reach the logs." |
| "A style-only diff across untouched code hides the change that matters." | "Mixing format changes with code changes makes the code changes harder to review." |

**Pain verbs.** *Bites, stings, burns, trips you up.* State the failure and
when it happens. "This will sting on large repos" becomes "Clones over 2 GB
time out."

**Teasers.** *The catch:, the fix:, the upshot:, short version:, there's a
catch.* Give the catch or the fix.

**Wry asides.** *(ask me how I know), which is a polite way of saying,
spoiler:, for some definition of.* Delete them. "Tests pass, for some
definition of pass" becomes "Tests pass because three are skipped."

**Drama adverbs.** *Quietly, silently, sneakily.* Say what the code does.
"Silently swallows the error" becomes "Catches the error and returns `[]`
without logging."

**Sincerity markers.** *The honest answer is, to be candid, to be fair.*
Give the answer.

**Rhetorical setups.** *What if...?, think about it:, here's what I mean:*,
a question followed by its own answer. Make the point.

**Fragments for drama.** "Speed. Quality. Cost. That's it." Write one
sentence.

**Lists of three for rhythm.** Use the number of items there are.

**Em dashes.** Use a full stop, a comma or a colon.

**Emphasis in code comments.** No bold or capitals for emphasis.

## Before and after

> Before: "Great question! Here's the thing: the build isn't failing because
> of the code. It's failing because of the cache. Let me walk you through it."
>
> After: "The build fails because the cache holds a stale lockfile. Clearing
> `~/.cache/pnpm` fixes it."

> Before: "I've implemented a robust, comprehensive solution that seamlessly
> handles all edge cases. Let me know if you'd like any changes!"
>
> After: "Added retry with backoff to `fetchUser`. Tested against a 503 and a
> timeout; both succeed on the second attempt. Not tested: rate-limit
> responses."

## Check before sending

- Does the first sentence answer the question or state the result?
- Any pattern from the cut list? Fix it.
- Any line that sounds clever? Rewrite it as the plain fact.
- Any term you made up? Describe the thing instead.
- Anything that can be deleted without losing information? Delete it.

## License

Parts of this file are adapted from
[stop-slop](https://github.com/hardikpandya/stop-slop):

Copyright (c) 2025 Hardik Pandya

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
