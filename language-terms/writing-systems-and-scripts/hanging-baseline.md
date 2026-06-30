---
term: Hanging baseline
slug: hanging-baseline
aliases: []
level: intermediate
depth: core
summary: The hanging baseline is the top alignment line that letters hang from in scripts like Devanagari and Tibetan, rather than the bottom line that Latin letters sit on.
related:
  - baseline
  - shirorekha
  - script-rules
  - line-height
  - devanagari
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

The hanging baseline is the top alignment line that letters hang from in scripts like [Devanagari](../../terms/devanagari.md) and [Tibetan](../../terms/tibetan-script.md), rather than the bottom line that [Latin](../../terms/latin-script.md) letters sit on.

It is one of several baseline types. Latin and most European scripts use the alphabetic [baseline](../../design-terms/typography/baseline.md), the line letters sit on; Chinese, Japanese, and Korean align to ideographic baselines; and Brahmic scripts like Devanagari and Bengali hang from a top line.<sup>1</sup> For example, in Devanagari `नमस्ते`, the letters line up along the [shirorekha](shirorekha.md) at the top of the word, and that top line is the hanging baseline.

### Why it matters in design systems

It is easy to assume every script shares one baseline, because in Latin the baseline is so steady you stop noticing it. It is not universal. A script that hangs from a top line takes that line, the hanging baseline, as its main alignment point, not a line at the bottom.<sup>2</sup>

That changes a few design-system decisions. When you set Devanagari and Latin on the same line, the two scripts align to different reference lines, so the text box and any vertical centring cannot assume a single baseline. A hanging-baseline script also carries marks that stack above and below the base letter, reaching past where Latin ascenders and descenders stop, so [line-height](../../terms/line-height.md) tokens tuned to Latin can clip them and these scripts often need a taller line box than a Latin default gives them.<sup>3</sup> Choosing a font that covers the script is the start; aligning it correctly is the rest.

CSS exposes this directly: the `hanging` value of `dominant-baseline` aligns content to the hanging baseline instead of the alphabetic one.<sup>4</sup>

***

### Related terms and mentions

[Baseline](../../design-terms/typography/baseline.md) · [Bengali-Assamese](../../terms/bengali-assamese.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [CJK](../../terms/cjk.md) · [Devanagari](../../terms/devanagari.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Script rules](script-rules.md) · [Shaping & layout](../../terms/shaping-layout.md) · [Shirorekha](shirorekha.md) · [Tibetan script](../../terms/tibetan-script.md) · [Typography](../../terms/typography.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Foundations: [Indic Layout Requirements (W3C)](https://www.w3.org/TR/ilreq/)

### Sources

1. CSS defines a set of baseline types: the alphabetic baseline is "used in writing Latin, Cyrillic, Greek, and many other scripts", and the hanging baseline is the one "from which characters in Tibetan and similar unicameral scripts with a strong but not absolute top edge seem to 'hang'" - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
2. "In Indic scripts that have a hanging baseline, the top alignment point is the hanging baseline"; the languages named include Hindi, Bengali, Gujarati, Marathi, and Punjabi - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
3. In Devanagari "the bottom edge of basic letters sits on the alphabetic baseline used by the Latin letters", while "ascenders and vowel signs ... push slightly beyond the Latin ascenders and descenders", so the script's marks reach above and below where Latin's do - Devanagari Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
4. The `hanging` value of `dominant-baseline` sets the dominant baseline to the font's hanging baseline table, aligning content to it instead of the alphabetic baseline - dominant-baseline (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline](https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline)
