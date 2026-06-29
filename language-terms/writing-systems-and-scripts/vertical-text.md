---
term: Vertical text
slug: vertical-text
aliases: [vertical writing, top to bottom]
tags: [writing-systems-scripts, shaping-layout]
level: foundational
depth: core
summary: Vertical text is a text direction where a script is written and read in columns running from top to bottom.
related: [text-direction, tategaki, left-to-right, right-to-left]
status: voice-passed
version_added: 0.1
updated: 2026-06-29
contributors: [sam-gordashko]
further_reading:
  - title: "writing-mode (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode
    type: code
  - title: "Vertical text (W3C Internationalization)"
    url: https://www.w3.org/International/articles/vertical-text/
    type: authority
license: CC-BY-4.0
---

# Vertical text

## Definition

Vertical text is a text direction where a script is written and read in columns running from top to bottom.

For example, Japanese can be set vertically (tategaki), and traditional Mongolian is written vertically.

### Why it matters in design systems

Several East Asian scripts can be set vertically, including Chinese, Japanese, and Korean, the traditional Japanese mode being [tategaki](../../terms/tategaki.md), as well as traditional [Mongolian](../../terms/mongolian-script.md). On the web you set vertical text with the CSS `writing-mode` property: `vertical-rl` stacks lines top to bottom with columns advancing right to left, as in [CJK](../../terms/cjk.md), and `vertical-lr` advances them left to right, as in Mongolian.<sup>1</sup>

So for a design system, vertical text is more than turning a horizontal block on its side. The [font](../../terms/font.md) has to provide vertical forms and spacing for its symbols, not only the horizontal ones,<sup>2</sup> and the rest of the component shifts with the text: scroll direction, form controls, and line breaking. Like the other directions, setting it is necessary but not sufficient on its own. It is one way a script's [text direction](text-direction.md) can run, alongside [left to right](../../terms/left-to-right.md) and [right to left](../../terms/right-to-left.md).

***

### Related terms and mentions

[CJK](../../terms/cjk.md) · [Font](../../terms/font.md) · [Left-to-right](../../terms/left-to-right.md) · [Mongolian script (traditional)](../../terms/mongolian-script.md) · [Right-to-left](../../terms/right-to-left.md) · [Tategaki](../../terms/tategaki.md) · [Text direction](text-direction.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [writing-mode (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
* Foundations: [Vertical text (W3C Internationalization)](https://www.w3.org/International/articles/vertical-text/)

### Sources

1. Vertical text is set with the CSS `writing-mode` property: `vertical-rl` lays out lines top to bottom with columns advancing right to left, and `vertical-lr` advances columns left to right; Chinese, Japanese, Korean, and Mongolian are written vertically - writing-mode (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
2. To be set vertically a font must supply vertical glyph forms (the `vert` and `vrt2` features transform or rotate default glyphs for upright vertical presentation) and vertical metrics, which a font built only for horizontal text does not include - OpenType feature registry (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_uz](https://learn.microsoft.com/en-us/typography/opentype/spec/features_uz)
