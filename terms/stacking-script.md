---
term: Stacking script
slug: stacking-script
aliases: [vertical stacking, stacked consonants]
tags: [writing-systems-scripts, shaping-layout]
level: advanced
depth: core
summary: A stacking script writes a group of consonants as a vertical pile rather than side by side.
related: [conjunct, reordering, complex-text-layout, tsheg]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Tibetan Layout Requirements (W3C)"
    url: https://www.w3.org/TR/tlreq/
    type: authority
license: CC-BY-4.0
---

# Stacking script

## Definition

A stacking script writes a group of consonants as a vertical pile rather than side by side.

For example, [Tibetan](tibetan-script.md) draws the extra consonants of a stack directly below the main one, rather than writing them after it.

### Why it matters in design systems

Tibetan builds these stacks from separate [code points](code-point.md): one for the main consonant, and a different one for each consonant stacked beneath it.<sup>1</sup> Some Indic scripts also stack consonants, but by a different route: a [virama](../language-terms/writing-systems-and-scripts/virama.md) joins consonants into a [conjunct](conjunct.md) that the font may draw as a vertical stack.<sup>2</sup> Either way, the result is one tall shape instead of a row of separate consonants.

For a design system, the consequence is vertical. A stack rises and drops further than a single [symbol](../language-terms/writing-systems-and-scripts/symbol.md), so it needs more room and more careful [glyph](glyph.md) work to assemble the pieces into one shape. A common sign of weak support is a stack that breaks apart and sits in a row instead. So budget [line height](line-height.md) for the tallest stacks, and test that the [font](font.md) actually builds them, rather than carrying over assumptions from the Latin script. Because the stack has to be assembled rather than placed in sequence, this is a [complex text layout](complex-text-layout.md) behaviour, in the same family as [joining](../language-terms/writing-systems-and-scripts/joining.md) and [reordering](reordering.md).

Stacking is one of several [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) a script can have, and each language that uses the script also has its own [orthography](../language-terms/writing-systems-and-scripts/orthography.md), its spelling and punctuation conventions.

***

### Related terms and mentions

[Code point](code-point.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Font](font.md) · [Glyph](glyph.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Line height](line-height.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](reordering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tibetan script](tibetan-script.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Tibetan Layout Requirements (W3C)](https://www.w3.org/TR/tlreq/)

### Sources

1. A distinguishing feature of Tibetan is the set of separate code points for subjoined consonants, used to create consonant stacks; of the 77 combining characters in the Tibetan block, 48 represent subjoined consonant forms - Tibetan Layout Requirements (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
2. Unlike many other Indic scripts, modern Tibetan orthography does not use a virama to create stacks; in those scripts a virama joins consonants into a conjunct that a font may render as a vertical stack - Tibetan Layout Requirements (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
