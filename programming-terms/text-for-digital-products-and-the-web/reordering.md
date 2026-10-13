---
term: Reordering
slug: reordering
aliases:
  - glyph reordering
  - character reordering
level: advanced
depth: deep
summary: >-
  Reordering is when a shaping engine changes the display order of characters
  relative to how they were typed.
related:
  - matra
  - reph
  - stacking-script
  - complex-text-layout
  - bidirectional-text
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Reordering

## Definition

Reordering is when a shaping engine changes the display order of characters relative to how they were typed.

### Why it matters in design systems

In several Indic and Brahmic scripts, the logical (typed) order of a vowel mark or a special consonant differs from its visual position, so the shaper has to move it during layout.<sup>1</sup> The classic cases are a left-side [matra](../../language-terms/writing-systems-and-scripts/matra.md) that displays before its consonant and a [reph](../../language-terms/writing-systems-and-scripts/reph.md) that jumps to the top of a cluster.<sup>2</sup>

This is distinct from bidi reordering, which flips whole runs for right-to-left text; reordering rearranges characters within a single syllable.

So for a design system, the stake is that you cannot assume the order characters are stored in is the order they appear on screen. The shaper decides display position, which is why reordering is a core part of [complex text layout](complex-text-layout.md) and why string logic that counts from the stored order can break.

### Example

A [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) left i-matra typed after its consonant is reordered to display before it.

### Common mistake

Assuming the order characters are stored in is the order they appear on screen. Within a reordering script it is not, so logic that walks a string by index, truncates it, or positions a cursor by counting from the start can land between characters that belong together and produce nonsense. Treat "where a character displays" as something the shaper decides, not something you can compute from the stored order.

### In practice

* **Never derive visual position from logical order:** for cursor movement, selection, and truncation in these scripts, rely on the platform's text APIs (which know the shaped result), not raw string indexing. This is the same discipline [grapheme cluster](../text-in-software/grapheme-cluster.md) segmentation calls for, applied to order rather than counting.
* **Distinguish it from bidi:** [bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) reordering and intra-syllable reordering are different mechanisms; a layout can need both, so do not assume handling one covers the other.
* **Languages:** which sequences reorder is script- and language-specific; confirm behaviour with the language experts and test with real content rather than transliterations.

***

### Related terms and mentions

[Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Brahmic scripts](../../language-terms/writing-systems-and-scripts/brahmic-scripts.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Grapheme cluster](../text-in-software/grapheme-cluster.md) · [Language](../../language-terms/linguistics/language.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Reph](../../language-terms/writing-systems-and-scripts/reph.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../text-in-software/segmentation.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Text shaping](text-shaping.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. "Because Devanagari and other Indic scripts have some dependent vowels that must be depicted to the left side of their consonant letter, the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
2. "Reph - The above-base form of the letter "Ra" that is used in Devanagari when "Ra" is the first consonant in the syllable and is not the base consonant" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
