---
term: Legibility
slug: legibility
aliases: []
level: foundational
depth: deep
summary: Legibility is how easily a reader can tell one character apart from another.
related: [readability, glyph, typeface, x-height, symbol]
status: voice-passed
version_added: 0.1
updated: 2026-06-25
contributors: [sam-gordashko]
further_reading:
  - title: "Legibility, Readability, and Comprehension (Nielsen Norman Group)"
    url: https://www.nngroup.com/articles/legibility-readability-comprehension/
    type: authority
license: CC-BY-4.0
tags: [typography]
---

# Legibility

## Definition

Legibility is how easily a reader can tell one character apart from another.

It is a typographic property decided at the level of the individual [symbol](../language-terms/writing-systems-and-scripts/symbol.md): whether a lowercase "l" can be mistaken for a capital "I" or the digit "1", an "O" for a "0". It lives in the [typeface](typeface.md) and its [glyph](glyph.md) shapes, so it is set by font choice and letterform style: weight, [x-height](x-height.md), how open the counters are, whether the zero is slashed. Its partner is [readability](readability.md), how comfortably a reader moves through whole lines and paragraphs; legibility is the zoomed-in view, readability the zoomed-out one.

## Why it matters in design systems

It is tempting to file legibility under "a nice font", but it is specific and testable, and it is decided by choices a design system controls. The typeface comes first: some faces draw "I l 1" or "O 0" as near-twins, others keep them apart, and that is a legibility decision before it is a brand one. Font setup comes second: many families ship a slashed zero, a single-story "a", or a dotted "i" as stylistic alternates you can switch on where a misread is costly. Size and context come third: a face that is crisp on a specimen can blur at 12px on a low-resolution screen, so legibility has to be judged where the text ships, not where it is shown off. And it is not readability: a font can be flawlessly legible, every character distinct, and still be a tiring wall of text if the spacing and measure are wrong. Legibility is necessary, not sufficient.

## Example

The everyday legibility failures are confusable pairs: lowercase "l", capital "I", and digit "1" collapsing into one stroke, or "O" and "0" swapping, which is why password fields, part numbers, and verification codes are where illegibility does real harm. The fix is usually a font choice or an alternate glyph, not new copy. And it is contextual: a face that separates those shapes cleanly at 72px can still merge them at the size and contrast of a real phone, so legibility belongs to the type in its setting, not the type alone. NN/g places legibility at the lowest level of content usability, the layer that decides whether a reader can recognize the characters at all before anything else about the text can matter.<sup>1</sup>

## Common mistake

Treating legibility and readability as the same thing, or as "how good the font looks". They are separate and can move in opposite directions: a distinctive display face can be very legible, every letter unmistakable, yet unreadable set as a paragraph, while a plain, legible text face can be made unreadable by cramped leading or an over-long line. Diagnose them apart. If single characters get misread, that is legibility, fix the typeface or the glyph. If the page is tiring to read, that is readability, fix the spacing and layout.

## In practice

* **Choose the typeface for its hard cases, not its headline:** set the confusable pairs ("Il1", "O0", "rn" against "m") in the real face at the smallest size they will ship, and check that they hold apart. The hero-size specimen hides exactly the failures that bite.
* **Switch on the alternates that fix legibility:** many fonts carry a slashed or dotted zero, a single-story "a", or a disambiguated "l" as OpenType stylistic sets. Turn them on for credential fields, codes, and data tables, and bake the choice into the component so it is not redecided per screen.
* **Separate the diagnosis from the cure:** a misread character is a legibility problem (typeface, glyph, size); a tiring paragraph is a readability problem (spacing, measure). Naming the right one keeps you from restyling a layout when the font was the issue.

## Related terms and mentions

[Glyph](glyph.md) · [Readability](readability.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Typeface](typeface.md) · [X-height](x-height.md)

## Further reading

* Foundations: [Legibility, Readability, and Comprehension (Nielsen Norman Group)](https://www.nngroup.com/articles/legibility-readability-comprehension/)

### Sources

1. Legibility is the lowest-level consideration in content usability, whether people can see, distinguish, and recognize the characters in the text, and is mainly determined by typography - Nielsen Norman Group: Legibility, Readability, and Comprehension [https://www.nngroup.com/articles/legibility-readability-comprehension/](https://www.nngroup.com/articles/legibility-readability-comprehension/)
</content>
