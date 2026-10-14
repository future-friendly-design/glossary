---
term: Variable font
slug: variable-font
aliases:
  - VF
  - OpenType variable font
level: intermediate
depth: core
summary: >-
  A variable font is a font file that holds a whole range of styles of a
  typeface, where an ordinary font file holds one.
related:
  - font-weight
  - typeface
  - font
  - font-subsetting
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
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

A variable font is a kind of font file that holds the whole range of font styles and weights of a typeface in a single file.<sup>1</sup>&#x20;

This is different from a standard [font](font.md), which has only 1 font style or font weight per font file. This means to support a normal font weight and a bold font weight, a variable font only needs to load one font file, and a standard font would need to load two font files.&#x20;

### Why it matters in design systems

A font's style menu usually offers a range of weights: Light, Regular, Semibold, Bold. Behind each name on that list there is normally a separate font file, because an ordinary font holds a single style.<sup>4</sup> With a variable font the list becomes a slider, as each font weight changes along its style axis.&#x20;

However, font weight is one of five style axes defined in a variable font file (weight, width, slant, italic and optical size),<sup>6</sup> and a type designer can add other styles of their own.<sup>7</sup> The designer can also give familiar names to points along an axis, so a variable font can still show Light and Semibold in a style menu the way an ordinary [typeface](typeface.md) family does.<sup>8</sup> Variable fonts are a later addition to [OpenType](opentype.md), the most widely used font format.<sup>9</sup>

Variable fonts are preferred in systems that value typography as a part of their visual identity due to its enhanced quality and the ability to be very specific with typesetting. A font weight taken from a variable font is worked out from the type designer's own drawings, and it is not counted as a fake, unlike [faux bold](faux-bold.md), where a browser thickens the regular shapes because no bold was available.<sup>10</sup> The second is that [font weight](font-weight.md) becomes a real number. A [design token](../../design-terms/design-token.md) can ask for font weight of `550`, or even `425.5`<sup>11</sup>&#x20;

A variable font is not automatically a smaller file size than a traditional font. The file is larger than a single ordinary font,<sup>12</sup> so it saves anything only when a product would otherwise load several styles.&#x20;

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Design token](../../design-terms/design-token.md) · [Fallback font](fallback-font.md) · [Faux bold](faux-bold.md) · [Font](font.md) · [Font subsetting](font-subsetting.md) · [Font weight](font-weight.md) · [Language](../../language-terms/linguistics/language.md) · [OpenType](opentype.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Typeface](typeface.md) · [Font terms](./)

### Further reading

* Code & specs: [Variable fonts (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [OpenType Font Variations Overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)

### Sources

1. "OpenType Font Variations allow a font designer to incorporate multiple font faces within a font family into a single font resource" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
2. "A font resource that supports multiple font faces in a family along designer-defined axes of variation using OpenType Font Variations mechanisms" - OpenType Font Variations Overview: Terminology, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview#terminology](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview#terminology)
3. "A variable font allows for continuous variation along some given design axis, such as weight" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
4. "each font would represent one specific width/weight/style combination" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
5. "Each axis is defined by a numeric range" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
6. "The five currently registered axes are weight, width, slant, italic, and optical size" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
7. "Fonts may use tags defined in this registry, or may use foundry-defined tags" - OpenType Design-Variation Axis Tag Registry, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg](https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg)
8. "the designer may identify particular variation instances as “Light” or “Semibold”" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
9. "Variable fonts are an evolution of the OpenType font specification" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
10. "Variable fonts, where the font designer has provided one or more axes of variation do not count as font synthesis" - CSS Fonts Module Level 4, W3C Working Draft: 2.8. Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
11. "Fractional weights are valid" - CSS Fonts Module Level 4, W3C Working Draft: 2.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-4/#font-weight-prop](https://www.w3.org/TR/css-fonts-4/#font-weight-prop)
12. "That file would be larger than a single font" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
13. "A variable font includes a table, the font variations ('fvar') table, that describes the axes of variation used by that font" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
14. "if an application specifies a value greater than the maxValue defined in the font, then maxValue must be used" - fvar: Font Variations Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/fvar](https://learn.microsoft.com/en-us/typography/opentype/spec/fvar)
15. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation: 5. Font Matching Algorithm [https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm](https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm)
16. "When a weight is specified for which no face exists, a face with a nearby weight is used" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
17. "If the font you’re using is a variable font, you’ll also see a Variable tab" - Explore text properties, Figma Learn [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
