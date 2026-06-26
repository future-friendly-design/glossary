---
term: Script rules
slug: script-rules
aliases:
  - script behaviors
  - script-specific behavior
level: foundational
depth: deep
summary: >-
  Script rules define the behaviour of individual visual elements of a script
  (its symbols, including marks).
related:
  - script
  - complex-text-layout
  - text-direction
  - joining
  - reordering
  - stacking-script
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Internationalization (W3C)
    url: https://www.w3.org/International/
    type: authority
  - title: The Unicode Standard (latest version)
    url: https://www.unicode.org/versions/latest/
    type: code
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Script rules

## Definition

Script rules define the behaviour of individual visual elements of a [script](script.md) (its [symbols](symbol.md), including [marks](mark.md)). They determine possible combinations and positioning of symbols, layout and direction for any language using the script in its [writing system](writing-system.md).

Each writing system defines additional rules on how to use a script for a specific language, known as [orthography](orthography.md). This means each written language has two sets of rules to consider, the script rules and its orthography.

While this glossary doesn't cover every script rule (or every script), here's a list of script rule terms you may want to explore:

| Script rule | What it does | Example | Learn more |
| --- | --- | --- | --- |
| Direction | which way the script runs: left to right, right to left, or top to bottom | [Arabic](../../terms/arabic-script.md) runs right to left; Japanese [tategaki](../../terms/tategaki.md) runs top to bottom | [Text direction](../../terms/text-direction.md) |
| Joining | whether letters connect and change shape by their position in a word | Arabic letters join: ب ح ث → بحث | [Joining](joining.md) |
| Combination | how [marks](../../programming-terms/combining-mark.md) attach to symbols and how symbols cluster or fuse | [Devanagari](../../terms/devanagari.md) conjuncts | [Conjunct](../../terms/conjunct.md) |
| Ordering | when the order symbols are stored in differs from the order they are displayed in | Indic [reph](../../terms/reph.md) | [Reordering](../../terms/reordering.md) |
| Stacking | how symbols pile into a vertical stack | [Tibetan](../../terms/tibetan-script.md) stacks | [Stacking script](../../terms/stacking-script.md) |
| Breaking | how the script marks word and line boundaries, which is not always a space | [Thai](../../terms/thai-script.md) has no word spaces | [Segmentation](../../terms/segmentation.md) |

### Why it matters in design systems

You do not choose a script rule; the script imposes it. But you do have to design around it, and that touches real decisions: which way a layout mirrors, how much [line height](../../terms/line-height.md) a stacked script needs, and whether your font and layout engine can join or reorder the letters.

To a linguist, these behaviours are properties of the script, shared by every language written in it.

To [typography](../../terms/typography.md), each rule is work the font and the layout engine have to do: the font must carry the joined, stacked, or reordered forms, and the engine has to apply them during [shaping](../../terms/text-shaping.md).

To a design tool, the rules are the catch. Many tools display the characters of a script but never apply its behaviours, so a prototype can look correct in a glyph table and still render wrong in a real sentence.

So covering a script's symbols is necessary but not sufficient. The rules that direct, join, reorder, and stack those symbols have to be applied too, which is the heart of [complex text layout](../../terms/complex-text-layout.md).

### Example

The Arabic script runs right to left, joins its letters into cursive forms that change by position, and places short vowel marks above and below the letters.<sup>1</sup> A designer prototyping an Arabic interface has to account for all three behaviours before any Arabic-language spelling rules enter the picture, because they are properties of the script, not the language.

### Common mistake

Treating script rules and orthography as the same thing. Script rules belong to the script and hold for every language written in it. Orthography belongs to one language. The Latin script runs left to right whether you write English or Vietnamese, so direction is a script rule. The spelling, capitalization, and diacritic conventions change between those two languages, so those are orthography. Switch the language and the orthography changes while the script rules stay put.

### In practice

* **Walk the six behaviours for your focus script:** does it run right to left, do its letters join, do marks stack on the symbols, does anything reorder, does it form vertical stacks, and how does it break into words. The answers tell you what your tool and fonts must support before you build.
* **Test with a real word, not a single letter:** many tools show the characters but do not apply the rules, so a glyph table can look correct while a real sentence renders wrong. Type a real word in your design tool and confirm it shapes.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Combining mark](../../programming-terms/combining-mark.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](../../terms/conjunct.md) · [Devanagari](../../terms/devanagari.md) · [Font](../../terms/font.md) · [Joining](joining.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Reordering](../../terms/reordering.md) · [Reph](../../terms/reph.md) · [Script](script.md) · [Segmentation](../../terms/segmentation.md) · [Stacking script](../../terms/stacking-script.md) · [Symbol](symbol.md) · [Tategaki](../../terms/tategaki.md) · [Text direction](../../terms/text-direction.md) · [Text shaping](../../terms/text-shaping.md) · [Thai script](../../terms/thai-script.md) · [Tibetan script](../../terms/tibetan-script.md) · [Typography](../../terms/typography.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)
* Code & specs: [The Unicode Standard (latest version)](https://www.unicode.org/versions/latest/)

### Sources

1. The Arabic script is written right to left and its letters take contextual joined forms (isolated, initial, medial, final); diacritic marks are positioned above and below the base letters - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
