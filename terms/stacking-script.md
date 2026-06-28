---
term: Stacking script
slug: stacking-script
aliases: [vertical stacking, stacked consonants]
tags: [writing-systems-scripts, shaping-layout]
level: advanced
depth: core
summary: A stacking script is one where consonants pile up vertically to form a cluster, as in Tibetan and many Indic scripts.
related: [conjunct, reordering, complex-text-layout, tsheg]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Requirements for Tibetan Text Layout (W3C)"
    url: https://www.w3.org/TR/tlreq/
    type: authority
license: CC-BY-4.0
---

# Stacking script

## Definition

A stacking script is one where consonants pile up vertically to form a cluster, as in Tibetan and many Indic scripts.

For example, a [Tibetan](tibetan-script.md) cluster draws a subjoined consonant below the root consonant rather than after it.

### Why it matters in design systems

In a stacking script, a consonant cluster is drawn with consonants placed above and below each other rather than side by side, forming a single vertical stack. Tibetan stacks a root consonant with subjoined consonants beneath it, using separate [characters](character.md) for those subjoined forms,<sup>1</sup> and Indic scripts can stack [conjuncts](conjunct.md) vertically.

To [typography](typography.md), that vertical pile is what complicates the layout: a stack rises and drops further than a single [symbol](../language-terms/writing-systems-and-scripts/symbol.md), so it needs more vertical room and more careful [glyph](glyph.md) composition. A practical tell of weak rendering support is a stack that comes apart and sits horizontally instead.

So for a design system, the lesson is that vertical space and [font](font.md) support need real testing for these scripts, not assumptions carried over from the Latin script. Budget [line height](line-height.md) for the tallest stacks, and check the font composes them rather than leaving the pieces side by side.

A quick thing to keep in mind: stacking is just one of a script's rules. A script usually has several, and they all apply to every language that uses it. So check the other [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) too, not only this page. After that, look at the [orthography](../language-terms/writing-systems-and-scripts/orthography.md) for each language you support: the language-specific layer, like its spelling and punctuation.

***

### Related terms and mentions

[Character](character.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Font](font.md) · [Glyph](glyph.md) · [Line height](line-height.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](reordering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tibetan script](tibetan-script.md) · [Tsheg](tsheg.md) · [Typography](typography.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Requirements for Tibetan Text Layout (W3C)](https://www.w3.org/TR/tlreq/)

### Sources

1. Tibetan uses separate code points for subjoined consonants to create consonant stacks; of the 77 combining characters in the Tibetan block, 48 represent subjoined consonant forms - Requirements for Tibetan Text Layout (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
