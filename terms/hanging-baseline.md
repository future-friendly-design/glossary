---
term: Hanging baseline
slug: hanging-baseline
aliases: []
tags:
  - typography
  - shaping-layout
level: intermediate
depth: core
summary: The hanging baseline is the top alignment line that letters hang from in scripts like Devanagari and Tibetan, rather than the bottom line that Latin letters sit on.
related:
  - baseline
  - shirorekha
  - line-height
  - devanagari
status: voice-passed
version_added: 0.1
updated: 2026-06-26
contributors:
  - sam-gordashko
further_reading:
  - title: "CSS Inline Layout Module Level 3: baseline values (W3C)"
    url: https://www.w3.org/TR/css-inline-3/
    type: code
  - title: "Indic Layout Requirements (W3C)"
    url: https://www.w3.org/TR/ilreq/
    type: authority
license: CC-BY-4.0
---

# Hanging baseline

## Definition

The hanging baseline is the top alignment line that letters hang from in scripts like [Devanagari](devanagari.md) and [Tibetan](tibetan-script.md), rather than the bottom line that [Latin](latin-script.md) letters sit on.

It is one of several baseline types. Latin and most European scripts use the alphabetic [baseline](baseline.md), the line letters sit on; Chinese, Japanese, and Korean align to ideographic baselines; and Brahmic scripts like Devanagari and Bengali hang from a top line.<sup>1</sup> For example, in Devanagari `नमस्ते`, the letters line up along the [shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) at the top of the word, and that top line is the hanging baseline.

## Why it matters in design systems

It is easy to assume every script shares one baseline, because in Latin the baseline is so steady you stop noticing it. It is not universal. A script that hangs from a top line takes that line, the hanging baseline, as its main alignment point, not a line at the bottom.<sup>2</sup>

That changes a few design-system decisions. When you set Devanagari and Latin on the same line, the two scripts align to different reference lines, so the text box and any vertical centring cannot assume a single baseline. [Line-height](line-height.md) tokens tuned to Latin can also clip the marks that stack above and below a hanging-baseline script, so these scripts often need a taller line box than a Latin default gives them.<sup>2</sup> Choosing a font that covers the script is the start; aligning it correctly is the rest.

CSS exposes this directly: the `hanging` value of `dominant-baseline` aligns content to the hanging baseline instead of the alphabetic one.<sup>1</sup>

## Related terms and mentions

[Baseline](baseline.md) · [Bengali-Assamese](bengali-assamese.md) · [Devanagari](devanagari.md) · [Latin script](latin-script.md) · [Line height](line-height.md) · [Shaping & layout](shaping-layout.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Tibetan script](tibetan-script.md) · [Typography](typography.md)

## Further reading

* Code & specs: [CSS Inline Layout Module Level 3: baseline values (W3C)](https://www.w3.org/TR/css-inline-3/)
* Foundations: [Indic Layout Requirements (W3C)](https://www.w3.org/TR/ilreq/)

## Sources

1. CSS defines a set of baseline types and describes the hanging baseline as the one "from which characters in Tibetan and similar unicameral scripts with a strong but not absolute top edge seem to 'hang'" - CSS Inline Layout Module Level 3 (W3C) [https://www.w3.org/TR/css-inline-3/](https://www.w3.org/TR/css-inline-3/)
2. Indic scripts that have a hanging baseline take the hanging baseline as the top alignment point, unlike scripts that sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
