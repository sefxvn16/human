# English patterns to remove

Read this file only when the text is in English. The 20 rules in `SKILL.md` still apply; this file adds English-specific phrase and structure lists.

All lists here are examples for recognition, not exhaustive bans. The words and phrases AI overuses change by model and by period: Wikipedia's "Signs of AI writing" (checked 5 Oct 2026) notes that "delve" was heavily overused in 2023 to early 2024 and has dropped sharply since, and that later models lean on words such as "emphasizing", "enhance", "highlighting" and "showcasing". A word being overused does not mean its synonyms are. Judge by mechanism (a generic word standing in for a concrete fact), not by matching a list.

Adapted from [stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya, MIT License (full text in `LICENSE-stop-slop.txt`). Three original rules were softened to match `SKILL.md`:

- **Em dashes:** follow rule 11 in `SKILL.md` (allowed only when a comma, parenthesis or colon cannot express the grammatical relation), not a total ban.
- **Passive voice:** prefer active voice and name the actor (rule 16), but keep passive where legal, administrative or formal register requires it.
- **Adverbs:** cut empty intensifiers and hedges (list below). Keep adverbs that carry meaning ("quarterly", "legally", "previously").

## Throat-clearing openers

State the content directly instead of announcing it.

- "Here's the thing:", "Here's what/why/this/that [X]"
- "The uncomfortable truth is", "The truth is,", "The reality is"
- "It turns out", "The real [X] is"
- "Let me be clear", "I'm going to be honest", "I'll say it again:"
- "Can we talk about", "Here's what I find interesting", "Here's the problem though"

## Emphasis crutches

Delete; they add no meaning.

- "Full stop." / "Period."
- "Let that sink in."
- "Make no mistake"
- "This matters because", "Here's why that matters"

## Business jargon

| Avoid | Use instead |
|---|---|
| navigate (challenges) | handle, address |
| unpack | explain, examine |
| lean into | accept, commit to |
| landscape | situation, field, market |
| game-changer | name the specific change |
| double down | commit further, increase |
| deep dive | analysis, review |
| take a step back | reconsider |
| moving forward | next, from now on |
| circle back | return to, follow up |
| on the same page | aligned, agreed |

## Empty intensifiers (cut) and meaningful hedges (keep)

Empty intensifiers add no meaning. Cut: really, just, literally, genuinely, honestly, simply, actually, deeply, truly, fundamentally, inherently, inevitably, interestingly, importantly, crucially.

Hedges that carry meaning stay (rule P4 in `SKILL.md`): "may", "perhaps", "tends to", "about" when the author is genuinely unsure or the data is approximate. Removing them changes the claim. Wikipedia's observation is that human-written text uses plain hedges and definite statements more often than AI text does, so stripping all hedging is not a fix.

Filler phrases: "At its core", "In today's [X]", "It's worth noting", "At the end of the day", "When it comes to", "In a world where"

## Meta-commentary

Let the text move instead of announcing its own structure.

- "Hint:", "Plot twist:", "Spoiler:"
- "You already know this, but", "But that's another post"
- "X is a feature, not a bug", "Dressed up as"
- "The rest of this essay explains...", "Let me walk you through...", "In this section, we'll...", "As we'll see...", "I want to explore..."

## Telling instead of showing

- "This is genuinely hard", "This is what leadership actually looks like", "actually matters"
- Vague declaratives: "The reasons are structural", "The implications are significant", "The stakes are high", "The consequences are real"

Replace with the specific reason, implication or consequence, or cut the sentence.

## Structures

| Pattern | Fix |
|---|---|
| Binary contrast: "Not because X. Because Y.", "The answer isn't X. It's Y.", "not just X but also Y", "stops being X and starts being Y" | State Y directly |
| Negative listing: "It wasn't X. It wasn't Y. It was Z." | State Z |
| Dramatic fragments: "[Noun]. That's it. That's the [thing].", "X. And Y. And Z." | Write complete sentences |
| Rhetorical setups: "What if [reframe]?", "Think about it:", "Here's what I mean:", "And that's okay." | Make the point |
| False agency: "the decision emerges", "the data tells us", "the market rewards", "the culture shifts" | Name who decided, who read the data, who paid |
| Narrator from a distance: "Nobody designed this.", "People tend to...", "This is why..." | Address the reader or name the specific people |
| Wh- sentence openers used as a crutch: "What makes this hard is..." | Lead with the subject: "The constraint is..." |
| Paragraphs opening with "So" or "Look," | Start with content |
| Copula avoidance: "serves as", "stands as", "marks", "boasts", "features", "offers", "represents" where "is" or "has" is meant | Write "is" or "has" |
| Vague connection: "associated with", "connected to", "known for" in place of a stated relationship | State it: "was CEO of", "designed by" (only if the input confirms it) |
| "Y rather than X" where nobody claimed X (common in AI-generated text) | State Y directly |

## Rhythm and word choice

- Three-item lists by reflex: use the real number of items (rule 2 in `SKILL.md`).
- A question answered in the very next sentence: cut the question.
- Stacked short punchy sentences: combine or vary.
- "Not always. Not perfectly.": hedging dressed as reassurance; cut.
- Lazy extremes (every, always, never, everyone, nobody) doing vague work: replace with the specific scope.
