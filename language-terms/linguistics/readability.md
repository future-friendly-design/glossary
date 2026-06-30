---
term: Readability
slug: readability
aliases: []
level: foundational
depth: deep
summary: Readability is how comfortably a reader can move through a block of text.
related:
  - legibility
  - leading
  - line-height
  - measure
  - tracking
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Legibility, Readability, and Comprehension (Nielsen Norman Group)
    url: https://www.nngroup.com/articles/legibility-readability-comprehension/
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Readability

## Definition

Readability is how comfortably a reader can move through a block of text.

Where [legibility](legibility.md) is about recognizing a single character, readability is about the whole passage: how easily the eye takes in the words and travels along each line and down to the next. It is a typographic property set by spacing and layout: the [line length](../../terms/measure.md), the [leading](../../terms/leading.md) between lines, the letter and word spacing ([tracking](../writing-systems-and-scripts/tracking.md)), the alignment, and the size. Legibility is the zoomed-in view of type, readability the zoomed-out one.

A note on the word: "readability" is also used, in a different field, to mean how complex the language is, the reading level a text demands, scored by formulas like Flesch-Kincaid. That sense is about words and sentences, not type. This entry is the typographic one, about how the text is set.<sup>1</sup>

## Why it matters in design systems

Readability is where typography becomes a systems problem, because its levers are tokens, not one-off tweaks. [Line height](../../terms/line-height.md) sets the vertical rhythm: too tight and the lines tangle, too loose and they drift apart. The line length, or measure, has a comfortable range before the eye starts losing its place on the return sweep. Letter and word spacing change the texture of the paragraph, and size ties it all together. In a design system these live as line-height, spacing, and max-width tokens applied across every component, so a readability decision made once propagates everywhere, which is power when it is right and damage when it is wrong. And readability is not legibility: you can have every character crisp and still build an unreadable page with the wrong measure and leading.

## Example

Take one perfectly legible paragraph and break its readability three ways without touching the font. Run the measure too wide, a line spanning a full desktop width, and the eye struggles to find the start of the next line. Pull the leading too tight and the lines visually merge; open it too far and they stop reading as a unit. Every character stays sharp and recognizable the whole time; the passage still gets harder to read. That gap, crisp letters and a tiring read, is what readability names and legibility cannot catch.

## Common mistake

Assuming a clear, legible font guarantees a readable page. Legibility is necessary but not enough: the most legible typeface is undone by a 120-character line, by leading so tight the rows blur, or by justified text that opens rivers of white space. Readability is decided after the font is chosen, in the spacing and layout, which is exactly the part a design system encodes in tokens. Reaching for a new font to fix a readability problem usually misses the cause.

## In practice

* **Set measure with a token, not by eye:** cap line length in the comfortable range so paragraphs do not stretch across wide screens, where the eye loses the start of the next line. See [measure](../../terms/measure.md).
* **Tune leading to the text, not a default:** body copy, dense tables, and large headings each want different [line height](../../terms/line-height.md); set them as steps in the type scale so the rhythm stays consistent across components.
* **Judge readability on a real paragraph, not a label:** a single line or a specimen will not reveal a bad measure or tight leading. Test with a full block of the actual content at the actual width.

## Related terms and mentions

[Leading](../../terms/leading.md) · [Legibility](legibility.md) · [Line height](../../terms/line-height.md) · [Measure](../../terms/measure.md) · [Tracking](../writing-systems-and-scripts/tracking.md)

## Further reading

* Foundations: [Legibility, Readability, and Comprehension (Nielsen Norman Group)](https://www.nngroup.com/articles/legibility-readability-comprehension/)

### Sources

1. "Readability" is also used to mean how complex a text's language is, the reading level it demands (e.g. Flesch-Kincaid), a measure separate from the typographic sense - Nielsen Norman Group: Legibility, Readability, and Comprehension [https://www.nngroup.com/articles/legibility-readability-comprehension/](https://www.nngroup.com/articles/legibility-readability-comprehension/)
