---
term: Variable font
slug: variable-font
aliases:
  - VF
  - OpenType variable font
level: intermediate
depth: core
summary: "A variable font is a kind of font file that holds a range of styles of a typeface, such as its weights, in a single file."
related:
  - font-weight
  - typeface
  - font
  - font-subsetting
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: Variable fonts (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide
    type: code
  - title: Explore text properties (Figma Learn)
    url: >-
      https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
  - title: OpenType Font Variations Overview (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Variable font

## Definition

A variable font is a kind of font file that holds a range of styles of a typeface, such as its weights, in a single file.<sup>1</sup>

This is different from a standard [font](font.md), which has only one style or weight per file. This means to support a normal font weight and a bold font weight, a variable font only needs to load one font file, and a standard font would need to load two font files.

### Why it matters in design systems

A font's style menu usually offers a range of weights: Light, Regular, Semibold, Bold. Behind each name on that list there is normally a separate font file.<sup>2</sup> With a variable font the list becomes a slider, because the weight changes along a line called an axis.

Weight is one of five axes with agreed names (weight, width, slant, italic and optical size),<sup>3</sup> and a type designer can add axes of their own.<sup>4</sup> The designer can also give familiar names to points along an axis, so a variable font can still show Light and Semibold in a style menu the way an ordinary [typeface](typeface.md) family does.<sup>5</sup> Variable fonts are a later addition to [OpenType](opentype.md), the most widely used font format.<sup>6</sup>

A variable font can suit a system where [typography](../../terms/typography.md) is part of the visual identity, because it gives better quality and finer control. A font weight taken from a variable font is worked out from the type designer's own drawings, and it is not counted as a fake, unlike [faux bold](faux-bold.md), where a browser thickens the regular shapes because no bold was available.<sup>7</sup> [Font weight](font-weight.md) also becomes a number you can set exactly: a [design token](../../design-terms/design-token.md) can ask for `550`, or even `425.5`.<sup>8</sup>

A variable font is not automatically a smaller file than a standard font. The file is larger than a single ordinary font,<sup>9</sup> so it saves anything only when a product would otherwise load several styles.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Design token](../../design-terms/design-token.md) · [Fallback font](fallback-font.md) · [Faux bold](faux-bold.md) · [Font](font.md) · [Font subsetting](font-subsetting.md) · [Font weight](font-weight.md) · [Language](../../language-terms/linguistics/language.md) · [OpenType](opentype.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Typeface](typeface.md) · [Typography](../../terms/typography.md) · [Font terms](./)

### Further reading

* Code & specs: [Variable fonts (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [OpenType Font Variations Overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)

### Sources

1. "OpenType Font Variations allow a font designer to incorporate multiple font faces within a font family into a single font resource" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
2. "each font would represent one specific width/weight/style combination" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
3. "The five currently registered axes are weight, width, slant, italic, and optical size" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
4. "Fonts may use tags defined in this registry, or may use foundry-defined tags" - OpenType Design-Variation Axis Tag Registry, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg](https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg)
5. "the designer may identify particular variation instances as “Light” or “Semibold”" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
6. "Variable fonts are an evolution of the OpenType font specification" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
7. "Variable fonts, where the font designer has provided one or more axes of variation do not count as font synthesis" - CSS Fonts Module Level 4, W3C Working Draft: 2.8. Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
8. "Fractional weights are valid" - CSS Fonts Module Level 4, W3C Working Draft: 2.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-4/#font-weight-prop](https://www.w3.org/TR/css-fonts-4/#font-weight-prop)
9. "That file would be larger than a single font" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
