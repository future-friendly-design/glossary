# Font terms

## Fonts provide the shapes of written content

When your design system chooses a [typeface](../../design-terms/typography/typeface.md), it is choosing the visual identity of written content. In programming, each typeface comes as one or more font files, which software loads and then reads during [text shaping](../text-shaping-and-layout/text-shaping.md). Text needs both: the font, and a [shaping engine](../text-shaping-and-layout/shaping-engine.md), the software that uses it.&#x20;

A [font](../text-for-digital-products-and-the-web/font.md) is a file that holds the shape for each character of text, called a [glyph](../text-for-digital-products-and-the-web/glyph.md), plus instructions for how to swap and place those glyphs during the text shaping process. A font has a limited number of glyphs specific to the script or scripts it was designed to support.&#x20;

Text shaping happens before text appears on a screen: software reads the font file and picks the right shapes (glyphs) for each character of text and decides where they go. When the text contains a character the font doesn’t have a glyph for, the software either borrows a shape from another font, called a [fallback font](../text-for-digital-products-and-the-web/fallback-font.md), or shows an empty box, called [tofu](../../design-terms/typography/tofu.md).&#x20;



### Why it matters

Choosing fonts for a multilingual product needs to be done with care. A font that looks right in the English brand deck may have no Arabic glyphs which means you need to choose a fallback font.&#x20;

#### Example

Set a page in a font made only for the Latin script, then show an Amharic name in it. The name does not appear in the style you chose. It appears as empty boxes, or in whatever unrelated font the operating system finds first. Neither outcome is a type decision anyone made on purpose.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every font format, feature, and control. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### Typeface, font, glyph

Three words used interchangeably in conversation that mean three different things in a spec, a licence, and a build.

* [Font](../text-for-digital-products-and-the-web/font.md)
* [Glyph](../text-for-digital-products-and-the-web/glyph.md)
* [Typeface](../../design-terms/typography/typeface.md)

One more term shares the word "script" without sharing the meaning. A [script typeface](../../design-terms/typography/script-typeface.md) is a style of lettering that imitates handwriting; a [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols used to write a language. The category comes from Latin type; other scripts have handwriting-based styles of their own.

* [Script (typeface)](../../design-terms/typography/script-typeface.md)

#### What is inside a font file

Beyond the shapes themselves, a font carries the instructions that let text be set correctly: which glyphs may replace or combine with which, how marks are positioned, and which stylistic options a designer can switch on.

* [OpenType](../../design-terms/typography/opentype.md)
* [OpenType features](../../design-terms/typography/opentype-features.md)
* [Font weight](../../design-terms/typography/font-weight.md)
* [Variable font](../../design-terms/typography/variable-font.md)

#### Coverage, and what happens without it

A font covers the characters it was drawn for and no others. When text asks for something a font lacks, the result is either a substitute font or a visible gap, and both are worth designing for deliberately.

* [Fallback font](../text-for-digital-products-and-the-web/fallback-font.md)
* [Font coverage](../text-for-digital-products-and-the-web/font-coverage.md)
* [Noto fonts](../../design-terms/typography/noto-fonts.md)
* [Tofu](../../design-terms/typography/tofu.md)

#### Shipping fonts

What you load costs bandwidth, and what you fail to load gets faked by the browser. Both have visible consequences.

* [Faux bold](../text-for-digital-products-and-the-web/faux-bold.md)
* [Faux italic](../text-for-digital-products-and-the-web/faux-italic.md)
* [Font subsetting](../text-for-digital-products-and-the-web/font-subsetting.md)

### Where to go next

* Having the right font is necessary but not sufficient: see [Text shaping & layout terms](../text-shaping-and-layout/) for the step that puts the glyphs in the right places.
* How type is sized and spaced once the font is chosen is covered in [Typography](../../design-terms/typography/).
* What the scripts a font must cover actually require is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
