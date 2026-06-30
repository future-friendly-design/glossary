---
term: Baseline
slug: baseline
aliases: []
level: foundational
depth: deep
summary: The baseline is the invisible line that most letters sit on.
related:
  - cap-height
  - x-height
  - ascender
  - descender
  - leading
  - vertical-trim
  - hanging-baseline
status: voice-passed
version_added: 0.1
updated: 2026-06-30T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'CSS Inline Layout Module Level 3: baseline values (W3C)'
    url: https://www.w3.org/TR/css-inline-3/
    type: code
  - title: Baseline (Google Fonts Knowledge)
    url: https://fonts.google.com/knowledge/glossary/baseline
    type: resource
license: CC-BY-4.0
tags:
  - typography
---

# Baseline

## Definition

The baseline is the invisible line that most letters sit on.

### Why it matters in design systems

The baseline is the anchor the whole vertical system is measured from. [x-height](../../terms/x-height.md), [cap-height](../../terms/cap-height.md), and the reach of [ascender](../../terms/ascender.md)s and [descender](../../terms/descender.md)s are all distances from it, and line spacing is measured baseline to baseline.<sup>1</sup> Most letters rest on it; descenders, like the tails of "g," "p," and "y," drop below it.<sup>2</sup> Once you can see the baseline, a lot of vertical alignment stops being guesswork.

### Example

The bottoms of "o," "n," and "m" rest on the baseline, while the tail of "g" hangs below it.

### Common mistake

Treating the baseline as the bottom of the text. It is not: descenders extend below it, and the font also reserves extra space above and below the letters on top of that. That reserved space is why a line of text rarely sits where you expect inside a fixed-height box, and why centring a label often needs a nudge.

### In practice

* **Tools and tokens:** the baseline is what [vertical-trim](../../terms/vertical-trim.md) and the CSS `text-box-trim` feature align to when they strip a font's built-in over and under space, so a label sits optically centred in a button with no manual padding.<sup>3</sup> That makes the baseline the reference point for tight, predictable vertical rhythm.
* **Line spacing:** because leading is measured baseline to baseline, the baseline is the reference for [line-height](../../terms/line-height.md) and [leading](../../terms/leading.md). Reasoning about spacing in baseline terms is more reliable than eyeballing the gap between lines.
* **Languages:** the single sit-on-the-line baseline is a Latin-centric model. Some scripts align differently: Devanagari hangs its letters from a top line, a [hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md), rather than sitting them on a bottom one, so do not assume every script shares one baseline behaviour when you set type in more than one script.<sup>4</sup>

***

### Related terms and mentions

[Ascender](../../terms/ascender.md) · [Cap height](../../terms/cap-height.md) · [Descender](../../terms/descender.md) · [Hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Leading](../../terms/leading.md) · [Line height](../../terms/line-height.md) · [Typography](../../terms/typography.md) · [Vertical trim](../../terms/vertical-trim.md) · [x-height](../../terms/x-height.md)

### Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Resource library: [Baseline (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/baseline)

### Sources

1. "Leading (or line height) is the vertical distance between lines of text. More precisely, the distance between their baselines (from one line's baseline to the following line's baseline)" - Kerning, tracking, leading and spacing in typography (TypeType) [https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/](https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/)
2. The alphabetic baseline is "used in writing Latin, Cyrillic, Greek, and many other scripts" and "corresponds to the bottom of most, but not all, their characters", which is why most letters sit on it and descenders fall below - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
3. `text-box-trim` "specifies which of the over and under edges of text content to trim", and with `text-box-edge` you can trim "the under edge flush with the font's baseline" - text-box-trim (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
4. "In Indic scripts that have a hanging baseline, the top alignment point is the hanging baseline", so scripts such as Devanagari hang their letters from a top line rather than sitting them on a bottom one - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
