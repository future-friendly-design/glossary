---
term: Stacking script
slug: stacking-script
aliases:
  - vertical stacking
  - stacked consonants
level: advanced
depth: core
summary: >-
  A stacking script writes a group of consonants as a vertical pile rather than
  side by side.
related:
  - conjunct
  - reordering
  - complex-text-layout
  - tsheg
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Tibetan Layout Requirements (W3C)
    url: https://www.w3.org/TR/tlreq/
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Stacking script

## Definition

A stacking script follows a script rule that vertically arranges the symbols within a consonant cluster (two or more consonants that come together with no vowel between them). The stacking script rule is independent of text direction, which may be horizontal.

For example, the Tibetan script writes the word རྒྱུད (rgyud, "string") with an initial stack of three consonants read top to bottom: the main consonant ga in the middle, ra stacked above it and ya below, followed by the vowel u and a suffix consonant da written to the right. The stack is vertical, yet the line runs left to right.<sup>1</sup>

Like all script rules, stacking script applies to any [language](../linguistics/language.md) using the [script](script.md) in its [writing system](writing-system.md).

While this glossary doesn't cover every script, here are some to be aware of that have a stacking script rule. You can select a linked term to navigate to its glossary page.

<sup>ADD TABLE HERE LIKE IN JOINING</sup>&#x20;

### Why it matters in design systems

For a design system to support stacking scripts, it has typographic and font design decisions to consider, as well as functional requirements on the development side.&#x20;

Displaying a stacking script correctly requires both a font that includes the stacked forms of the consonant glyphs and a shaping engine that assembles those separate glyphs into one vertical shape.&#x20;

Stacking scripts require more vertical space per character (single unit of text) than other scripts, so you'll want to be sure your tracking and line height values are tall enough to avoid clipping or cutting off the too of your tallest stacks.&#x20;

Because the stack is assembled rather than placed in sequence, this is a [complex text layout](../../terms/complex-text-layout.md) behaviour, in the same family as [joining](joining.md) and [reordering](../../terms/reordering.md). Stacking is just one of a script's [script rules](script-rules.md); each language that uses the script also has its own [orthography](orthography.md), the language-specific spelling and punctuation rules that apply on top of the script's behaviour

***

### Related terms and mentions

[Brahmic scripts](../../terms/brahmic-scripts.md) · [Code point](../../terms/code-point.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](../../terms/conjunct.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Joining](joining.md) · [Line height](../../terms/line-height.md) · [Orthography](orthography.md) · [Reordering](../../terms/reordering.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Tibetan script](../../terms/tibetan-script.md) · [Tsheg](../../terms/tsheg.md) · [Virama](virama.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Tibetan Layout Requirements (W3C)](https://www.w3.org/TR/tlreq/)

### Sources

1. A distinguishing feature of Tibetan is the set of separate code points for subjoined consonants, used to create consonant stacks; of the 77 combining characters in the Tibetan block, 48 represent subjoined consonant forms - Tibetan Layout Requirements (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
2. Unlike many other Indic scripts, modern Tibetan orthography does not use a virama to create stacks; in those scripts a virama joins consonants into a conjunct that a font may render as a vertical stack - Tibetan Layout Requirements (W3C) [https://www.w3.org/TR/tlreq/](https://www.w3.org/TR/tlreq/)
