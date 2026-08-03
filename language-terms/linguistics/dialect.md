---
term: Dialect
slug: dialect
aliases:
  - language variety
level: foundational
depth: core
summary: >-
  A dialect is a regional or social variety of a language with its own
  distinctive words, pronunciation, or grammar.
related:
  - macrolanguage
  - language-family
  - autonym
  - orthography
status: voice-passed
version_added: 0.1
updated: 2026-06-19T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Dialect (Wikipedia)
    url: https://en.wikipedia.org/wiki/Dialect
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Dialect

## Definition

A dialect is a regional or social variety of a [language](language.md) with its own distinctive words, pronunciation, or grammar.<sup>1</sup> The line between a dialect and a separate language is often social and political rather than purely linguistic,<sup>2</sup> so the same variety can be called either depending on who is asking.

### Why it matters in design systems

It is tempting to treat one variety as the "correct" language and the rest as deviations, but that ranking does not hold linguistically: standard varieties are just dialects that gained prestige, captured in the linguist Max Weinreich's often-quoted line that "a language is a dialect with an army and navy."<sup>3</sup> For product work this is why choices of spelling, terminology, and regional variant are content and [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) decisions, not questions linguistics settles for you. Let the community's own sense of its language guide the default, and model regional varieties as locale variants rather than as one right answer.

### Example

British and American English are dialects of English that differ in spelling ("colour" versus "color") and vocabulary ("lift" versus "elevator"). That spelling split is where a dialect meets [orthography](../writing-systems-and-scripts/orthography.md): orthography is the set of rules for writing a language, and a dialect that has been standardized usually carries its own spelling conventions, so the same language ends up written two slightly different ways. Neither is more correct; they map to different locales (`en-GB`, `en-US`), which makes "which spelling do we ship" a locale and content decision rather than a matter of right and wrong.

***

### Related terms and mentions

[Autonym](autonym.md) · [Language](language.md) · [Language family](language-family.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Macrolanguage](macrolanguage.md) · [Orthography](../writing-systems-and-scripts/orthography.md) · [Language & linguistics](./)

### Further reading

* Foundations: [Dialect (Wikipedia)](https://en.wikipedia.org/wiki/Dialect)

### Sources

1. "a variety of language spoken by a particular group of people" [Dialect (Wikipedia)](https://en.wikipedia.org/wiki/Dialect)
2. The language and dialect distinction is "often subject to debate, with the differentiation between the two classifications often grounded in arbitrary or sociopolitical motives." [Dialect (Wikipedia)](https://en.wikipedia.org/wiki/Dialect)
3. "A language is a dialect with an army and navy," a quip attributed to the linguist Max Weinreich. [Dialect (Wikipedia)](https://en.wikipedia.org/wiki/Dialect)
