---
term: Precomposed character
slug: precomposed-character
aliases: [composite character, canonical composite]
tags: [characters-encoding]
level: intermediate
depth: core
summary: A precomposed character is a single code point for a letter-plus-accent combination that could also be built from separate pieces.
related: [combining-mark, normalization, diacritic, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Precomposed Character (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#precomposed_character
    type: authority
license: CC-BY-4.0
---

## Definition
A precomposed character is a single code point for a letter-plus-accent combination that could also be built from separate pieces.

## Why it matters
Many accented letters exist as one code point even though the same shape can be assembled from a base letter plus a [combining-mark](combining-mark.md). Because text can mix the two representations, two strings that look identical may not be equal byte-for-byte, which quietly breaks comparison, search, and deduplication. [normalization](normalization.md) is what resolves it: NFC tends to prefer precomposed characters, while NFD decomposes them into base plus marks.

## Example
"é" can be one precomposed code point (U+00E9) or "e" plus a combining acute accent (U+0065 U+0301).

## Related terms
[combining-mark](combining-mark.md) · [normalization](normalization.md) · [diacritic](diacritic.md) · [code-point](code-point.md)

## Further reading
- Foundations: [Precomposed Character (Unicode Glossary)](https://www.unicode.org/glossary/#precomposed_character)
