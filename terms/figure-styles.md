---
term: Figure styles
slug: figure-styles
aliases: [numeral styles, figures]
tags: [typography]
level: advanced
depth: deep
summary: Figure styles are the different designs a font offers for numerals, such as lining vs oldstyle and tabular vs proportional.
related: [small-caps, cap-height, x-height]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-variant-numeric (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric
    type: code
  - title: "Alternate figures (Butterick's Practical Typography)"
    url: https://practicaltypography.com/alternate-figures.html
    type: authority
license: CC-BY-4.0
---

## Definition
Figure styles are the different designs a font offers for numerals, such as lining vs oldstyle and tabular vs proportional.

## Why it matters
Numerals are not a single design. Lining figures sit at a uniform height aligned to the [cap-height](cap-height.md) and stand out cleanly in headings and alongside capitals; oldstyle figures have ascenders and descenders so they blend into running lowercase text. Separately from that, tabular figures share one fixed width so numbers stack into aligned columns, while proportional figures vary in width to read evenly inline. The two distinctions are independent, so a font may offer all four combinations, each selected through OpenType features.

## Example
Use tabular lining figures for a price table; use oldstyle proportional figures for a date inside a sentence.

## Common mistake
Using proportional figures in a table, so the columns of numbers do not line up and the eye cannot scan them. The reverse trips people too: oldstyle figures set next to capitals look like they are sliding off the line. Match the figure style to the context rather than taking whatever the font defaults to.

## In practice
- **Tokens and CSS:** set `font-variant-numeric: tabular-nums` for any data table, dashboard, or aligned number column, and `oldstyle-nums` for numbers in running prose. Bake these into the relevant type styles so the right figures come along automatically. See [font-variant-numeric (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric).
- **Font coverage:** the figures only exist if the font includes them, and some web fonts get subset down and lose the extra sets. Confirm the figures you need survived before relying on them.

## Related terms
[small-caps](small-caps.md) · [cap-height](cap-height.md) · [x-height](x-height.md)

## Further reading
- Code & specs: [font-variant-numeric (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric)
- Foundations: [Alternate figures (Butterick's Practical Typography)](https://practicaltypography.com/alternate-figures.html)
