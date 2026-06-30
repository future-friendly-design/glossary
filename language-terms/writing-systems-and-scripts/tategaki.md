---
term: Tategaki
slug: tategaki
aliases:
  - 縦書き
level: advanced
depth: core
summary: Tategaki is the traditional Japanese form of vertical text, set in columns that run from top to bottom and are ordered from right to left.
related:
  - vertical-text
  - text-direction
  - full-width
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: writing-mode (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode
    type: code
  - title: Vertical text (W3C Internationalization)
    url: https://www.w3.org/International/articles/vertical-text/
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Tategaki

## Definition

Tategaki is the traditional Japanese form of vertical text, set in columns that run from top to bottom and are ordered from right to left.

For example, a Japanese novel is typically set in tategaki, read down each column and then leftward to the next.

### Why it matters in design systems

Tategaki is the Japanese name for this form of [vertical text](../../terms/vertical-text.md); the same top-to-bottom, right-to-left setting is used across [CJK](../../terms/cjk.md) more broadly. It was long the standard for Japanese and is still everywhere in novels, newspapers, manga, and signage, while horizontal writing, called yokogaki, came later and now dominates the web and technical text. Both are still in use, and which one fits depends on the content and audience, not a fixed rule, so a Japanese product may need to support both and let the content or reader choose, much as [text direction](text-direction.md) can call for letting a user pick between scripts. Confirm the expected mode with readers rather than guessing.

Setting it is more than turning a horizontal block ninety degrees. Digits and short runs of Latin letters follow their own orientation rules (a short horizontal run set upright inside a vertical line is called tate-chu-yoko),<sup>1</sup> and the whole component shifts with the text: scroll direction, form controls, line breaking, and bidirectional runs. On the web the mode is the CSS `writing-mode: vertical-rl` property.<sup>2</sup> So, like any text direction, setting it is necessary but not sufficient.

***

### Related terms and mentions

[CJK](../../terms/cjk.md) · [Font coverage](../../terms/font-coverage.md) · [Full-width](../../terms/full-width.md) · [Text direction](text-direction.md) · [Vertical text](../../terms/vertical-text.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [writing-mode (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
* Foundations: [Vertical text (W3C Internationalization)](https://www.w3.org/International/articles/vertical-text/)

### Sources

1. In vertical text, ordinary number digits lie on their side by default whereas fullwidth digits and enclosed alphanumerics are upright by default, and short horizontal runs (tate-chu-yoko) are produced with `text-combine-upright` - Vertical text (W3C Internationalization) [https://www.w3.org/International/articles/vertical-text/](https://www.w3.org/International/articles/vertical-text/)
2. In Japanese, Chinese, and Korean the lines run right to left, set in CSS with `writing-mode: vertical-rl` - Vertical text (W3C Internationalization) [https://www.w3.org/International/articles/vertical-text/](https://www.w3.org/International/articles/vertical-text/)
