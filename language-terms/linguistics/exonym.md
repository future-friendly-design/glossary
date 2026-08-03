---
term: Exonym
slug: exonym
aliases: []
level: intermediate
depth: core
summary: An exonym is the name outsiders use for a language, place, or people, different from the name that group uses for itself.
related:
  - autonym
  - localization
  - cldr
  - iso-639-3
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
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

# Exonym

## Definition

An exonym is the name outsiders use for a language, place, or people, different from the name that group uses for itself.<sup>1</sup> It is the flip side of an [autonym](autonym.md), also called an endonym, which is the name a group uses for itself.<sup>2</sup>

### Why it matters in design systems

English speakers say "German," "Finnish," and "Japanese"; the speakers themselves say "Deutsch," "suomi," and "日本語." The practical rule is the one the [autonym](autonym.md) entry makes: a language picker should show each language by its autonym, not its English exonym, so a user spots their language at a glance. It also matters because some exonyms are dated or politically loaded, and a community may prefer not to be labelled by one, so treat the choice of name as a respect decision sourced from a maintained dataset like [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md), not an English default hardcoded into the interface.

### Example

"German" is the exonym English speakers use for the language its own speakers call "Deutsch."

***

### Related terms and mentions

[Autonym](autonym.md) · [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) · [ISO 639-3](iso-639-3.md) · [Language](language.md) · [Localization](../../programming-terms/text-for-digital-products-and-the-web/localization.md) · [Language & linguistics](../../terms/language-linguistics.md)

### Further reading

* Foundations: [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)

### Sources

1. An exonym is "a foreign-established, non-native name" for a group of people, a place, a language, or a dialect. [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)
2. "An endonym or autonym is a common, self-chosen, native name of a group of people, an individual person of that group, a geographical place, a language or a dialect." [Endonym and exonym (Wikipedia)](https://en.wikipedia.org/wiki/Endonym_and_exonym)
