# Fonts

## The files you ship, and what is inside them

A typeface is a design.
A font is a file.
You can admire a typeface, but the thing you load, licence, subset, and pay for in page weight is a font, and the difference starts to matter the moment a product ships in more than one language.

A font file holds drawn shapes, called glyphs, plus instructions for how to combine and position them.
It does not hold every character in the world, and no font does.
What a font covers, and what happens when it runs out of coverage, is the question this section keeps returning to.

### Why it matters

Choosing type for a multilingual product is not the same job as choosing type for an English one.
A family that looks right in the brand deck may have no Arabic, no Devanagari, and no Cyrillic, and the fallback that quietly steps in for the missing text will not match the weight, the width, or the height of everything around it.

The decisions this section supports are concrete: which families to adopt, which cuts to load, what to name in a token, what to test before launch, and what your product should do when a person's name contains a character your font never anticipated.

#### Example

Set a page in a font drawn only for Latin, then render an Amharic name in it.
The name does not render in a different style, it renders as empty boxes, or in whatever unrelated font the operating system finds first.
Neither outcome is a type decision anyone made on purpose.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every font format, feature, and control; its coverage follows the questions that came up in the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### Typeface, font, glyph

Three words used interchangeably in conversation that mean three different things in a spec, a licence, and a build.

* [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md)
* [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md)
* [Typeface](../typography/typeface.md)

One more term shares the word "script" without sharing the meaning. A [script typeface](../typography/script-typeface.md) is a style of lettering that imitates handwriting; a [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols used to write a language. A script typeface is almost always a Latin one.

* [Script (typeface)](../typography/script-typeface.md)

#### What is inside a font file

Beyond the shapes themselves, a font carries the instructions that let text be set correctly: which glyphs may replace or combine with which, how marks are positioned, and which stylistic options a designer can switch on.

* [OpenType](../typography/opentype.md)
* [OpenType features](../typography/opentype-features.md)
* [Font weight](../typography/font-weight.md)
* [Variable font](../typography/variable-font.md)

#### Coverage, and what happens without it

A font covers the characters it was drawn for and no others. When text asks for something a font lacks, the result is either a substitute font or a visible gap, and both are worth designing for deliberately.

* [Fallback font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md)
* [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md)
* [Noto fonts](../typography/noto-fonts.md)
* [Tofu](../typography/tofu.md)

#### Shipping fonts

What you load costs bandwidth, and what you fail to load gets faked by the browser. Both have visible consequences.

* [Faux bold](../../programming-terms/text-for-digital-products-and-the-web/faux-bold.md)
* [Faux italic](../../programming-terms/text-for-digital-products-and-the-web/faux-italic.md)
* [Font subsetting](../../programming-terms/text-for-digital-products-and-the-web/font-subsetting.md)

### Where to go next

* Having the right font is necessary but not sufficient: see [Text shaping & layout](../../programming-terms/text-shaping-and-layout/) for the step that puts the glyphs in the right places.
* How type is sized and spaced once the font is chosen is covered in [Typography](../typography/).
* What the scripts a font must cover actually require is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
