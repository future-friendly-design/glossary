---
term: Language
slug: language
aliases: []
level: foundational
depth: deep
summary: A language is a system a community uses to communicate in speech or sign; writing is a separate layer added on top of it.
related:
  - language-family
  - dialect
  - macrolanguage
  - orthography
  - writing-system
  - script
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Language (Wikipedia)
    url: https://en.wikipedia.org/wiki/Language
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Language

## Definition

A language is a system a community uses to communicate in speech or sign; writing is a separate layer added on top of it.

### Why it matters in design systems

The most common category error in interface work is treating a language as if it were the same thing as its writing or its [script](../writing-systems-and-scripts/script.md). A language is spoken or signed, and writing is a technology layered on top of it: a language exists whether or not it is written, and the same language can be written in more than one script, each with its own [orthography](../writing-systems-and-scripts/orthography.md). This separation is what the whole writing-systems cluster depends on, and it drives concrete decisions: model language, script, and [writing system](../writing-systems-and-scripts/writing-system.md) as three separate axes rather than one dropdown, and pick fonts and shaping for the script, not the language. A language code is necessary but not sufficient to render text: knowing a string is Hindi tells you nothing about layout until you also know the script behind it. Language is also the root the other terms in this cluster hang from: a [language family](language-family.md) groups languages by shared ancestry, a [dialect](dialect.md) is a variety of one language, and a [macrolanguage](macrolanguage.md) is a cluster of closely related languages treated as one identity.

### Example

Serbian is one language written in two scripts: it is a rare case of synchronic digraphia, using both Cyrillic and Latin, so the language stays the same while the script changes.<sup>1</sup> Spoken Mandarin and spoken Cantonese run the other way: they are classified as separate individual languages, both grouped under the Chinese macrolanguage, yet they have historically shared one written form.<sup>2</sup> Neither fact makes sense if "language" and "writing" are treated as the same thing.

### Common mistake

Treating a language as if it were a country or a [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md). A single language crosses many borders (Spanish, Arabic, and Swahili each span several countries), a single country can hold dozens of languages, and many languages are primarily spoken with little or no standard written form. Wiring "languages supported" to a list of countries or locale codes breaks for exactly the multilingual users a product most wants to reach.

### In practice

* **Treat language, script, and writing system as three separate axes:** the language is what is spoken or signed, the script is how it is written down, and the writing system is a script applied to one language with its orthographic rules. Modeling them separately is what lets one product support a single language in two scripts, or one script across many languages.
* **Identify languages by stable codes, not names:** language names are ambiguous and contested, so use standardized identifiers such as [ISO 639-3](iso-639-3.md) and the catalogues that maintain them; which code applies to which variety is exactly the kind of judgment to verify with the language's own community.
* **List languages by their own name in pickers:** a language selector that shows each language by its [autonym](autonym.md), its own name, lets a speaker recognize their language at a glance instead of reading an outsider's label; pull the names from a maintained dataset rather than translating them by hand.

***

### Related terms and mentions

[Autonym](autonym.md) · [Dialect](dialect.md) · [ISO 639-3](iso-639-3.md) · [Language family](language-family.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Macrolanguage](macrolanguage.md) · [Orthography](../writing-systems-and-scripts/orthography.md) · [Script](../writing-systems-and-scripts/script.md) · [Writing system](../writing-systems-and-scripts/writing-system.md) · [Language & linguistics](../../terms/language-linguistics.md)

### Further reading

* Foundations: [Language (Wikipedia)](https://en.wikipedia.org/wiki/Language)

### Sources

1. "Serbian is a rare example of synchronic digraphia, using both Cyrillic and Latin scripts." [Serbian language (Wikipedia)](https://en.wikipedia.org/wiki/Serbian_language)
2. Chinese [zho] is listed as a macrolanguage containing Mandarin Chinese [cmn] and Yue Chinese (Cantonese) [yue] as separate individual languages. [ISO 639-3: zho (SIL)](https://iso639-3.sil.org/code/zho)
