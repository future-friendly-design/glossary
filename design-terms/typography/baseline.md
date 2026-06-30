---
term: Baseline
slug: baseline
aliases: []
level: foundational
depth: core
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

For example, the bottoms of "o," "n," and "m" rest on the baseline, while the tail of "g" drops below it.

### Why it matters in design systems

The baseline is the anchor the whole vertical system is measured from: [x-height](../../terms/x-height.md), [cap-height](../../terms/cap-height.md), and the reach of [ascender](../../terms/ascender.md)s and [descender](../../terms/descender.md)s are all distances from it, and [leading](../../terms/leading.md), the spacing the [line-height](../../terms/line-height.md) control sets, is measured baseline to baseline.<sup>1</sup> Most letters rest on it while descenders drop below, and the font reserves extra space above and below on top of that, which is why a line of text rarely sits where you expect inside a fixed-height box.<sup>2</sup>

The baseline is also what [vertical-trim](../../terms/vertical-trim.md) and the CSS `text-box-trim` feature align to when they strip that built-in space, so a label can sit optically centred in a button with no manual padding.<sup>3</sup> One caveat for multilingual work: the sit-on-the-line baseline is a Latin-centric model, and some scripts align differently, like Devanagari, which hangs its letters from a top line called a [hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md).<sup>4</sup>

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
