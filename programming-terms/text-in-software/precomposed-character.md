---
term: Precomposed character
slug: precomposed-character
aliases:
  - composite character
  - canonical composite
level: intermediate
depth: core
summary: A precomposed character is a single character that already has its accent built in, rather than a plain letter followed by a separate accent character.
related:
  - combining-mark
  - normalization
  - diacritic
  - code-point
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Precomposed Character (Unicode Glossary)
    url: https://www.unicode.org/glossary/#precomposed_character
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Precomposed character

## Definition

A precomposed character is a single [character](character.md) that already has its accent built in, rather than a plain letter followed by a separate accent character.

## Why it matters

There are two ways to store `é`. The first is as one character of its own, with its own number in [Unicode](unicode.md)'s list (the [code point](code-point.md) U+00E9), meaning "e with an acute accent". The second is as the plain letter `e` followed by a second character, a [combining mark](combining-mark.md), whose only job is to add an accent to whatever came before it. A precomposed character is the first way.

Both come out looking the same on screen, and neither is wrong. The trouble is that software comparing two pieces of text normally compares them piece by piece, so the one-character `é` and the two-character `é` do not match, even though a reader would say they are the same word. That is what quietly breaks comparison, search, deduplication, and "have I seen this name before" checks.

[Normalization](normalization.md) is what resolves it: rewrite both into the same chosen form before comparing anything. Of Unicode's forms, NFC tends to prefer precomposed characters, while NFD takes them apart into a base letter plus separate marks.

## Example

`é` can be one precomposed character (U+00E9) or `e` plus a combining acute accent (U+0065 U+0301).

## Related terms

[Character](character.md) · [Code point](code-point.md) · [Combining mark](combining-mark.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Normalization](normalization.md) · [Unicode](unicode.md)

## Further reading

* Foundations: [Precomposed Character (Unicode Glossary)](https://www.unicode.org/glossary/#precomposed_character)
