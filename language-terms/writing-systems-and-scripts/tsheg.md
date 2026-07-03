---
term: Tsheg
slug: tsheg
aliases:
  - tsek
  - syllable dot
level: intermediate
depth: core
summary: The tsheg is a punctuation symbol used in Tibetan script to separate syllables.
related:
  - complex-text-layout
  - stacking-script
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Tibetan Script Resources (W3C)
    url: https://www.w3.org/TR/tibt-lreq/
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Tsheg

## Definition

The tsheg is a punctuation symbol used in Tibetan script to separate syllables.

For example, the dot between the syllables in [Tibetan](../../terms/tibetan-script.md) `བོད་ཡིག` is a tsheg.

### Why it matters in design systems

Tibetan does not put spaces between words. Instead a tsheg marks the boundary between syllables, and the unit of text between two tshegs is called a tsheg-bar.<sup>1</sup> Because many Tibetan words are a single syllable, the tsheg often behaves much like a space.

So for a design system, the tsheg is what line breaking and word finding have to key on instead of a space. A non-breaking variant also exists, so the layout engine has to treat the two differently when deciding where a line may break. That makes Tibetan another case where [segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) cannot follow Latin assumptions, part of [complex text layout](../../terms/complex-text-layout.md).

***

### Related terms and mentions

[Complex text layout](../../terms/complex-text-layout.md) · [Punctuation mark](punctuation-mark.md) · [Script rules](script-rules.md) · [Segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Stacking script](stacking-script.md) · [Symbol](symbol.md) · [Tibetan script](../../terms/tibetan-script.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Tibetan Script Resources (W3C)](https://www.w3.org/TR/tibt-lreq/)

### Sources

1. Tibetan words comprise units called tsheg-bar, basically phonological syllables, separated using the character U+0F0B (Unicode name: Tibetan Mark Intersyllabic Tsheg) - Tibetan Script Resources (W3C) [https://www.w3.org/TR/tibt-lreq/](https://www.w3.org/TR/tibt-lreq/)
