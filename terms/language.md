---
term: Language
slug: language
aliases: []
tags: [language-linguistics]
level: foundational
depth: deep
summary: "A language is a system a community uses to communicate in speech or sign; writing is a separate layer added on top of it."
related: [language-family, dialect, macrolanguage, orthography, writing-system, script]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Language (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Language
    type: authority
license: CC-BY-4.0
---

# Language

## Definition
A language is a system a community uses to communicate in speech or sign; writing is a separate layer added on top of it.

## Why it matters
The most useful thing this term pins down is a separation the whole writing-systems cluster depends on: a language is spoken or signed, and writing is a technology layered on top of it. A language exists whether or not it is written, one language can be written with more than one [script](script.md), and the rules for writing a particular language are its [orthography](orthography.md). It is also the root the other linguistics terms hang from, [language family](language-family.md), [dialect](dialect.md), and [macrolanguage](macrolanguage.md). Keeping "language" distinct from "script" and "writing system" is what stops the most common category error in interface work: treating "languages supported" as if it answered "which scripts and layouts do we render."

## Example
Spoken Mandarin and spoken Cantonese are different languages that have historically shared one written form; Serbian is one language written in two scripts. Neither fact makes sense if "language" and "writing" are treated as the same thing.

## Common mistake
Equating a language with its writing, or with a country. Many languages are primarily spoken and have little or no standard written form, the same language can cross many borders, and a single country can hold dozens of languages. For software this surfaces as conflating a language with a [locale](locale.md) or a script, which then breaks for multilingual users.

## In practice
- **Treat language, script, and writing system as three separate axes:** the [language](language.md) is what is spoken, the [script](script.md) is the sign set, and the [writing system](writing-system.md) is a script applied to a language with its orthographic rules. Modeling them separately is what lets a product support, say, one language in two scripts.
- **Identify languages with stable codes, not names:** language names are ambiguous and political, so engineering uses standardized identifiers (see [ISO 639-3](iso-639-3.md)) and the catalogues that maintain them. Which code applies to which variety is exactly the kind of judgment the language cohort verifies.

## Related terms
[Language family](language-family.md) · [Dialect](dialect.md) · [Macrolanguage](macrolanguage.md) · [Orthography](orthography.md) · [Writing system](writing-system.md) · [Script](script.md)

## Further reading
- Foundations: [Language (Wikipedia)](https://en.wikipedia.org/wiki/Language)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). Upgrade to an authoritative primary (Glottolog, Ethnologue, ISO 639-3 registry) vetted by the SILCON cohort. Any count of the world's languages is deliberately omitted; the Mandarin/Cantonese shared-writing example and the Serbian two-script example are standard but should be confirmed. -->
