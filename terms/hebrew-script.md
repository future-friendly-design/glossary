---
term: Hebrew script
slug: hebrew-script
aliases: [hebrew]
tags: [writing-systems-scripts]
level: intermediate
depth: core
summary: "The Hebrew script is a right-to-left abjad used for Hebrew and several other languages, with optional vowel points written below and around the consonants."
related: [abjad, arabic-script, bidirectional-text, text-direction, diacritic]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Hebrew alphabet (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Hebrew_alphabet
    type: authority
license: CC-BY-4.0
---

# Hebrew script

## Definition
The Hebrew script is a right-to-left abjad used for Hebrew and several other languages, with optional vowel points written below and around the consonants.

## Why it matters
Like the [Arabic script](arabic-script.md), the Hebrew script is an [abjad](abjad.md): the letters are consonants, and the short vowels are normally left unwritten or shown only as optional points (niqqud) added around the base letters. It runs right to left, which is why it comes up beside Arabic any time you deal with [bidirectional text](bidirectional-text.md): the moment a Hebrew line includes a Latin brand name or a number, your layout has to handle runs going in two directions at once. One thing it does not share with Arabic is cursive joining; Hebrew letters stay separate. Five letters do take a distinct final form at the end of a word, which the shaper selects automatically.

## Example
A Hebrew sentence with the English word "email" and a price in digits needs the bidirectional algorithm to keep each run in the right order, so the Hebrew reads right to left while "email" and the number stay left to right.

## Related terms
[Abjad](abjad.md) · [Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Text direction](text-direction.md) · [Diacritic](diacritic.md)

## Further reading
- Foundations: [Hebrew alphabet (Wikipedia)](https://en.wikipedia.org/wiki/Hebrew_alphabet)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). Upgrade to an authoritative primary (Unicode Standard Section 9.1 Hebrew, ScriptSource: Hebr) vetted by the SILCON cohort. The set of languages written in the Hebrew script (beyond Hebrew, e.g. Yiddish, Ladino) is a script-to-language mapping to confirm; no letter counts are asserted. -->
