---
term: Macrolanguage
slug: macrolanguage
aliases: []
tags: [language-linguistics]
level: intermediate
depth: core
summary: A macrolanguage is an ISO 639-3 grouping of several closely related individual languages that are treated as one language in some contexts.
related: [iso-639-3, language-family, dialect]
status: voice-passed
version_added: 0.1
updated: 2026-06-19
contributors: [sam-gordashko]
further_reading:
  - title: "ISO 639-3: Scope of denotation"
    url: https://iso639-3.sil.org/about/scope
    type: authority
license: CC-BY-4.0
---

# Macrolanguage

## Definition

A macrolanguage is an ISO 639-3 grouping of several closely related individual languages that are treated as one language in some contexts. It sits between a single [language](language.md) and a [language family](language-family.md): the members are close enough that in some settings, such as a shared written standard, one common identity is enough,<sup>1</sup> while each member still keeps its own [ISO 639-3](iso-639-3.md) code for when precision matters.

### Why it matters in design systems

The trap is assuming a language tag names exactly one language. It may name a macrolanguage, which is coarser: a label like "Arabic" can cover several distinct spoken and written varieties. The level you tag content at changes behaviour: a font may cover the macrolanguage broadly while a specific variety needs different vocabulary, a language picker may list the macrolanguage in one place and its members in another, and a [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) usually pins one specific variety. Decide deliberately which level a string, font, or setting is really about, rather than assuming the broad label is specific enough.

### Example

Arabic (`ara`) is a macrolanguage; ISO 639-3 lists 28 individual languages under it, including Standard Arabic (`arb`), Egyptian Arabic (`arz`), and Moroccan Arabic (`ary`), a count that can shift between releases.<sup>2</sup>

***

### Related terms and mentions

[ISO 639-3](iso-639-3.md) · [Language](language.md) · [Language family](language-family.md) · [Dialect](dialect.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Language & linguistics](../../terms/language-linguistics.md)

### Further reading

* Foundations: [ISO 639-3: Scope of denotation](https://iso639-3.sil.org/about/scope)

### Sources

1. Macrolanguages exist where clusters of closely related varieties can be considered distinct individual languages, yet "in certain usage contexts a single language identity for all is needed." [ISO 639-3: Scope of denotation (SIL)](https://iso639-3.sil.org/about/scope)
2. Arabic [ara] is a macrolanguage containing 28 individual languages, including Standard Arabic [arb], Egyptian Arabic [arz], and Moroccan Arabic [ary]. [ISO 639-3: ara (SIL)](https://iso639-3.sil.org/code/ara)
