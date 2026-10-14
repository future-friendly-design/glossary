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

A variable font is a font file that holds a whole range of styles of a typeface, where an ordinary font file holds one.<sup>1</sup>

A variable font is a kind of [font](font.md), the file that holds the shapes software uses to show text.<sup>2</sup>

The styles are not stored one by one. The file stores how the design changes between two ends, such as its lightest and its heaviest, and software can produce any point in between.<sup>3</sup> Each of those lines of change is called an axis.

### Why it matters in design systems

A style menu usually offers a short list: Light, Regular, Semibold, Bold. Behind each name on that list there is normally a separate font file, because an ordinary font holds a single style.<sup>4</sup> With a variable font the list becomes a slider.

An axis is one way the design can change, written as a range of numbers that the type designer sets inside the file.<sup>5</sup> Weight is the one most people meet first. Five axes have agreed names (weight, width, slant, italic and optical size),<sup>6</sup> and a type designer can add others of their own.<sup>7</sup> The designer can also give familiar names to points along an axis, so a variable font can still show Light and Semibold in a style menu the way an ordinary [typeface](typeface.md) family does.<sup>8</sup> Variable fonts are a later addition to [OpenType](opentype.md), a common font file format.<sup>9</sup>

Two things follow for a design system. The first is quality. A weight taken from a variable font is worked out from the type designer's own drawings, and it is not counted as a fake, unlike [faux bold](faux-bold.md), where a browser thickens the regular shapes because no bold was available.<sup>10</sup> The second is that [font weight](font-weight.md) becomes a real number. A [token](../../design-terms/design-token.md) can ask for 550, or even 425.5,<sup>11</sup> where separate files offer only the weights somebody chose to make.

A variable font is not automatically the smaller download. The file is larger than a single ordinary font,<sup>12</sup> so it saves anything only when a product would otherwise load several styles. Count the styles you really use before deciding.

The limit that matters most in a product with more than one language is that every font has its own axes and its own ranges.<sup>13</sup> Asking for a value outside a font's range is not an error. The value is pulled back to the nearest end of the range.<sup>14</sup> Software chooses a font for each character,<sup>15</sup> so text in each [script](../../language-terms/writing-systems-and-scripts/script.md) is usually shown in a different font in the font list, the ordered list of fonts a product names, and those fonts were made separately. One may be variable with a wide weight range, another variable with a narrow one, and a third not variable at all. Here is one weight token meeting three such fonts, where the two ordinary files follow a browser's rule for a missing weight:<sup>16</sup>

| Weight asked for | Variable font, range 100 to 900 | Variable font, range 400 to 700 | Two ordinary files, 400 and 700 |
| ---------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| 300              | 300                             | 400                             | 400                             |
| 550              | 550                             | 550                             | 700                             |
| 800              | 800                             | 700                             | 700                             |

A heading set at 800 comes out heavier in one script than in the two beside it, on the same page, from the same token.

So treat "variable" as a fact about one file, not about your whole type system. For each font in the font list, record whether it is variable, which axes it has, and the range of each. Keep weight tokens inside the range that every script can honour, or accept the difference on purpose. Design tools show the same limits: in Figma, a variable font adds a Variable tab to the type settings,<sup>17</sup> and a value chosen there only reaches the product if the font file the product ships has that axis and that range.

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
