---
term: Harakat
slug: harakat
aliases: [tashkil, arabic vowel marks]
tags: [writing-systems-scripts]
level: advanced
depth: core
summary: "Harakat are the optional vowel marks of the Arabic script, small signs written above and below the consonants to show short vowels."
related: [arabic-script, abjad, diacritic, mark, combining-mark]
status: draft
version_added: 0.1
updated: 2026-06-21
contributors: [sam-gordashko]
further_reading:
  - title: "Harakat (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#harakat
    type: authority
license: CC-BY-4.0
---

# Harakat

## Definition
Harakat are the optional vowel marks of the Arabic script, small signs written above and below the consonants to show short vowels.

## Why it matters
The [Arabic script](arabic-script.md) is an [abjad](abjad.md): it writes consonants and long vowels, while short vowels are normally left out and supplied by the reader. Harakat (part of a larger set of marks called tashkil) are the optional signs that spell those short vowels out when needed, for example in the Quran, in children's books, in dictionaries, and anywhere ambiguity has to be removed. They are combining [mark](mark.md)s layered on the base letters, so in software a letter plus its harakat is a sequence, not a single precomposed character, and Unicode advises always representing them that way. That has direct consequences: search and matching usually need to ignore harakat so a word is found whether or not it is voweled, and input methods have to let users add the marks.

## Example
The same sequence of Arabic consonants can be read as different words; adding harakat above and below them fixes which short vowels are meant.

## Related terms
[Arabic script](arabic-script.md) · [Abjad](abjad.md) · [Diacritic](diacritic.md) · [Mark](mark.md) · [Combining mark](combining-mark.md)

## Further reading
- Foundations: [Harakat (Unicode Glossary)](https://www.unicode.org/glossary/#harakat)

<!-- NEEDS EXPERT REVIEW: Unicode glossary anchor confirmed to exist. The relationship between harakat and the broader tashkil set, and the contexts where vowel marks are conventionally used, should be confirmed by the SILCON cohort. -->
