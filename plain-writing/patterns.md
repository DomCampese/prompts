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
