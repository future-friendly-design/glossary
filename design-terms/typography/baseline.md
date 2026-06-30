---
term: Baseline
slug: baseline
aliases: []
level: foundational
depth: core
summary: In typography, the baseline refers to an invisible line that aligns glyphs that are placed together to form words.
related:
  - cap-height
  - x-height
  - ascender
  - descender
  - leading
  - line-height
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
  - writing-systems-scripts
  - shaping-layout
---

# Baseline

## Definition

In typography, the baseline refers to an invisible line that aligns glyphs that are placed together to form words. For example, in the [Latin script](../../terms/latin-script.md), the bottoms of the letters "o," "n," and "m" rest on top of the alphabetic baseline, while the tail of "g" (known as the [descender](../../terms/descender.md)) drops below it.

However, not every script sits its symbols on top of a baseline. The line a script aligns to depends on the script, and there are several baseline types:

| Script | Example languages | Baseline it aligns to | How symbols sit |
| --- | --- | --- | --- |
| [Latin](../../terms/latin-script.md) | English, French, Vietnamese | Alphabetic (a bottom line) | Symbols sit on the line, and descenders drop below it.<sup>1</sup> |
| [Devanagari](../../terms/devanagari.md) | Hindi, Marathi, Nepali | Hanging (a top line) | Symbols hang from a top line, the [shirorekha](../../language-terms/writing-systems-and-scripts/shirorekha.md); that top line is the [hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md).<sup>2</sup> |
| [Tamil](../../terms/tamil-script.md) | Tamil | Alphabetic (a bottom line) | An abugida like Devanagari, but its symbols sit on a bottom line instead of hanging.<sup>3</sup> |
| [CJK](../../terms/cjk.md) (Han, Hangul, Kana) | Chinese, Japanese, Korean | Ideographic (the square's edges) | Glyphs are drawn to fill a square and align to its top and bottom edges, not a letter baseline.<sup>4</sup> |

### Why it matters in design systems

In horizontal Latin typesetting, the baseline is the reference all of a font's vertical measurements are taken from: [x-height](../../terms/x-height.md), [cap-height](../../terms/cap-height.md), and the reach of [ascender](../../terms/ascender.md)s and descenders are all distances from it, and [leading](../../terms/leading.md), the spacing the [line-height](../../terms/line-height.md) control sets, is measured from one line's baseline to the next.<sup>5</sup> Most symbols rest on it while descenders drop below, and the font keeps extra space above and below on top of that, which is why a line of text rarely sits where you expect inside a fixed-height box. The baseline is also the edge that [vertical-trim](../../terms/vertical-trim.md) and the CSS `text-box-trim` feature trim to when they strip that built-in space, so a label sits optically centred in a button with no manual padding.<sup>6</sup>

Those measurements describe horizontal text. Set the same text vertically, as in Japanese [tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md), and the line everything aligns to becomes a central one running down the middle of each line, not a bottom baseline.<sup>7</sup> Japanese vertical text does not even measure line spacing baseline to baseline: it spaces lines by the box each character sits in, from the edge of one to the next.<sup>8</sup> So line-height tokens, vertical centring, and any baseline-based reasoning tuned to Latin will misalign other scripts and writing directions; the baseline you know is one script's behaviour, not a universal.

***

### Related terms and mentions

[Ascender](../../terms/ascender.md) · [Cap height](../../terms/cap-height.md) · [CJK](../../terms/cjk.md) · [Descender](../../terms/descender.md) · [Devanagari](../../terms/devanagari.md) · [Glyph](../../terms/glyph.md) · [Hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Latin script](../../terms/latin-script.md) · [Leading](../../terms/leading.md) · [Line height](../../terms/line-height.md) · [Shirorekha](../../language-terms/writing-systems-and-scripts/shirorekha.md) · [Tamil script](../../terms/tamil-script.md) · [Tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md) · [Typography](../../terms/typography.md) · [Vertical trim](../../terms/vertical-trim.md) · [x-height](../../terms/x-height.md)

### Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Resource library: [Baseline (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/baseline)

### Sources

1. The alphabetic baseline is "used in writing Latin, Cyrillic, Greek, and many other scripts" and "corresponds to the bottom of most, but not all, their characters", so their symbols sit on it and descenders fall below - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
2. "In Indic scripts that have a hanging baseline, the top alignment point is the hanging baseline"; the languages named include Hindi, which is written in Devanagari - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
3. Tamil is listed among the "scripts that don't have hanging baseline such as Kannada, Tamil, Telugu, Malayalam, Odia", so its symbols sit on a lower baseline even though it is an abugida like Devanagari - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
4. The ideographic-over and ideographic-under baselines "correspond to the line-over / line-under design edge of CJK (Han/Hangul/Kana) text", whose glyphs are designed to fill a square - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
5. "Leading (or line height) is the vertical distance between lines of text. More precisely, the distance between their baselines (from one line's baseline to the following line's baseline)" - Kerning, tracking, leading and spacing in typography (TypeType) [https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/](https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/)
6. `text-box-trim` "specifies which of the over and under edges of text content to trim", and with `text-box-edge` you can trim "the under edge flush with the font's baseline" - text-box-trim (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
7. In vertical typographic mode "the central baseline is used as the dominant baseline", and "Han-based systems, whose glyphs are designed to fill a square, tend to align on their bottoms or through their centers" - CSS Writing Modes Level 4 (W3C) [https://www.w3.org/TR/css-writing-modes-4/](https://www.w3.org/TR/css-writing-modes-4/)
8. Japanese composition measures line spacing by the character frame, not a baseline: a multi-line space is the sum of the character-frame sizes plus the line gaps between frames, edge to edge - Requirements for Japanese Text Layout (W3C) [https://www.w3.org/TR/jlreq/](https://www.w3.org/TR/jlreq/)
