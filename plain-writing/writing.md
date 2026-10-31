# Plain writing

These rules apply to any assistant or agent working in the repository.

Write the way a careful engineer who owns the codebase would: plainly,
briefly, and for the next reader. Apply this to everything you touch, and to
your replies.

Do not reformat files you are not otherwise changing. Making format changes
only obfuscates actual code changes.

## Replies to the user

- Answer first. Then give only the detail needed to act on it.
- Report what was done and how it was checked. If something failed or was
  skipped, say so plainly.
- Do not repeat the request back, summarise the summary, or list options you
  will not pursue. Give a recommendation.
- No praise of the question or idea. No closing offer of more help.
- No announcing what you are about to do ("Let me walk you through...",
  "Here's what I found:"). Do it.
- Trust the reader. Skip reassurance ("And that's okay"), softening and
  hand-holding.

## Code

- A name says what the thing is, with units where it helps (`timeoutMs`,
  `widthPx`, `rows`). Short names are fine when they are local and
  conventional in that code.
- One function, one job. If a block needs a comment to say what it does, it
  usually wants to be a function with that name.
- No dead code, no commented-out code, no unused parameters kept "for later".
- A number that means something gets a name. A number used in two places gets
  one definition that both read.
- Prefer data over branches: a table of per-case values beats a chain of `if`s.
- Respect the project's existing layering and conventions.

## Comments

- A comment states a constraint or a reason the code cannot show. It does not
  restate the code.
- Lead with the rule. If a plausible edit would break it, add the symptom in
  one clause: "Must match `PANEL_HALF`, or the highlight is the wrong size."
- One to three lines is normal. A long history belongs in the commit message.
- No jokes or scene-setting in code.
- No first person, no "we", no addressing the reader.

## Register

Code, comments, docs, commit messages, PR descriptions and replies are
technical writing, not marketing copy. Say what the code does, with its
parameters and units. Describe a feature by what the user can do.

- No figurative or atmospheric language.
- No false agency: code, data and decisions do not act on their own. Name the
  actor. "The retry loop hides the error", not "the error gets swallowed";
  "you decide", not "the decision emerges".
- Prefer active voice. Passive is fine only when the actor is unknown or
  irrelevant.
- Be specific. "The implications are significant" says nothing; name the
  implication. Replace "always", "never", "every" with the actual scope unless
  they are literally true.
- No selling: a PR or reply says what changed, how it was verified and what to
  check, not why it is exciting.
- A README describes features plainly. It is documentation, not a trailer.
- Real engineering terms are fine: *race condition, idempotent, footgun,
  blast radius, happy path*. Invented terms are not. Do not coin a name for a
  problem ("the dual-source problem") and then use it as if the reader knows
  it. Describe the problem.
- Write full sentences a newcomer can parse: subject, verb, condition,
  result. Do not compress a sentence into a slick line that drops articles
  and leans on an unusual verb. "B at a ledge lets you mantle" becomes
  "Press B while facing a ledge to climb onto it."

Bad: `// The heart of the system: where requests find their home.`
Good: `// Routes requests by path prefix; first match wins.`

## Words and constructions to cut

These read as filler or as generated text. The full lists, with fixes, are in
[patterns.md](patterns.md).

- Throat-clearing openers: *here's the thing, it turns out, the truth is, let
  me be clear*, any "here's what/why/how".
- Intensifiers and hedges: *very, really, just, simply, actually, basically,
  genuinely, honestly, literally, crucially, importantly, essentially,
  fundamentally, quite, arguably*.
- Signposting and meta-commentary: *note that, it's worth noting, keep in
  mind, the key insight, in other words, as we'll see, in this section*.
- Emphasis crutches: *full stop, let that sink in, make no mistake, this
  matters because*.
- Inflated vocabulary and jargon: *leverage, robust, seamless, utilize,
  facilitate, comprehensive, delve, navigate, unpack, landscape, deep dive,
  game-changer, ensure that* (write "so" or "to").
- Binary contrasts: "not X, but Y"; "X isn't the problem, Y is"; "not just X
  but also Y". State Y.
- Negative listing: "Not X. Not Y. Z." State Z.
- Dramatic fragments: "Speed. Quality. Cost. That's it." Write a sentence.
- Rhetorical setups: "What if...?", "Think about it:", a question answered in
  the next sentence, a sentence that only announces the next one.
- Three-item lists added for rhythm. Use the number of items there are.
- Paragraphs that end on a quotable one-liner. If it sounds like a pull-quote,
  rewrite it.
- Emphasis markup (bold, capitals) inside code comments.
- Pain verbs for problems: *bites, stings, burns, trips you up, gets you*
  ("here's the part that bites"). State the failure and when it happens.
- Polished one-liners: mirrored sentences ("cheap to add, expensive to
  remove"), clever disguises ("a cache bug wearing a network costume"),
  "X is doing a lot of work here". Say the fact the line hints at.
- Colon reveals and teasers: *the catch:, the fix:, the upshot:, short
  version:, there's a catch*. Give the catch or the fix.
- Wry asides: *(ask me how I know), which is a polite way of saying,
  spoiler:, for some definition of*.
- Drama adverbs on mechanisms: *quietly, silently, sneakily*. Say what the
  code does: "catches the error and returns `[]` without logging".
- Sincerity markers: *the honest answer is, to be candid, to be fair*.
- Business nouns: *the ask, the unlock, the win, the learnings, the play*.
- Em dashes. Use a full stop, a comma or a colon.

## Commit messages

Imperative subject under 72 characters, naming the area: `auth: split token
refresh out of the client`. The body says what changed, why, and how it was
verified. No marketing.

## Documentation

Lead each section with the rule or the fact. Use a table when comparing
things. State a measured number with how it was measured. Record a failure
mode when the code does not make it obvious, in the form: rule, symptom,
reason.

## Behaviour-preserving changes

A refactor claims to change nothing. Prove it with the cheapest proof that
works: identical output from the same inputs, identical build output for code
that only moved, before/after captures, then the test suite. State which
proofs you ran in the commit message.

## Check before sending

- Does the first sentence answer the question or state the result?
- Any word from the cut lists? Remove it.
- Any "not X, but Y"? State Y.
- Any thing doing a human verb? Name who does it.
- Any vague claim of importance? Name the specific thing or cut it.
- Any em dash? Replace it.
- Any line that sounds clever? Rewrite it as the plain fact.
- Any term you made up? Replace it with a description.
- Anything that can be deleted without losing information? Delete it.
