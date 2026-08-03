---
term: Language family
slug: language-family
aliases: []
tags: [language-linguistics]
level: foundational
depth: core
summary: A language family is a group of languages that all descend from a single common ancestor, called its proto-language.
related: [macrolanguage, iso-639-3, dialect, glottolog]
status: voice-passed
version_added: 0.1
updated: 2026-06-19
contributors: [sam-gordashko]
further_reading:
  - title: "Glottolog: Language families"
    url: https://glottolog.org/glottolog/family
    type: authority
license: CC-BY-4.0
---

# Language family

## Definition

A language family is a group of languages that all descend from a single common ancestor, called its proto-language.<sup>1</sup> It is a grouping by shared history, not by how the languages are written: members can use completely different scripts. Distinguish it from a [macrolanguage](macrolanguage.md), which gathers closely related varieties treated as one language, and from a [dialect](dialect.md), which is a variety of a single [language](language.md). Some languages are isolates, like Basque, with no known relatives and so no family.<sup>2</sup>

### Why it matters in design systems

The mistake is to treat family membership as a unit of support, as if "we handle Indo-European" meant anything for rendering. A family tells you about descent, not about what a language needs on screen: related languages routinely use different [scripts](../writing-systems-and-scripts/script.md), directions, and shaping, so two members can share nothing that matters for your fonts or layout. The largest families by number of languages include Atlantic-Congo (also called Niger-Congo), Austronesian, Sino-Tibetan, and Indo-European,<sup>3</sup> but that scale is genealogical, not typographic. Plan [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) and shaping per script and per language, and treat the family only as coarse background, never as the axis your support matrix is built on.

### Example

English, Hindi, Russian, and Spanish all belong to the Indo-European family, yet English and Spanish are written in the [Latin script](../writing-systems-and-scripts/latin-script.md), Russian in [Cyrillic](../writing-systems-and-scripts/cyrillic.md), and Hindi in [Devanagari](../writing-systems-and-scripts/devanagari.md). Shared ancestry, three different rendering problems.

***

### Related terms and mentions

[Macrolanguage](macrolanguage.md) · [Dialect](dialect.md) · [Language](language.md) · [ISO 639-3](iso-639-3.md) · [Glottolog](glottolog.md) · [Script](../writing-systems-and-scripts/script.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Latin script](../writing-systems-and-scripts/latin-script.md) · [Cyrillic](../writing-systems-and-scripts/cyrillic.md) · [Devanagari](../writing-systems-and-scripts/devanagari.md) · [Language & linguistics](../../terms/language-linguistics.md)

### Further reading

* Foundations: [Glottolog: Language families](https://glottolog.org/glottolog/family)

### Sources

1. "a group of languages related through descent from a common ancestor, called the proto-language of that family" [Language family (Wikipedia)](https://en.wikipedia.org/wiki/Language_family)
2. Language isolates "cannot be proven to be genealogically related to any other modern language"; Basque is the classic example. [Language family (Wikipedia)](https://en.wikipedia.org/wiki/Language_family)
3. By number of languages, the largest families include Niger-Congo (Atlantic-Congo), Austronesian, Sino-Tibetan, and Indo-European (Ethnologue 27, 2024). [Language family (Wikipedia)](https://en.wikipedia.org/wiki/Language_family)
