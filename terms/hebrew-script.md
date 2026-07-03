---
term: Hebrew script
slug: hebrew-script
aliases:
  - hebrew
level: intermediate
depth: core
summary: >-
  The Hebrew script is a right-to-left abjad used for Hebrew and several other
  languages, with optional vowel points written below and around the consonants.
related:
  - abjad
  - arabic-script
  - bidirectional-text
  - text-direction
  - diacritic
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Hebrew alphabet (Wikipedia)
    url: https://en.wikipedia.org/wiki/Hebrew_alphabet
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Hebrew script

## Definition

The Hebrew script is a right-to-left abjad used for Hebrew and several other languages, with optional vowel points written below and around the consonants.

## Why it matters

Like the [Arabic script](arabic-script.md), the Hebrew script is an [abjad](../language-terms/writing-systems-and-scripts/abjad.md): the letters are consonants, and the short vowels are normally left unwritten or shown only as optional points (niqqud) added around the base letters. It runs right to left, which is why it comes up beside Arabic any time you deal with [bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md): the moment a Hebrew line includes a Latin brand name or a number, your layout has to handle runs going in two directions at once. One thing it does not share with Arabic is cursive joining; Hebrew letters stay separate. Five letters do take a distinct final form at the end of a word, which the shaper selects automatically.

## Example

A Hebrew sentence with the English word "email" and a price in digits needs the bidirectional algorithm to keep each run in the right order, so the Hebrew reads right to left while "email" and the number stay left to right.

## Related terms

[Abjad](../language-terms/writing-systems-and-scripts/abjad.md) · [Arabic script](arabic-script.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md)

## Further reading

* Foundations: [Hebrew alphabet (Wikipedia)](https://en.wikipedia.org/wiki/Hebrew_alphabet)
