# Font terms

## Fonts provide the shapes of written content

When your design system chooses a [typeface](typeface.md), it is choosing the visual identity of written content. In programming, each typeface comes as one or more font files, which software loads and then reads during [text shaping](../text-shaping-and-layout/text-shaping.md). Text needs both: the font, and a [shaping engine](../text-shaping-and-layout/shaping-engine.md), the software that uses it.

A [font](font.md) is a file that holds the shape for each character of text, called a [glyph](glyph.md), plus instructions for how to swap and place those glyphs during the text shaping process. A font has a limited number of glyphs specific to the script or scripts it was designed to support.

Text shaping happens before text appears on a screen: software reads the font file and picks the right shapes (glyphs) for each character of text and decides where they go. When the text contains a character the font doesn’t have a glyph for, the software either borrows a shape from another font, called a [fallback font](fallback-font.md), or shows an empty box, called [tofu](tofu.md).

### Why it matters

Choosing fonts for a multilingual product needs to be done with care. A font that looks right in the English brand deck may have no Arabic glyphs which means you need to choose a fallback font.

#### Example

Set a page in a font made only for the Latin script, then show an Amharic name in it. The name does not appear in the style you chose. It appears as empty boxes, or in whatever unrelated font the operating system finds first. Neither outcome is a type decision anyone made on purpose.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every font format, feature, and control. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### The font and its design

Font is the parent of every term in this section: what a font holds, the format it is stored in, what it covers, and what happens when it falls short.

Typeface and font are used interchangeably in conversation, but they mean different things in a spec, a licence and a build. A typeface is the design. A font is the file that holds it, as a set of glyphs.

[**Typeface**](typeface.md)

A typeface is the design shared by a set of written symbols, such as letters, numbers and marks.

[**Font**](font.md)

A font is a file that holds the shapes software uses to show text.

[**Glyph**](glyph.md)

A glyph is the specific visual shape a font holds for a character.

[**Font weight**](font-weight.md)

Font weight is how thick the strokes of a font are, from very thin to very heavy.

[**Variable font**](variable-font.md)

A variable font is a font file that holds a whole range of styles of a typeface, where an ordinary font file holds one.

One more term shares the word "script" without sharing the meaning. A script typeface is a style of lettering that imitates handwriting; a [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols used to write a language. The category comes from Latin type; other scripts have handwriting-based styles of their own.

[**Script (typeface)**](../../design-terms/typography/script-typeface.md)

A script typeface is a typeface drawn to look like handwriting.

#### Inside the font file

Beyond the shapes themselves, a font carries the instructions that text shaping reads: which glyphs to swap for others, where to place each one, and which optional styles a designer can switch on.

[**OpenType**](opentype.md)

OpenType is a font file format, and it is the most widely used one.

[**OpenType features**](opentype-features.md)

OpenType features are named groups of instructions inside a font file, each one telling software how to swap or place the font's shapes for one purpose.

[**GSUB**](gsub.md)

GSUB is the part of a font file that lists which shapes to swap for other shapes, and when.

[**GPOS**](gpos.md)

GPOS is the part of a font file that tells software where to place each shape in relation to the shapes around it.

[**Ligature**](ligature.md)

A ligature is a single glyph, a shape in a font, that stands for two or more characters at once.

#### When the font falls short

A font holds shapes only for the characters it was made for. When the text needs something the font does not have, software borrows a shape from another font, shows an empty box, or fakes a style the font does not include. Each of these is worth designing for on purpose.

[**Font coverage**](font-coverage.md)

Font coverage is the set of characters that a font file holds a shape for.

[**Fallback font**](fallback-font.md)

A fallback font is a font that software uses in place of the one you chose, either because your font is not available or because it holds no shape for a character in the text.

[**Tofu**](tofu.md)

Tofu is the nickname for the empty box that appears in place of a character when no font available to the software holds a shape for it.

[**Faux bold**](faux-bold.md)

Faux bold is an imitation of bold text that software makes by thickening the shapes of a regular font, because it has no bold font to use.

[**Faux italic**](faux-italic.md)

Faux italic is an imitation of italic text that software makes by slanting the shapes of a regular font, because it has no italic font to use.

#### Getting fonts to people

Where fonts for many scripts come from, and how to load only the part of a font a product needs.

[**Noto fonts**](noto-fonts.md)

The Noto fonts are a collection of free fonts, directed by Google, that aims to provide a font for every script in Unicode.

[**SIL fonts**](sil.md)

SIL fonts are a collection of free fonts from SIL Global, made for languages that most fonts do not support well.

[**Font subsetting**](font-subsetting.md)

Font subsetting is the practice of making a smaller copy of a font file by keeping only the shapes and instructions needed for the characters a product expects to use.

### Where to go next

* Having the right font is necessary but not sufficient: see [Text shaping & layout terms](../text-shaping-and-layout/) for the step that puts the glyphs in the right places.
* How type is sized and spaced once the font is chosen is covered in [Typography](../../design-terms/typography/).
* What the scripts a font must cover actually require is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
