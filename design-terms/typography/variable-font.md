---
term: Variable font
slug: variable-font
aliases:
  - VF
  - OpenType variable font
level: intermediate
depth: core
summary: A variable font is a font file that holds a whole range of styles of a typeface, where an ordinary font file holds one.
related:
  - font-weight
  - typeface
  - font
  - font-subsetting
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Variable fonts (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide
    type: code
  - title: Explore text properties (Figma Learn)
    url: https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
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

A variable font is a font file that holds a whole range of styles of a typeface, where an ordinary font file holds one.<sup>1</sup>

The styles are not stored one by one. The file stores how the design changes between two ends, such as its lightest and its heaviest, and software can produce any point in between.<sup>2</sup> Each of those lines of change is called an axis.

### Why it matters in design systems

A style menu usually offers a short list: Light, Regular, Semibold, Bold. Behind each name on that list there is normally a separate [font](../../programming-terms/text-for-digital-products-and-the-web/font.md) file, because an ordinary font holds a single style.<sup>3</sup> With a variable font the list becomes a slider.

An axis is one way the design can change, written as a range of numbers that the type designer sets inside the file.<sup>4</sup> Weight is the one most people meet first. Five axes have agreed names (weight, width, slant, italic and optical size),<sup>5</sup> and a type designer can add others of their own.<sup>6</sup> The designer can also give familiar names to points along an axis, so a variable font can still show Light and Semibold in a style menu the way an ordinary [typeface](typeface.md) family does.<sup>7</sup> Variable fonts are a later addition to [OpenType](opentype.md), a common font file format.<sup>8</sup>

Two things follow for a design system. The first is quality. A weight taken from a variable font is the type designer's own drawing at that weight, and it is not counted as a fake, unlike [faux bold](../../programming-terms/text-for-digital-products-and-the-web/faux-bold.md), where a browser thickens the regular shapes because no bold was available.<sup>9</sup> The second is that [font weight](font-weight.md) becomes a real number. A token can ask for 550, or even 425.5,<sup>10</sup> where separate files offer only the weights somebody chose to export.

A variable font is not automatically the smaller download. The file is larger than a single ordinary font,<sup>11</sup> so it saves anything only when a product would otherwise load several styles. Count the styles you really use before deciding.

The limit that catches multilingual products is that every font has its own axes and its own ranges.<sup>12</sup> Asking for a value outside a font's range is not an error. The value is pulled back to the nearest end of the range.<sup>13</sup> Software chooses a font for each character,<sup>14</sup> so text in each [script](../../language-terms/writing-systems-and-scripts/script.md) is usually drawn from a different font in the font list, and those fonts were made separately. One may be variable with a wide weight range, another variable with a narrow one, and a third not variable at all. Here is one weight token meeting three such fonts, where the two ordinary files follow the browser's nearest-weight rule:<sup>15</sup>

| Weight asked for | Variable font, range 100 to 900 | Variable font, range 400 to 700 | Two ordinary files, 400 and 700 |
| ---------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| 300 | 300 | 400 | 400 |
| 550 | 550 | 550 | 700 |
| 800 | 800 | 700 | 700 |

A heading set at 800 comes out heavier in one script than in the two beside it, on the same page, from the same token.

So treat "variable" as a fact about one file, not about your whole type system. For each font in the font list, record whether it is variable, which axes it has, and the range of each. Keep weight tokens inside the range that every script can honour, or accept the difference on purpose. Design tools show the same limits: in Figma, a variable font adds a Variable tab to the type settings,<sup>16</sup> and a value chosen there only reaches the product if the font file the product ships has that axis and that range.

***

### Related terms and mentions

[Character](../../programming-terms/text-in-software/character.md) · [Fallback font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md) · [Faux bold](../../programming-terms/text-for-digital-products-and-the-web/faux-bold.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font subsetting](../../programming-terms/text-for-digital-products-and-the-web/font-subsetting.md) · [Font weight](font-weight.md) · [OpenType](opentype.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Typeface](typeface.md) · [Fonts](../fonts/)

### Further reading

* Code & specs: [Variable fonts (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [OpenType Font Variations Overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)

### Sources

1. "OpenType Font Variations allow a font designer to incorporate multiple font faces within a font family into a single font resource" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
2. "A variable font allows for continuous variation along some given design axis, such as weight" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
3. "A regular static font can only contain one font per file" - Explore text properties, Figma Learn [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
4. "Each axis is defined by a numeric range" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
5. "The five currently registered axes are weight, width, slant, italic, and optical size" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
6. "Fonts may use tags defined in this registry, or may use foundry-defined tags" - OpenType Design-Variation Axis Tag Registry, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg](https://learn.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg)
7. "the designer may identify particular variation instances as “Light” or “Semibold”" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
8. "Variable fonts are an evolution of the OpenType font specification" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
9. "Variable fonts, where the font designer has provided one or more axes of variation do not count as font synthesis" - CSS Fonts Module Level 4, W3C Working Draft: 2.8. Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
10. "Fractional weights are valid" - CSS Fonts Module Level 4, W3C Working Draft: 2.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-4/#font-weight-prop](https://www.w3.org/TR/css-fonts-4/#font-weight-prop)
11. "That file would be larger than a single font" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
12. "A variable font includes a table, the font variations ('fvar') table, that describes the axes of variation used by that font" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
13. "if an application specifies a value greater than the maxValue defined in the font, then maxValue must be used" - fvar: Font Variations Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/fvar](https://learn.microsoft.com/en-us/typography/opentype/spec/fvar)
14. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation: 5. Font Matching Algorithm [https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm](https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm)
15. "When a weight is specified for which no face exists, a face with a nearby weight is used" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
16. "If the font you’re using is a variable font, you’ll also see a Variable tab" - Explore text properties, Figma Learn [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
