---
term: Autonym
slug: autonym
aliases:
  - endonym
level: intermediate
depth: core
summary: >-
  An autonym is the name a people, language, or script uses for itself, as
  opposed to a name given by outsiders.
related:
  - exonym
  - dialect
  - iso-639-3
  - localization
  - cldr
status: voice-passed
version_added: 0.1
updated: 2026-06-19T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Endonym and exonym (Wikipedia)
    url: https://en.wikipedia.org/wiki/Endonym_and_exonym
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Autonym

## Definition

An autonym is the name a people, language, or script uses for itself, as opposed to a name given by outsiders.<sup>1</sup> Its opposite is an [exonym](exonym.md), the name outsiders use;<sup>2</sup> "autonym" and "endonym" are two words for the same self-name.

### Why it matters in design systems

Language and country pickers are often built from English names, which quietly tells speakers their language is being described from the outside. A well-internationalized picker lists each [language](language.md) by its autonym, so a reader recognizes their own language at a glance instead of decoding an outsider's label for it. Pull the autonyms from a maintained dataset such as [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) rather than translating them by hand, and store them as data, not as UI strings baked into one layout. The same courtesy applies to scripts and places: use the self-name where one exists.

### Example

"Deutsch" is the autonym for the language English speakers call by the exonym "German." A [script](../writing-systems-and-scripts/script.md)'s own name works the same way: देवनागरी is the autonym of the [Devanagari](../writing-systems-and-scripts/devanagari.md) script, the name it carries in the languages that use it.

***

### Related terms and mentions

[CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) · [Devanagari](../writing-systems-and-scripts/devanagari.md) · [Dialect](dialect.md) · [Exonym](exonym.md) · [ISO 639-3](iso-639-3.md) · [Language](language.md) · [Localization](../../programming-terms/text-for-digital-products-and-the-web/localization.md) · [Script](../writing-systems-and-scripts/script.md) · [Language & linguistics](/broken/pages/2BAGMUx1IldkYfEdZVOY)

### Further reading

* Foundations: [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)

### Sources

1. "An endonym or autonym is a common, self-chosen, native name of a group of people, an individual person of that group, a geographical place, a language or a dialect." [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)
2. An exonym is "a foreign-established, non-native name" for a group of people, a place, a language, or a dialect. [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)
