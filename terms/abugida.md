---
term: Abugida
slug: abugida
aliases: [alphasyllabary]
tags: [writing-systems-scripts]
level: intermediate
depth: core
summary: An abugida is a script where each consonant carries a built-in vowel that is changed by adding marks.
related: [alphabet, abjad, syllabary, brahmic-scripts, matra]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Glossary: Abugida"
    url: https://www.unicode.org/glossary/#abugida
    type: authority
license: CC-BY-4.0
---

## Definition
An abugida is a script where each consonant carries a built-in vowel that is changed by adding marks.

## Why it matters
Unlike an [[alphabet]], which gives consonants and vowels separate letters, an abugida attaches vowel signs to a base consonant that has a default inherent vowel. Most [[brahmic-scripts|Brahmic scripts]], such as Devanagari and Thai, work this way. This matters for layout because those attached vowel signs (called [[matra]]s) can sit to the left, right, above, or below the consonant, and one typed after its consonant may need to display before it. That reordering and mark placement is why abugidas need real shaping support rather than simple left-to-right glyph placement.

## Example
In Devanagari, the consonant "k" carries an inherent "a"; a vowel sign changes it to "ki" or "ku".

## Related terms
[[alphabet]] · [[abjad]] · [[syllabary]] · [[brahmic-scripts]] · [[matra]]

## Further reading
- Foundations: [Unicode Glossary: Abugida](https://www.unicode.org/glossary/#abugida)
