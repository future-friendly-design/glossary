---
term: Abjad
slug: abjad
aliases: [consonantal alphabet]
tags: [writing-systems-scripts]
level: intermediate
depth: core
summary: An abjad is a script in which each letter represents a consonant and vowels are usually left unwritten.
related: [alphabet, abugida, script]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Glossary: Abjad"
    url: https://www.unicode.org/glossary/#abjad
    type: authority
license: CC-BY-4.0
---

## Definition
An abjad is a script in which each letter represents a consonant and vowels are usually left unwritten.

## Why it matters
In an abjad the consonant symbols are primary and vowel sounds are typically omitted, or only optionally shown with [diacritic](diacritic.md) marks. Arabic and Hebrew, the two abjads most relevant to interface work, are both written right to left, so supporting them brings in [bidirectional text](bidirectional-text.md) handling on top of the script's own behavior. The fact that short vowels are normally unwritten also affects how search, matching, and text input work for these scripts.

## Example
In written Arabic and Hebrew, short vowels are normally omitted, so the reader supplies them from context. "Pure" abjads such as early Phoenician mark no vowels at all, while Arabic and Hebrew can add optional vowel marks.

## Related terms
[Alphabet](alphabet.md) · [Abugida](abugida.md) · [Script](script.md)

## Further reading
- Foundations: [Unicode Glossary: Abjad](https://www.unicode.org/glossary/#abjad)
