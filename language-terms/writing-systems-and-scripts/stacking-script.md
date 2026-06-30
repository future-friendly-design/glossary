---
term: Stacking script
slug: stacking-script
aliases:
  - vertical stacking
  - stacked consonants
level: advanced
depth: core
summary: >-
  A stacking script follows a script rule that vertically arranges the symbols
  within a consonant cluster.
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

A stacking script follows a script rule that vertically arranges the symbols within a consonant cluster. A cluster is two or more consonants that come together with no vowel between them. This stacking is independent of text direction, which can still run horizontally.

For example, the Tibetan script writes the word རྒྱུད (rgyud, "string") as an initial stack of three consonants read top to bottom: ra on top, the main consonant ga in the middle, and ya below, with the vowel u beneath the stack and a suffix consonant da to the right. The stack is vertical, yet the line runs left to right.<sup>1</sup>

Like all script rules, stacking applies to any [language](../linguistics/language.md) using the [script](script.md) in its [writing system](writing-system.md).

While this glossary doesn't cover every script, here are some to be aware of that have a stacking script rule. You can select a linked term to navigate to its glossary page.

| Script                                   | Languages          | How stacking works here                                                                                                         | Example |
| ---------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------- | ------- |
| [Tibetan](../../terms/tibetan-script.md) | Tibetan, Dzongkha  | Subjoined consonant forms pile below a root consonant, and a superscript consonant can sit above it.                            | རྒྱུད   |
| Khmer                                    | Khmer, Pali        | A second consonant takes a subscript form, called coeng, written below the base consonant.                                      | ស្ន     |
| Myanmar                                  | Burmese, Mon, Shan | A second consonant is written below the first to mark a cluster with no vowel between them, mostly in words borrowed from Pali. | ဗុဒ္ဓ   |

### Why it matters in design systems

For a design system to support stacking scripts, it has typographic and font design decisions to consider, as well as functional requirements on the development side.

Displaying a stacking script correctly requires both a [font](../../terms/font.md) that includes the stacked forms of the consonant [glyphs](../../terms/glyph.md) and a [shaping engine](../../terms/shaping-engine.md) that assembles those separate glyphs into one vertical shape.<sup>2</sup>

Because a stack piles several consonants into one shape, it is taller than a single consonant and needs more vertical room. Set your [line height](../../terms/line-height.md) tall enough that the tallest stacks are not clipped.

Because the stack is assembled rather than placed in sequence, this is a [complex text layout](../../terms/complex-text-layout.md) behaviour, in the same family as [joining](joining.md) and [reordering](../../programming-terms/reordering.md). Stacking is just one of a script's [script rules](script-rules.md); each language that uses the script also has its own [orthography](orthography.md), the language-specific spelling and punctuation rules that apply on top of the script's behaviour.

***

### Related terms and mentions

[Brahmic scripts](../../terms/brahmic-scripts.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](conjunct.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Joining](joining.md) · [Language](../linguistics/language.md) · [Line height](../../terms/line-height.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../terms/shaping-engine.md) · [Symbol](symbol.md) · [Tibetan script](../../terms/tibetan-script.md) · [Tsheg](../../terms/tsheg.md) · [Virama](virama.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Tibetan Layout Requirements (W3C)](https://www.w3.org/TR/tlreq/)

### Sources

1. A Tibetan stack places a superscript consonant above the root consonant and a subjoined consonant below it, and Tibetan text runs left to right in horizontal lines - Tibetan script notes (r12a.github.io) [https://r12a.github.io/scripts/tibt/bo.html](https://r12a.github.io/scripts/tibt/bo.html)
2. Stacks are assembled at display time: in Khmer the stacking behaviour is driven by a control character (U+17D2) that has no visual form of its own, which the rendering system uses to write the following consonant as a subscript below the base, so the font must supply those subscript glyph forms - Khmer script notes (r12a.github.io) [https://r12a.github.io/scripts/khmr/km.html](https://r12a.github.io/scripts/khmr/km.html)
