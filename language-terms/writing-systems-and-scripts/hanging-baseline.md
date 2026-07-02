---
term: Hanging baseline
slug: hanging-baseline
aliases: []
level: intermediate
depth: core
summary: The hanging baseline is a top line that a script's symbols hang from, instead of the bottom baseline that Latin and similar scripts sit on.
related:
  - baseline
  - shirorekha
  - script-rules
  - devanagari
  - bengali-assamese
  - tibetan-script
  - line-height
status: voice-passed
version_added: 0.1
updated: 2026-06-30T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'CSS Inline Layout Module Level 3: baseline values (W3C)'
    url: https://www.w3.org/TR/css-inline-3/
    type: code
  - title: Indic Layout Requirements (W3C)
    url: https://www.w3.org/TR/ilreq/
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - typography
  - shaping-layout
---

# Hanging baseline

## Definition

The hanging baseline is a top line that a script's symbols hang from, instead of the bottom baseline that Latin and similar scripts sit on.

The visible headstroke that runs along it in [Devanagari](../../terms/devanagari.md) is the [shirorekha](shirorekha.md); the hanging baseline is the invisible alignment line, not the stroke itself. In नमस्ते (namaste), for instance, every letter hangs from the unbroken line across the top of the word, and that top line is the hanging baseline.

While this glossary doesn't cover every script, here are some scripts you may want to explore that use a hanging baseline. Select a linked term to open its glossary page:

| Script | Example languages | How the hanging baseline works | Example |
| --- | --- | --- | --- |
| [Devanagari](../../terms/devanagari.md) | Hindi, Marathi, Nepali | Most symbols hang from one continuous top line.<sup>1</sup> | नमस्ते (namaste) |
| [Bengali-Assamese](../../terms/bengali-assamese.md) | Bengali, Assamese | Letters join along a top bar, and the hanging baseline is based on it.<sup>2</sup> | বাংলা (bangla) |
| [Tibetan](../../terms/tibetan-script.md) | Tibetan, Dzongkha | Glyphs hang from a strong, though not absolute, top edge.<sup>3</sup> | བོད་ཡིག (böyig) |

Whether a script hangs is decided per script, not by family: Gujarati, Marathi, and Punjabi hang as well, but other [Brahmic scripts](../../terms/brahmic-scripts.md) such as [Tamil](../../terms/tamil-script.md), Telugu, and Malayalam sit on a bottom [baseline](../../design-terms/typography/baseline.md) like [Latin](../../terms/latin-script.md).<sup>4</sup>

### Why it matters in design systems

Which baseline a script uses is a [script rule](script-rules.md): it holds for every language written in that script, and it is set before any font or styling choice. A hanging-baseline script takes its top line as the main alignment point, not a line at the bottom, so it does not drop into a Latin vertical rhythm unchanged.

Set a hanging-baseline script and Latin on the same line and the two align to different reference lines, so a text box and any vertical centring cannot assume a single baseline. The script also carries [marks](mark.md) that stack above and below the base [symbol](symbol.md), reaching past where Latin [ascender](../../terms/ascender.md)s and [descender](../../terms/descender.md)s stop, so [line-height](../../terms/line-height.md) tokens tuned to Latin can clip them, and these scripts usually need a taller line box than a Latin default gives.<sup>5</sup> Covering the script is not only about glyphs, either: the font has to render the continuous top line and the hanging behaviour correctly, or a word looks broken even when every symbol is present.

On the web, CSS exposes this directly: the `hanging` value of `dominant-baseline` aligns content to the hanging baseline instead of the alphabetic one.<sup>6</sup> Still, the baseline is only one script rule. To support a language written in a hanging-baseline script, walk the other script rules too (direction, shaping, breaking), then its [orthography](orthography.md); the baseline tells you how to align and space the script vertically, not whether you can render it at all.

***

### Related terms and mentions

[Ascender](../../terms/ascender.md) · [Baseline](../../design-terms/typography/baseline.md) · [Bengali-Assamese](../../terms/bengali-assamese.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [Descender](../../terms/descender.md) · [Devanagari](../../terms/devanagari.md) · [Glyph](../../terms/glyph.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Script rules](script-rules.md) · [Shirorekha](shirorekha.md) · [Symbol](symbol.md) · [Tamil script](../../terms/tamil-script.md) · [Tibetan script](../../terms/tibetan-script.md) · [Typography](../../terms/typography.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Foundations: [Indic Layout Requirements (W3C)](https://www.w3.org/TR/ilreq/)

### Sources

1. "In Indic scripts that have a hanging baseline, the top alignment point is the hanging baseline"; the languages named include Hindi, which is written in Devanagari - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
2. Bengali has a "top bar that joins the letters", and its hanging baseline is based on that top bar - Bengali/Bangla Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/beng/bn.html](https://r12a.github.io/scripts/beng/bn.html)
3. The hanging baseline is the one "from which characters in Tibetan and similar unicameral scripts with a strong but not absolute top edge seem to 'hang'" - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
4. Indic scripts with a hanging baseline are named as Hindi, Bengali, Gujarati, Marathi, and Punjabi, while "scripts that don't have hanging baseline such as Kannada, Tamil, Telugu, Malayalam, Odia" sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
5. In Devanagari "the bottom edge of basic letters sits on the alphabetic baseline used by the Latin letters", while "ascenders and vowel signs ... push slightly beyond the Latin ascenders and descenders", so its marks reach above and below where Latin's do - Devanagari Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
6. The `hanging` value of `dominant-baseline` sets the dominant baseline to the font's hanging baseline table, aligning content to it instead of the alphabetic baseline - dominant-baseline (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline](https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline)
