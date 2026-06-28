# Glossary entry verification task

Hand this file to an independent agent (Cowork or a fresh session) to fact-check and
review one glossary entry. Tell it which entry to review, e.g. *"Run the verification
in glossary-entry-verify.md on `terms/reph.md`."* The agent produces a findings
report; the original author applies the findings. This is the second pass over an
entry someone else first-passed.

---

You are an **independent reviewer** of one Future Friendly glossary entry. You did
**not** write it. Find what is wrong with it, skeptically, and return a findings
report. **Do not edit any files.**

The glossary is a CC-BY reference mapping writing-system and linguistics terms to
typography and design-system concepts. Readers are **designers and language
communities, often ESL, not linguists**. House spec: `glossary-canonical-entry-format.md`.

## The one rule that makes this worth running

**Verify by fetching, never from memory.** Every accuracy finding must carry a real
source URL you actually fetched. Errors hide exactly where someone asserted a
plausible fact without checking; verifying from memory reproduces the failure. If you
cannot fetch a source, mark the claim UNVERIFIED.

Primary sources (preferred): Unicode (the Standard, UAX, the UCD data files), W3C
Internationalization (w3.org/International, layout-requirements docs, r12a.github.io),
CLDR, MDN, Microsoft script-development / OpenType docs, type foundries, SIL.
**Wikipedia and blogs are secondary cross-checks only**, never the sole basis for a
VERIFIED.

## Audit on four axes. Be exhaustive, especially terminology.

### 1. Factual accuracy
For every factual or example claim, fetch a primary source and report: the claim,
**VERIFIED / UNVERIFIED / WRONG**, and the source URL. Flag any fact with no citable
primary source. Check worked examples literally (decompose the actual characters,
confirm the rendering claim). Watch for **popular-but-imprecise framings** that primary
sources contradict (e.g. a positional consonant form called a "diacritic mark").

### 2. Terminology misuse (the priority, be ruthless)
- **"letter(s)" for the generic unit of a script** - house term is **"symbol"**;
  "letter"/"consonant" only where genuinely alphabet/abjad-specific ("the Arabic
  letters", "the Latin letter f"). Flag every generic use.
- any **symbol or mark called a "sign."**
- **"Latin" used as if a language** - it means the **Latin script** (English, Spanish,
  Vietnamese...). Recommend "Latin script" or "English".
- **undefined / unglossed jargon** a designer or ESL reader would not know and that is
  neither glossed nor linked (run, cursive, cluster, subjoined, inherent vowel,
  above-base, shaping, glyph, code point, conjunct, baseline, hinting...). Swapping one
  unfamiliar word for another is not a fix.
- **definitions that are not script-neutral** (must hold for abjads, abugidas,
  syllabaries, logographic scripts, not only alphabets).
- **spelling:** Canadian in prose (behaviour, colour, centre), US/canonical in code and
  CSS identifiers (color, line-height).
- **em dashes** - there should be none.

### 3. Clarity for the audience
Flag sentences that assume knowledge, are convoluted, personify an abstraction, use
idiom an ESL reader may miss, or restate the Definition. Propose a plainer rewrite,
one idea per sentence.

### 4. Structure and sourcing
- frontmatter `summary` must equal the **Definition's first sentence** (ignoring links).
- source markers `<sup>n</sup>` must **ascend in order of first appearance** (an opener
  table precedes "Why it matters", so its sources are 1, 2, 3...).
- **no citation marker on a navigational sentence** (e.g. an opener table lead-in); the
  source goes in Further reading or on the specific claim/cell.
- **"Related terms and mentions"** is a knowledge-graph relationship list: include every
  term **mentioned in the body** + **genuine related peers** (the frontmatter `related`
  set and true conceptual neighbours, even if not yet mentioned) + the parent MOC
  anchor. Flag only **genuinely-unrelated** terms (junk edges) or a **missing genuine
  relationship**, not a peer that is merely unmentioned.
- the closing reminder is **a short paragraph on genuine rule pages, one sentence on
  narrow feature/classification pages**; flag if it overstates ("applies to every
  language" when some behaviours are language-specific).
- assess the framing: a **rule** vs a **feature/output** vs a **classification** (e.g.
  "stacking script" is a behaviour, not a script class; "reph" is a form produced by the
  reordering rule, not a rule itself).

## Output

A numbered findings list. For each: **(a)** the exact quoted text and location,
**(b)** the problem and severity (**blocker / should-fix / nit**), **(c)** a specific
proposed rewrite, **(d)** a source URL wherever accuracy is involved. End with a
one-line **verdict** (factually sound and term-clean, or needs another pass) and the
list of sources you fetched. **Do not edit any files.**
