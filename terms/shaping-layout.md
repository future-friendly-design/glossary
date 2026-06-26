---
term: Shaping & layout
slug: shaping-layout
aliases: []
level: foundational
entry_type: overview
summary: >-
  Shaping and layout are how a string of characters becomes correctly formed,
  ordered, and positioned glyphs on the line, the work a font and shaping engine
  do beyond simply placing one letter after another.
related:
  - typography
  - characters-encoding
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: What is HarfBuzz? (HarfBuzz)
    url: https://harfbuzz.github.io/what-is-harfbuzz.html
    type: authority
license: CC-BY-4.0
---

# Shaping & layout

## Definition

Shaping and layout are how a string of characters becomes correctly formed, ordered, and positioned glyphs on the line, the work a font and shaping engine do beyond simply placing one letter after another.

## Why it matters

For Latin text it is easy to assume rendering is just "draw each character in order," and that assumption quietly breaks for much of the world's writing. Arabic letters join and change shape, Indic scripts reorder vowel signs and fuse consonants into conjuncts, Tibetan stacks letters vertically, and ligatures fuse pairs even in Latin. Getting this right is what separates software that genuinely supports a language from software that merely stores its characters. This category covers the machinery (the OpenType format and its tables, the shaping engine) and the script-specific behaviors that machinery exists to handle, so you can reason about why complex text renders the way it does and what it takes to support it.

## Key terms

A guided tour of the shaping and layout terms in this glossary, grouped by what they help you reason about:

* **The shaping pipeline:** [Text shaping](text-shaping.md), [Shaping engine](shaping-engine.md), [Complex text layout](complex-text-layout.md), [Reordering](reordering.md)
* **The OpenType format and its tables:** [OpenType](opentype.md), [OpenType features](opentype-features.md), [GSUB](gsub.md), [GPOS](gpos.md)
* **Joining and combining glyphs:** [Ligature](ligature.md), [Conjunct](conjunct.md)
* **Indic script features:** [Matra](../language-terms/writing-systems-and-scripts/matra.md), [Reph](reph.md), [Shirorekha](shirorekha.md), [Virama](../language-terms/writing-systems-and-scripts/virama.md)
* **Tibetan and vertical stacking:** [Tsheg](tsheg.md), [Stacking script](stacking-script.md)

## Further reading

* Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)
