---
term: Tsheg
slug: tsheg
aliases: [tsek, syllable dot]
tags: [writing-systems-scripts, shaping-layout]
level: intermediate
depth: core
summary: The tsheg is a small dot used in Tibetan script to separate syllables.
related: [complex-text-layout, stacking-script]
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

# Tsheg

## Definition
The tsheg is a small dot used in Tibetan script to separate syllables.

For example, the dot between the syllables in [Tibetan](tibetan-script.md) `བོད་ཡིག` is a tsheg.

### Why it matters in design systems
Tibetan does not put spaces between words. Instead a tsheg marks the boundary between syllables, and the unit of text between two tshegs is called a tsheg-bar.<sup>1</sup> Because many Tibetan words are a single syllable, the tsheg often behaves much like a space.

So for a design system, the tsheg is what line breaking and word finding have to key on instead of a space. A non-breaking variant also exists, so the layout engine has to treat the two differently when deciding where a line may break. That makes Tibetan another case where segmentation cannot follow Latin assumptions, part of [complex text layout](complex-text-layout.md).

***

### Related terms and mentions
[Complex text layout](complex-text-layout.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Stacking script](stacking-script.md) · [Tibetan script](tibetan-script.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading
- Foundations: [Requirements for Tibetan Text Layout (W3C)](https://www.w3.org/TR/tlreq/)

### Sources
1. Tibetan words comprise units called tsheg-bar (phonological syllables), separated using the mark U+0F0B Tibetan Mark Intersyllabic Tsheg - Requirements for Tibetan Text Layout (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
