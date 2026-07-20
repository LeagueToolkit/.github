# AI styleguide

Rules for anything an LLM writes in a LeagueToolkit repo: docs, READMEs, code comments, commit
messages, PR descriptions, issue replies.

The goal is not "hide that AI was involved." It's that AI defaults produce a recognizable texture -
padded, hedging, over-formatted, confidently wrong about binary formats - and that texture is bad
writing regardless of who produced it. These rules mostly say *stop doing the default thing*.

If you are an agent reading this: treat it as binding. If you are a human reviewing agent output,
this is the checklist.

## Punctuation and typography

- **No em dashes (U+2014).** Use a plain hyphen `-` for the parenthetical break instead. The em
  dash is sloppy.
- **En dashes (U+2013) are fine** where they're typographically correct: numeric and date ranges
  (2013–2024, pages 10–14, Rust 1.75–1.82). You can use regular dashes as line breaks.
- **No "smart" quotes or apostrophes** (U+2018/2019/201C/201D). ASCII `'` and `"` only, and three
  periods rather than the single-character ellipsis (U+2026).
- **Emoji in markdown headings are fine when they earn their place.** One per heading, used as a
  visual anchor that helps a reader scan a long doc or tells sections apart at a glance. What's
  not fine is decorating every heading, or reaching for 🚀/✨/🔥 as enthusiasm. If removing it
  loses nothing, it wasn't doing anything.
- **No emoji in code, commit messages, or PR titles.** Those get read by tooling and terminals.
- **Arrows (`→`) are fine** in ordered lists and flow descriptions. They're not a dash.

## Sentence patterns to avoid

These read as machine-generated because they are:

- **The contrast cliché.** "It's not just a parser - it's a complete toolkit." "This isn't about
  speed; it's about correctness." Say the thing, drop the setup.
- **Rule-of-three padding.** "Fast, reliable, and easy to use." Three adjectives where one carries
  meaning means two are filler. Pick the one that's actually true and specific.
- **Hollow openers.** "In today's fast-paced world", "It's worth noting that", "Let's dive into",
  "At its core". Delete the sentence and start with the content.
- **Vocabulary tells.** *delve, leverage, seamless, robust, comprehensive, elevate, unlock,
  harness, streamline, cutting-edge, game-changing, boasts, plethora, testament to.* Pick the
  plain word: use, not leverage. Full, not comprehensive.
- **Summary paragraphs that restate the section.** "In summary, we've covered..." If the section
  needed a summary it was too long.
- **Hedged non-answers.** "This may or may not work depending on your setup." Either find out, or
  say precisely what you don't know: "Untested on macOS."
- **Fake enthusiasm.** "Great question!", "Happy hacking!", "You're all set!". Exclamation marks
  themselves are fine - use them where you'd actually raise your voice, like a real warning
  ("This will overwrite your install!"). The problem is manufactured excitement, not the mark.

## Formatting discipline

- **Don't bold half the sentence.** Bold marks the one term a scanner needs to catch. Bolding
  every clause is the same as bolding nothing.
- **Prose beats bullets for reasoning; bullets beat prose for enumeration.** A bulleted list where
  each bullet is a full paragraph should have been prose. Three-word bullets that need context
  should have been a sentence.
- **No nested lists past two levels.** If you need three, the structure is wrong.
- **No tables for two-column data with three rows.** Use a list.
- **Headings are navigation, not decoration.** Don't add a `##` for two sentences.

## Voice

- **Second person, present tense, active voice.** "Run this in PowerShell", not "This command may
  be run by the user."
- **Concrete over abstract.** "Extracts a 2 GB WAD in about 4 seconds" beats "high performance".
  If you don't have the number, don't make the claim.
- **State limits plainly.** "ETC1, ETC2, and BC5 are not supported for encoding." No apology, no
  roadmap promise.
- **No marketing.** Nobody arriving at a `.wad` extractor needs to be sold on it.

## Accuracy, especially for reverse-engineered formats

This org documents undocumented binary formats. Confident-sounding invention is the most damaging
thing an LLM can do here.

- **Never state a format detail you haven't verified against code or a real file.** Offsets, field
  sizes, magic values, version numbers - if it came from the model's prior rather than from this
  repo, it is a guess and must be labeled one.
- **Label guesses inline.** "Probably a flags field; observed values are 0 and 3." Not "A flags
  field."
- **Don't name unknown fields plausibly.** `unknown_0x14` with an observation comment beats
  `render_flags` that turns out to be wrong - a wrong name propagates into every downstream tool.
- **Don't invent CLI flags, file paths, config keys, or crate APIs.** Read the actual `clap`
  definitions or the actual source. A README documenting a flag that doesn't exist is worse than
  an undocumented flag.
- **Don't fabricate benchmarks, version numbers, dates, or contributor names.**
- **Cite where knowledge came from** when it's non-obvious: a game version, a binary offset, a
  related project.

## Code comments

- **Comment why, not what.** `// increment i` is noise. `// chunk counts are u24 in v3.1, u32 from
  v3.2` is the whole reason the line exists.
- **Match the file's existing comment density.** Don't carpet a sparsely-commented codebase in
  docstrings because that's the default habit.
- **No section-banner comments** (`// ===== HELPERS =====`) unless the file already uses them.
- **No comments restating the function signature** in a doc comment.

## Commits and PRs

- Conventional Commits, imperative mood, lowercase after the type:
  `fix: handle zero-length chunks when extracting`.
- **Subject line under ~72 chars, no trailing period.**
- **The body says why, and what changed in behavior.** Not a bullet list of every file touched -
  the diff already has that.
- **No "🤖 Generated with..." trailers or AI attribution lines** unless a maintainer asks for them.
- **PR descriptions state what was actually tested**, with the commands run. If it wasn't tested,
  say that explicitly rather than implying coverage.

## Reporting on your own work

- **Say what failed.** If tests fail, paste the output. If a step was skipped, name it.
- **Don't pad with what you didn't do.** No "next steps you might consider" lists nobody asked for.
- **Don't claim verification you didn't perform.** "Builds clean" requires having run the build.
- **Length matches the work.** A one-line fix gets a one-line summary.

## Quick checklist

Before committing anything an LLM wrote:

- [ ] Zero em dashes; ASCII quotes and apostrophes (en dashes OK in ranges)
- [ ] No contrast clichés, rule-of-three padding, or vocabulary tells
- [ ] Every format detail, flag, and path verified against the source
- [ ] Guesses labeled as guesses; unknown fields named `unknown_*`
- [ ] Bold and headings used sparingly and deliberately
- [ ] Emoji earn their place (headings only, sparingly); no marketing or manufactured enthusiasm
- [ ] Commit subject is conventional, imperative, under ~72 chars, no AI trailer
- [ ] Claims about testing are true

Structural conventions for READMEs specifically live in
[repo-template/docs/README-STYLE.md](https://github.com/LeagueToolkit/repo-template/blob/main/docs/README-STYLE.md).
