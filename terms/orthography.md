---
term: Orthography
slug: orthography
aliases: [spelling system]
tags: [language-linguistics]
level: intermediate
depth: deep
summary: Orthography is the set of conventions for writing a language, including its script, spelling, and punctuation rules.
related: [dialect, script, writing-system, segmentation, input-method-editor, autonym]
status: voice-passed
version_added: 0.1
updated: 2026-06-19
contributors: [sam-gordashko]
further_reading:
  - title: "Orthography (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Orthography
    type: authority
  - title: "W3C Internationalization (i18n)"
    url: https://www.w3.org/International/
    type: authority
license: CC-BY-4.0
---

# Orthography

## Definition
Orthography is the set of conventions for writing a language, including its script, spelling, and punctuation rules.

## Why it matters
Orthography covers which [script](script.md) a language uses, how its sounds map to written symbols, and the rules for spelling, capitalization, and punctuation. It is the language-specific layer that sits on top of a script: the script is the toolkit of signs, the orthography is how one language agrees to use them. A single language can have more than one orthography, and orthographies get reformed over time, so the writing conventions for a language are not fixed facts you can hardcode.

## Example
Serbian can be written in two orthographies, [Cyrillic](cyrillic.md) and [Latin](latin-script.md), for the same language, and many Serbian speakers read both.

## Common mistake
Collapsing orthography into either "language" or "script" and assuming one implies the other. Picking a font with the right script glyphs does not guarantee the spelling, punctuation, and capitalization rules a particular language expects, and choosing a language code does not tell you which orthography a user wants. Serbian, Kurdish, and others genuinely use more than one.

## In practice
- **Treat orthography as configurable, not implied:** where a language has more than one orthography, let the choice be set (a locale variant, a user preference) rather than assuming the script from the language. This connects to [segmentation](segmentation.md) (word breaking and capitalization rules differ by orthography) and [input methods](input-method-editor.md) (how users type the orthography they want).
- **Punctuation and casing are orthography, not afterthoughts:** quotation marks, decimal separators, and capitalization conventions vary by language and orthography, so they belong in localization data, not in hardcoded UI strings.
- **Languages:** which orthographies a language uses, and which is current or preferred, is community-specific and changes over time. Treat it as expert-verified, and confirm specifics with the language cohort.

## Related terms
[Dialect](dialect.md) · [Script](script.md) · [Segmentation](segmentation.md) · [Input method editor (IME)](input-method-editor.md) · [Autonym](autonym.md)

## Further reading
- Foundations: [Orthography (Wikipedia)](https://en.wikipedia.org/wiki/Orthography)
- Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). "Writing system" is now its own node (see writing-system.md), so it is not an alias here. The three levels: a script is the sign set, a writing system is a script applied to one language with its rules, and orthography is the specific spelling, casing, and punctuation conventions within that writing system. Cohort to confirm this distinction and the multi-orthography examples (Serbian, Kurdish). -->
