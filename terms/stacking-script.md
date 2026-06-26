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

For example, a [Tibetan](tibetan-script.md) cluster draws a subjoined consonant directly beneath the root letter rather than after it.

### Why it matters in design systems

In a stacking script, a consonant cluster is drawn with letters placed above and below each other rather than side by side, forming a single vertical stack. Tibetan stacks a root letter with subjoined consonants beneath it, using separate characters for those subjoined forms,<sup>1</sup> and Indic scripts can stack [conjuncts](conjunct.md) vertically.

To [typography](typography.md), that vertical pile is what complicates the layout: a stack rises and drops further than a single letter, so it needs more vertical room and more careful glyph composition. A practical tell of weak rendering support is a stack that comes apart and sits horizontally instead.

So for a design system, the lesson is that vertical space and font support need real testing for these scripts, not Latin assumptions. Budget [line height](line-height.md) for the tallest stacks, and check the font composes them rather than leaving the pieces side by side.

***

### Related terms and mentions

[Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Line height](line-height.md) · [Reordering](reordering.md) · [Tibetan script](tibetan-script.md) · [Tsheg](tsheg.md) · [Typography](typography.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Requirements for Tibetan Text Layout (W3C)](https://www.w3.org/TR/tlreq/)

### Sources

1. Tibetan uses separate code points for subjoined consonants to create consonant stacks; of the 77 combining characters in the Tibetan block, 48 represent subjoined consonant forms - Requirements for Tibetan Text Layout (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
