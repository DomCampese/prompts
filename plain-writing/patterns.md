# Patterns to cut

Fuller lists for the rules in SKILL.md. Adapted in part from
[stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya
(MIT).

## Throat-clearing openers

State the content without them.

- "Here's the thing:", "Here's what/why/how..."
- "The truth is", "The uncomfortable truth is", "The reality is"
- "It turns out"
- "The real X is"
- "Let me be clear", "I'll be honest"
- "Great question", "You're right to ask"
- "At its core", "When it comes to", "At the end of the day"
- "In today's X", "In a world where"

## Emphasis crutches

- "Full stop." / "Period."
- "Let that sink in."
- "Make no mistake"
- "This matters because", "Here's why that matters"

## Meta-commentary

- "Let me walk you through...", "I want to explore..."
- "In this section, we'll...", "As we'll see..."
- "The rest of this explains..."
- "Hint:", "Spoiler:", "Plot twist:"
- "You already know this, but"
- "X is a feature, not a bug"

## Telling instead of showing

- "This is hard", "This actually matters"
- "This is what X looks like"
- "The reasons are structural", "The implications are significant",
  "The stakes are high"

Replace with the specific reason, implication or stake, or delete.

## Jargon

| Avoid | Use |
|---|---|
| leverage, utilize | use |
| facilitate | help, let |
| navigate (a problem) | handle |
| unpack | explain |
| landscape | field, situation |
| deep dive | look at, analysis |
| lean into | accept |
| double down | commit to |
| moving forward | next, from now on |
| circle back | return to |
| robust | name the property: handles X, tested against Y |
| seamless | name what no longer needs a manual step |

## Binary contrasts

| Pattern | Fix |
|---|---|
| "Not because X. Because Y." | "Because Y." |
| "X isn't the problem. Y is." | "The problem is Y." |
| "The answer isn't X. It's Y." | "Y." |
| "It feels like X. It's actually Y." | "It is Y." |
| "not just X but also Y" | "X and Y." |
| "stops being X and starts being Y" | "becomes Y" or say what changed |

## Negative listing and fragments

- "Not a X. Not a Y. A Z." → state Z.
- "[Noun]. That's it. That's the [thing]." → one sentence.
- "X. And Y. And Z." → one sentence.

## Rhetorical setups

- "What if...?"
- "Think about it:"
- "Here's what I mean:"
- "And that's okay."
- A question followed by its own answer.

## False agency

Inanimate things do not act. Name the actor.

| Pattern | Fix |
|---|---|
| "the data tells us" | "the logs show" / "I read the logs and found" |
| "the decision emerges" | "you decide" / "the team decided" |
| "the bug crept in" | "commit abc123 introduced the bug" |
| "the codebase wants" | say what change would make it simpler |

## Passive voice

| Pattern | Fix |
|---|---|
| "Mistakes were made" | Say who made them |
| "It is believed that" | Say who believes it |
| "The file was updated" | "I updated the file" (in a reply) |

## Pain verbs

Problems do not bite, sting or burn. State the failure and the condition.

| Pattern | Fix |
|---|---|
| "Here's the part that bites" | "This fails when..." |
| "This will sting on large repos" | "Clones over 2 GB time out." |
| "We got burned by the cache" | "A stale cache entry served old prices for 3 hours." |
| "The gotcha is ordering" | "Migrations must run before seeds, or seeding fails on missing tables." |

## Compressed, slick sentences

Lines that drop articles and context and lean on an unusual verb to sound
sharp. Write the full sentence.

| Pattern | Fix |
|---|---|
| "B at a ledge lets you mantle." | "Press B while facing a ledge to climb onto it." |
| "Stale lockfile, cold cache, red build." | "The build fails because the cache holds a stale lockfile." |
| "Retries paper over the 503s." | "The client retries 503 responses, so they never reach the logs." |
| "A style-only diff across untouched code hides the change that matters." | "Making format changes only obfuscates actual code changes." |
| "One flag gates the whole path." | "`ENABLE_SYNC` turns the sync code on or off." |

## Polished one-liners

| Pattern | Fix |
|---|---|
| "Cheap to add, expensive to remove." | "Removing it later means migrating every stored record." |
| "The code is fine. The contract isn't." | "The function matches its docs, but callers pass `null`, which the docs forbid." |
| "Treat X as the source and Y as the packaging." | "Edit X. Y only points to it." |
| "A cache bug wearing a network costume." | "The timeout comes from a stale cache entry, not the network." |
| "That 'usually' is doing a lot of work." | "It fails when the file is over 2 MB." |

## Invented terms

Real engineering vocabulary is fine. A name coined for this conversation is
not, because the reader has to work out what it means.

| Pattern | Fix |
|---|---|
| "This is the classic dual-source problem." | "The rules live in two files, so they will drift apart." |
| "Call it a two-hop include." | "`CLAUDE.md` imports `AGENTS.md`, which links to `docs/writing.md`." |
| "That's config drift tax." | "Every copy has to be updated by hand." |

## Teasers, asides and drama adverbs

| Pattern | Fix |
|---|---|
| "There's a catch." / "The fix: one line." | State the catch or the fix. |
| "Tests pass, for some definition of pass." | "Tests pass because three are skipped." |
| "(ask me how I know)" | Delete. |
| "This quietly breaks on Windows." | "Paths use `/`, so it fails on Windows." |
| "The honest answer is no." | "No." |
| "The big unlock is caching." | "Caching cuts load time from 3 s to 0.4 s." |

## Before and after

> Before: "Great question! Here's the thing: the build isn't failing because of
> the code. It's failing because of the cache. Let me walk you through it."
>
> After: "The build fails because the cache holds a stale lockfile. Clearing
> `~/.cache/pnpm` fixes it."

> Before: "I've implemented a robust, comprehensive solution that seamlessly
> handles all edge cases. Let me know if you'd like any changes!"
>
> After: "Added retry with backoff to `fetchUser`. Tested against a 503 and a
> timeout; both now succeed on the second attempt. Not tested: rate-limit
> responses."

> Before: "Speed. Reliability. Simplicity. That's what this refactor delivers."
>
> After: "The refactor removes the second cache layer. Cold start drops from
> 1.8 s to 0.9 s, measured over 20 runs."
