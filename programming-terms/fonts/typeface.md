---
term: Typeface
slug: typeface
aliases:
  - type family
  - font family
level: foundational
depth: deep
summary: >-
  A typeface is the design shared by a set of written symbols, such as letters,
  numbers and marks.
related:
  - font
  - font-weight
  - variable-font
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: font-family (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-family
    type: code
  - title: Explore text properties (Figma Learn)
    url: >-
      https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
  - title: Glossary (Monotype)
    url: https://support.monotype.com/en/articles/8949273-glossary
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Typeface

## Definition

A typeface is the design shared by a set of written symbols, such as letters, numbers and marks.<sup>1</sup>

It is what makes a page of type look like one thing: the same proportions, the same kind of stroke, the same small details from one symbol to the next. A typeface is not a file. The files that carry a typeface into software are called [fonts](font.md).<sup>2</sup> One typeface is usually delivered as several of them.

### Why it matters in design systems

When someone admires a poster and asks "what font is that?", the thing they are admiring is a typeface. Monotype, a type foundry, puts the whole difference in one line: "A font is what you use, and a typeface is what you see."<sup>3</sup>

In everyday talk the two words are often used as if they meant the same thing.<sup>4</sup> A design system is one of the places where they cannot be, because it has to answer questions about looks and questions about files, and those questions usually land with different people:

| Question                                                                                   | Typeface or fonts?                                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| What should our product look like?                                                         | The typeface.                                                                                    |
| What do we hold a licence for?                                                             | The fonts. A licence is permission to use font software.<sup>5</sup>                             |
| What does a page download?                                                                 | The fonts, one file at a time.                                                                   |
| What does a [token](../../design-terms/design-token.md) called "brand" or "body" point to? | A typeface, by its family name. Software then has to match that name to a font file.<sup>6</sup> |
| Which languages can we show?                                                               | The fonts, because the shapes are held in the files.<sup>7</sup>                                 |

A typeface normally comes as a family, the same design in several weights, widths and slants.<sup>8</sup> Each member is delivered as its own font, unless the family is built as a [variable font](variable-font.md), where one file holds a range. So "we use this typeface" does not yet say which weights, which styles or which files, and a design system has to say all three.

The web has its own words for this. CSS, the styling language of the web, calls the family a font family, so a designer who writes "typeface" in a specification should expect to find it as `font-family` in the code.<sup>9</sup>

### Common mistake

Choosing a typeface in one script and assuming it will be there in the others. A typeface is drawn for particular scripts, and one drawn for the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) has nothing to offer Thai or Arabic text. Extending a design to another [script](../../language-terms/writing-systems-and-scripts/script.md) is new design work, and it needs someone who knows how that script is written and read.<sup>10</sup> Even the list of styles in a family does not carry across. Italic belongs to some traditions and not to others, and fonts for Chinese, Japanese and Korean almost always come without one,<sup>11</sup> so a rule such as "use italic for emphasis" has nothing to call on in those scripts. A brand typeface is a decision for the scripts it was drawn for. Every other script the product uses needs a decision of its own.

### In practice

* **Choose a companion typeface for each script.** For every script your languages are written in, pick a typeface that sits well beside the one you already have, in weight and in tone, and have someone who reads that script judge it. A person who cannot read the script can only compare shapes, not how the text reads.
* **Name tokens by role, not by typeface.** A token called `font-family-body` can stand for one typeface in Latin text and another in Arabic text. A token named after a single typeface cannot do that without becoming untrue.
* **Look at the family before you rely on it.** In Figma you choose the font family first, then a weight or style from the field directly beneath it.<sup>12</sup> That second menu shows what the family really has, and every family has its own selection.<sup>13</sup> A [weight](font-weight.md) or an italic that is missing there is missing in the product too, where software may fake it instead (see [faux bold](faux-bold.md) and [faux italic](faux-italic.md)).

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Design token](../../design-terms/design-token.md) · [Faux bold](faux-bold.md) · [Faux italic](faux-italic.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font weight](font-weight.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script (typeface)](../../design-terms/typography/script-typeface.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Variable font](variable-font.md) · [Font terms](./)

### Further reading

* Code & specs: [font-family (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [Glossary (Monotype)](https://support.monotype.com/en/articles/8949273-glossary)

### Sources

1. "A typeface (or font family) is a design of letters, numbers and other symbols, to be used in printing or for electronic display" - Glossary: Font family/Family/Typeface, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
2. "font refers to the physical embodiment (whether it’s a case of metal pieces or a computer file) while typeface refers to the design (the way it looks)" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
3. "A font is what you use, and a typeface is what you see" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
4. "Although font and typeface are often used interchangeably" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
5. "A font license (also known as EULA or end-user license agreement) is a legally binding document authorizing you to use font software under pre-defined conditions" - Glossary: Font license, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
6. "For a given range of text, CSS font properties are used to select a font family and a specific font face within that family to be used when rendering that text" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
7. "At the simplest level it contains information that maps character codes to shapes (called glyphs) that represent these characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
8. "Within a family, the shape displayed for a given character can vary by stroke weight, slant or relative width, among others" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
9. "Fonts sharing a common design style are commonly grouped into font families classified by a set of standard font properties" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
10. "Creating fonts that support multiple scripts is a difficult task; designers need to understand the cultural traditions surrounding the use of type in different scripts and come up with letterforms that somehow share a common theme" - CSS Fonts Module Level 3, W3C Recommendation: 2. Typography Background [https://www.w3.org/TR/css-fonts-3/#typography-background](https://www.w3.org/TR/css-fonts-3/#typography-background)
11. "Many scripts lack the tradition of mixing a cursive form within text rendered with a normal face. Chinese, Japanese and Korean fonts almost always lack italic or oblique faces" - CSS Fonts Module Level 3, W3C Recommendation: 3.4. Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
12. "Adjust the font-weight using the field directly below the font family" - Explore text properties, Figma Learn [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
13. "Every font family will come with its own selection of styles" - Explore text properties, Figma Learn [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
