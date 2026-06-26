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

In several Indic and Brahmic scripts, the logical (typed) order of a vowel mark or a special consonant differs from its visual position, so the shaper has to move it during layout.<sup>1</sup> The classic cases are a left-side [matra](../language-terms/writing-systems-and-scripts/matra.md) that displays before its consonant and a [reph](reph.md) that jumps to the top of a cluster.

This is distinct from bidi reordering, which flips whole runs for right-to-left text; reordering rearranges characters within a single syllable.

So for a design system, the stake is that you cannot assume the order characters are stored in is the order they appear on screen. The shaper decides display position, which is why reordering is a core part of [complex text layout](complex-text-layout.md) and why string logic that counts from the stored order can break.

### Example

A [Devanagari](devanagari.md) left i-matra typed after its consonant is reordered to display before it.

### Common mistake

Assuming the order characters are stored in is the order they appear on screen. Within a reordering script it is not, so logic that walks a string by index, truncates it, or positions a cursor by counting from the start can land between characters that belong together and produce nonsense. Treat "where a character displays" as something the shaper decides, not something you can compute from the byte order.

### In practice

* **Never derive visual position from logical order:** for cursor movement, selection, and truncation in these scripts, rely on the platform's text APIs (which know the shaped result), not raw string indexing. This is the same discipline [grapheme cluster](grapheme-cluster.md) segmentation calls for, applied to order rather than counting.
* **Distinguish it from bidi:** [bidirectional text](bidirectional-text.md) reordering and intra-syllable reordering are different mechanisms; a layout can need both, so do not assume handling one covers the other.
* **Languages:** which sequences reorder is script- and language-specific; confirm behaviour with the language experts and test with real content rather than transliterations.

***

### Related terms and mentions

[Bidirectional text](bidirectional-text.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Grapheme cluster](grapheme-cluster.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reph](reph.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Stacking script](stacking-script.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. The Indic shaping engine reorders characters within a syllable cluster, for example moving a pre-base matra or a reph into its display position, after analysing the cluster - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
