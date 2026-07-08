---
term: Baseline
slug: baseline
aliases: []
level: foundational
depth: core
summary: >-
  In typography, the baseline refers to an invisible line that aligns glyphs
  that are placed together to form words.
related:
  - cap-height
  - x-height
  - ascender
  - descender
  - leading
  - line-height
  - vertical-trim
  - hanging-baseline
  - script-rules
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

In typography, the baseline refers to an invisible line that aligns glyphs that are placed together to form words. For example, in the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md), the bottoms of the letters "o," "n," and "m" rest on top of the alphabetic baseline, while the tail of "g" (known as the [descender](../../terms/descender.md)) drops below it.

However, not every script sits its [symbols](../../language-terms/writing-systems-and-scripts/symbol.md) on top of a baseline. The line a script aligns to depends on the script, and there are several baseline types. While this glossary doesn't cover every script, here are some you may want to explore. Select a linked term to open its glossary page:

| Script                                                                    | Example languages           | Baseline                                                                                 | How symbols sit                                                                                                                                                | Example          |
| ------------------------------------------------------------------------- | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| [Latin](../../language-terms/writing-systems-and-scripts/latin-script.md) | English, French, Vietnamese | Alphabetic baseline                                                                      | Symbols sit on the baseline, and descenders drop below it.<sup>1</sup>                                                                                         | page             |
| [Devanagari](../../terms/devanagari.md)                                   | Hindi, Marathi, Nepali      | [Hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md) | Symbols hang from a top line, the [shirorekha](../../language-terms/writing-systems-and-scripts/shirorekha.md).<sup>2</sup>                                    | नमस्ते (namaste) |
| [Tamil](../../terms/tamil-script.md)                                      | Tamil                       | Alphabetic baseline                                                                      | An [abugida](../../language-terms/writing-systems-and-scripts/abugida.md) like Devanagari, but its symbols sit on the baseline instead of hanging.<sup>3</sup> | தமிழ் (tamizh)   |
| [CJK](../../terms/cjk.md) (Han, Hangul, Kana)                             | Chinese, Japanese, Korean   | Ideographic baseline                                                                     | Glyphs fill a square and align to its top and bottom edges, not a letter baseline.<sup>4</sup>                                                                 | 你好 (nǐ hǎo)      |

### Why it matters in design systems

At the script level of the design system, the position of symbols along its baseline is defined by the [script rules](../../language-terms/writing-systems-and-scripts/script-rules.md). When we zoom into the typography part of the system, the baseline determines many sizing properties and glyph alignment defined within the font styling design decisions.

Recall that in the Latin script, the symbols are aligned horizontally. Most of the symbols sit on top of the baseline, with descenders dropping below the baseline. This allows words like `script` to appear horizontally aligned along the baseline, even though the tail of the `p` drops below it. In longform text, the next row of text is placed below.

In scripts that run horizontally, whether [left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) or [right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md), symbols rest on the baseline, and it is the reference a font's vertical metrics are measured from. Which metrics those are depends on the script. Latin is bicameral, so it has a [cap-height](../../terms/cap-height.md) and an [x-height](../../terms/x-height.md) alongside the reach of [ascender](../../terms/ascender.md)s and descenders. [Arabic](../../terms/arabic-script.md) and [Hebrew](../../terms/hebrew-script.md) run horizontally and rest on a baseline too, but both are unicameral, a single case, so they have no cap height or x-height;<sup>5</sup> they carry their own heights, and Arabic's ascenders and descenders reach much further above and below the baseline than Latin's.<sup>6</sup> A shared direction and a shared baseline do not mean shared metrics. [Leading](../../terms/leading.md), the vertical spacing controlled by [line-height](../../terms/line-height.md), is measured from the baseline of one line of text to the baseline of the line below it.<sup>7</sup>

Beyond the space the letters themselves take up, every font also reserves empty space above its tallest glyphs and below its lowest, built into the font's own metrics, so a line of text rarely sits flush against the edges of its bounding box. Both design tools and code offer a way to trim that reserved space back to the cap height and baseline (see known as [vertical-trim](../../terms/vertical-trim.md) in design and `text-box-trim` in CSS).<sup>8</sup>

All of that describes horizontal text, in scripts that run vertically, the symbols no longer sit on a bottom baseline. For example, in CJK scripts such as Japanese [tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md), symbols are aligned to the center axis running down the middle of a column, and these vertical lines of text are positioned side by side.<sup>9</sup>

The line spacing in vertical text is not measured from baseline to baseline. In Japanese for example, each symbol ([character](../../terms/character.md)) sits in an invisible bounding box, and the line spacing is measured between the bounding boxes from one vertical line of text to the next.<sup>10</sup>

Thinking about a multi-language design system, it's important to remember that a baseline is one script's way of aligning text, it is not universal. Calculating typography design decisions using the baseline of one script (most commonly Latin for English language support) will not scale across all languages. Line-height, vertical-trim, text-box-trim and any text alignment pinned to a bottom baseline may need to be rebuilt when adding support for new languages in your design system.

***

### Related terms and mentions

[Abugida](../../language-terms/writing-systems-and-scripts/abugida.md) · [Arabic script](../../terms/arabic-script.md) · [Ascender](../../terms/ascender.md) · [Cap height](../../terms/cap-height.md) · [Character](../../terms/character.md) · [CJK](../../terms/cjk.md) · [Descender](../../terms/descender.md) · [Devanagari](../../terms/devanagari.md) · [Glyph](../../terms/glyph.md) · [Han characters](../../terms/han-characters.md) · [Hanging baseline](../../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Hangul](../../terms/hangul.md) · [Hebrew script](../../terms/hebrew-script.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Leading](../../terms/leading.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Line height](../../terms/line-height.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Shirorekha](../../language-terms/writing-systems-and-scripts/shirorekha.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Tamil script](../../terms/tamil-script.md) · [Tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Typography](../../terms/typography.md) · [Vertical trim](../../terms/vertical-trim.md) · [x-height](../../terms/x-height.md)

### Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Resource library: [Baseline (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/baseline)

### Sources

1. The alphabetic baseline is "used in writing Latin, Cyrillic, Greek, and many other scripts" and "corresponds to the bottom of most, but not all, their characters", so their symbols sit on it and descenders fall below - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
2. "In Indic scripts that have a hanging baseline, the top alignment point is the hanging baseline"; the languages named include Hindi, which is written in Devanagari - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
3. Tamil is listed among the "scripts that don't have hanging baseline such as Kannada, Tamil, Telugu, Malayalam, Odia", so its symbols sit on a lower baseline even though it is an abugida like Devanagari - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
4. The ideographic-over and ideographic-under baselines "correspond to the line-over / line-under design edge of CJK (Han/Hangul/Kana) text", the edges CJK glyphs align to rather than a letter baseline - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
5. Hebrew "uses the so-called 'alphabetic' baseline, which is the same as for Latin", and has "no case distinction", so it carries no cap height or x-height - Hebrew Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/hebr/he.html](https://r12a.github.io/scripts/hebr/he.html)
6. The Arabic script is unicameral (it has no letter case, and so no cap height or x-height) and sits on a baseline along which letters join; "Arabic ascenders and descenders extend much further than those of the Latin script" - Arabic & Persian Layout Requirements (W3C) [https://www.w3.org/TR/alreq/](https://www.w3.org/TR/alreq/)
7. "Leading (or line height) is the vertical distance between lines of text. More precisely, the distance between their baselines (from one line's baseline to the following line's baseline)" - Kerning, tracking, leading and spacing in typography (TypeType) [https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/](https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/)
8. `text-box-trim` "specifies which of the over and under edges of text content to trim", and with `text-box-edge` you can trim "the under edge flush with the font's baseline" - text-box-trim (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
9. In vertical typographic mode "the central baseline is used as the dominant baseline", and "Han-based systems, whose glyphs are designed to fill a square, tend to align on their bottoms" - CSS Writing Modes Level 4 (W3C) [https://www.w3.org/TR/css-writing-modes-4/](https://www.w3.org/TR/css-writing-modes-4/)
10. Japanese composition measures line spacing by the character frame, not a baseline: a multi-line space is the sum of the character-frame sizes plus the line gaps between frames, edge to edge - Requirements for Japanese Text Layout (W3C) [https://www.w3.org/TR/jlreq/](https://www.w3.org/TR/jlreq/)
