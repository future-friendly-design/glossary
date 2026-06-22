---
term: Nukta
slug: nukta
aliases: []
tags: [shaping-layout]
level: advanced
depth: core
summary: "A nukta is a dot added below a consonant in many Indic scripts to extend the script to sounds the base letters do not cover."
related: [matra, virama, diacritic, mark, devanagari]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Nuqta (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Nuqta
    type: authority
license: CC-BY-4.0
---

# Nukta

## Definition
A nukta is a dot added below a consonant in many Indic scripts to extend the script to sounds the base letters do not cover.

## Why it matters
A nukta (the word means "dot") is a small combining sign that sits beneath a consonant and changes the sound it represents, letting an [abugida](abugida.md) such as Devanagari write sounds borrowed from other languages without inventing whole new letters. It belongs to the same family of attached signs as the vowel sign ([matra](matra.md)) and the vowel-killer ([virama](virama.md)). For software, the practical points are that a base letter plus a nukta can often also exist as a single precomposed character, which is a normalization concern, and that the nukta is one more combining [mark](mark.md) the shaper has to position correctly.

## Example
In Devanagari, adding a nukta under a consonant turns it into a related sound used mainly in loanwords, while the rest of the letter stays the same.

## Related terms
[Matra](matra.md) · [Virama](virama.md) · [Diacritic](diacritic.md) · [Mark](mark.md) · [Devanagari](devanagari.md)

## Further reading
- Foundations: [Nuqta (Wikipedia)](https://en.wikipedia.org/wiki/Nuqta)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). Upgrade to an authoritative primary (Unicode Standard Section 12.1 Devanagari, Unicode glossary) vetted by the SILCON cohort. The specific scripts that use a nukta and the exact sounds it produces are script-to-language details to confirm; no inventory of affected letters is asserted. -->
