---
term: Orthography
slug: orthography
aliases:
  - spelling system
level: intermediate
depth: deep
summary: >-
  Orthography is the set of language-specific rules for using a script to write
  a particular language: its spelling, capitalization, and punctuation
  conventions.
related:
  - dialect
  - script
  - writing-system
  - segmentation
  - input-method-editor
  - autonym
status: voice-passed
version_added: 0.1
updated: 2026-06-23T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: W3C Internationalization (i18n)
    url: https://www.w3.org/International/
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Orthography

## Definition

Orthography is the set of language-specific rules for using a script to write a particular language: its spelling, capitalization, and punctuation conventions.

A [writing system](writing-system.md) is made of two parts: a [script](script.md) and an orthography. The script supplies the [symbols](../../terms/symbol.md); the orthography is the language-specific layer that decides how one language uses them.



### Why it matters in design systems

In a design system, the script decides whether the symbols render; the orthography decides whether the language is actually right. Spelling, capitalization, quotation marks, and number formatting all live in the orthography, and they are the details that make localized text read as correct or wrong to a native speaker.&#x20;

None of them come from the font or the script, so multi-language support that stops at "the glyphs are there" is missing the orthography layer entirely. And because a language can have more than one orthography, and orthographies get reformed over time, these belong in locale data and user settings, not in hardcoded constants.



#### Example

American and British English share one language and the same [Latin script](../../terms/latin-script.md), but follow different orthographies: "color" and "organize" in one, "colour" and "organise" in the other. Same words, same letters available, different spelling rules. Orthographies can differ more deeply than spelling, down to the script itself: Serbian is written in both [Cyrillic](../../terms/cyrillic.md) and [Latin](../../terms/latin-script.md), which makes it two [writing systems](writing-system.md) for one language.



### Common mistake

The right script does not mean the right language support. A font with full Latin glyphs has no opinion on whether the spelling is "color" or "colour", whether every noun is capitalized (in German, it is), or which quotation marks French expects. Those live in the orthography, not the script.&#x20;

Choosing a script gets the symbols on screen; it says nothing about the spelling, casing, and punctuation rules a language expects, and a language code alone does not settle it either, since some languages (Serbian, Kurdish) use more than one orthography.



### In practice

* **Treat orthography as configurable, not implied:** where a language has more than one orthography, let the choice be set (a locale variant, a user preference) rather than assuming it from the language or the script. This connects to [segmentation](../../terms/segmentation.md) (line-breaking and capitalization rules differ by orthography) and [input methods](../../terms/input-method-editor.md) (how users type the orthography they want).
* **Punctuation and casing are orthography, not afterthoughts:** quotation marks, decimal separators, and capitalization conventions vary by language, so they belong in localization data, not hardcoded UI strings.
* **Orthographies change:** which orthography a language uses, and which is current or preferred, is community-specific and shifts over time (spelling reforms, script revivals). Treat it as expert-verified, and confirm specifics with the language cohort.



***

### Related terms and mentions

[Dialect](../../terms/dialect.md) · [Script](script.md) · [Writing system](writing-system.md) · [Segmentation](../../terms/segmentation.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Autonym](../../terms/autonym.md)



### Further reading

* Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)



### Sources

*
