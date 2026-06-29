---
term: Complex text layout
slug: complex-text-layout
aliases:
  - CTL
  - complex script rendering
level: advanced
depth: deep
summary: >-
  Complex text layout is rendering scripts where glyph shape, order, or position
  depends on surrounding characters rather than a simple left-to-right line.
related:
  - text-shaping
  - reordering
  - stacking-script
  - bidirectional-text
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Shaping concepts (HarfBuzz)
    url: https://harfbuzz.github.io/shaping-concepts.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Complex text layout

## Definition

Complex text layout is rendering scripts where glyph shape, order, or position depends on surrounding characters rather than a simple left-to-right line.

## Why it matters

Many scripts cannot be laid out by placing one fixed glyph after another. Arabic letters join and change form, Indic scripts reorder vowel marks and stack consonants into conjuncts, and right-to-left scripts need bidi handling. Supporting these needs a [shaping-engine](shaping-engine.md) plus fonts with the right [opentype](opentype.md) layout rules. Latin needs only minimal shaping by comparison, which is exactly why "complex text layout" is named as a distinct capability: it is the work a system has to do beyond the simple case.

## Example

Rendering the Devanagari "कि" requires moving the i-vowel mark to the left of the consonant it follows, which is complex text layout.

## Common mistake

Assuming that what works for English generalizes. A UI tested only in Latin can silently mangle complex scripts: glyphs that should join stay separate, vowel marks land in the wrong place, conjuncts fail to form. "It looks fine in English" is not evidence that text layout is correct.

## In practice

* **Rely on platform shaping, with the right fonts:** complex layout comes from the OS or browser shaping engine combined with fonts that carry the necessary OpenType tables. Your job is to not break that path (avoid manual glyph positioning, image-of-text shortcuts, or naive truncation) and to pick fonts with real [font-coverage](font-coverage.md) and shaping for the scripts you ship.
* **Test with real content:** include genuine Arabic, Indic, and other complex-script samples in design and QA, not Latin placeholder text. This connects to [reordering](reordering.md), [stacking-script](../language-terms/writing-systems-and-scripts/stacking-script.md)s, and [bidirectional-text](../language-terms/writing-systems-and-scripts/bidirectional-text.md).
* **Languages:** treat complex-script correctness as expert-verified, not assumed; confirm specifics with the language experts.

## Related terms

[Text shaping](text-shaping.md) · [Reordering](reordering.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md)

## Further reading

* Foundations: [Shaping concepts (HarfBuzz)](https://harfbuzz.github.io/shaping-concepts.html)
