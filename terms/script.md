---
term: Script
slug: script
aliases: []
tags: [writing-systems-scripts]
level: foundational
depth: deep
summary: A script is the set of visual symbols and rules used to write one or more languages.
related: [alphabet, abugida, abjad, syllabary, logographic, featural-alphabet, brahmic-scripts, font-coverage, writing-system, script-typeface]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Glossary: Script"
    url: https://www.unicode.org/glossary/#script
    type: authority
license: CC-BY-4.0
---

# Script

{% hint style="info" %}
This is the writing-systems sense of "script." For the type-design classification, see [Script (typeface)](script-typeface.md); the computing sense (a program) is out of scope in this glossary. A script applied to one language with its spelling and punctuation rules is a [writing system](writing-system.md).
{% endhint %}

## Definition
A script is the set of visual symbols and rules used to write one or more languages.

## Why it matters
Script and language are not the same thing, and conflating them is one of the most common mistakes in interface work. A single script can serve many languages (the Latin script writes English, Vietnamese, and Swahili), and a single language can be written in more than one script. Scripts are classified by what each sign represents: [alphabet](alphabet.md)s, [abugida](abugida.md)s, [abjad](abjad.md)s, [syllabaries](syllabary.md), and [logographic](logographic.md) systems each behave differently when it comes to spacing, line height, input, and font support. For a design system that means the unit you actually have to support is the script, not the country or the language, and the scripts you choose to cover define the typographic and engineering work ahead.

## Example
English, Vietnamese, and Turkish are all written with the same script (Latin) but are different languages. Conversely, Serbian is written in both Cyrillic and Latin.

## Common mistake
Treating "languages supported" as the planning unit and assuming a font or layout that works for one language works for the rest. Coverage is per script: a typeface that handles English fine may have no glyphs for Devanagari or Arabic, and a layout that works left to right may break entirely for a right-to-left or [stacking](stacking-script.md) script.

## In practice
- **Plan support by script, then verify [font-coverage](font-coverage.md):** the question "do we support Hindi?" is really "do our fonts and shaping cover Devanagari, and does our layout handle its reordering and conjuncts?" Pick fonts with genuine coverage for every script you ship, not just Latin.
- **Do not assume Latin defaults:** spacing, capitalization, line breaking, and input all vary by script. What looks correct in English is not evidence the script is rendering correctly.
- **Languages:** which languages use which script, and the finer points of each script's behavior, are exactly the material the language cohort verifies. NEEDS EXPERT REVIEW for any specific script-to-language mapping you rely on.

## Related terms
[Alphabet](alphabet.md) · [Abugida](abugida.md) · [Abjad](abjad.md) · [Syllabary](syllabary.md) · [Logographic](logographic.md) · [Featural alphabet](featural-alphabet.md) · [Brahmic scripts](brahmic-scripts.md) · [Font coverage](font-coverage.md)

## Further reading
- Foundations: [Unicode Glossary: Script](https://www.unicode.org/glossary/#script)
