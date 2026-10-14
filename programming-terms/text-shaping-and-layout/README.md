# Text shaping & layout

## Text shaping and layout ensures readability

In programming, there are many processes that happen under the hood to ensure text is stored and displayed properly. Text shaping and layout processes ensures each piece of text you see on your screen is displayed correctly based on your language preferences and the localization conventions that come along with it.&#x20;

### Why it matters

Computers store text as binary code, according to the [Unicode](../text-in-software/unicode.md) standard, that gives every [character](../text-in-software/character.md) in the world's writing systems a unique number.<sup>1</sup>

Between the characters a system stores and the text a person reads, something has to decide which shapes of a font to draw and where to put them on the page. That step is called text shaping. When a design system supports multiple languages, writing systems, and scripts, the text shaping process becomes more important.&#x20;

For example, in English and many other languages that use a Latin script, Text shaping looks like it does nothing: one character comes in, one glyph goes out, placed to the right of the last one.&#x20;

For many other scripts it has much more to work out. Letters change shape depending on their neighbours, marks are positioned over or under a base, pairs merge into a single form, and some vowel marks are drawn in a different order than they were typed.

A tool that places glyphs without shaping them will render Arabic as disconnected letters and Devanagari with its vowel marks in the wrong place, using a font that is perfectly capable of doing better.

That is why the advice throughout this glossary is to test in the real design tools and the real browser, not only to confirm that a font covers a script.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every shaping feature. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### The shaping step

What shaping is, what does it, and which scripts need more of it than others. Text shaping is the parent of every other term in this section: the software that does it, another name for it, the instructions it reads from the font, and what it produces.

[**Text shaping**](../text-for-digital-products-and-the-web/text-shaping.md)

Text shaping is the step in which software works out which of a font's shapes to draw for a piece of text, and where each shape goes.

[**Shaping engine**](../text-for-digital-products-and-the-web/shaping-engine.md)

A shaping engine is the software that works out which of a font's shapes to draw for a piece of text, and where each shape goes.

[**Complex text layout**](../text-for-digital-products-and-the-web/complex-text-layout.md)

Complex text layout is a name for text shaping in the scripts where shaping has the most to do: where the right shape or position of a character depends on the characters around it, or characters are drawn in a different order from the one they are stored in.

#### What shaping does to the glyphs

Shaping swaps glyphs for other glyphs, moves them relative to one another, and in some scripts changes the order they are drawn in. A font carries the instructions for the first two jobs, in two separate lists. Changing the order is done by the shaping software.

[**GSUB**](../text-for-digital-products-and-the-web/gsub.md)

GSUB is the part of a font file that lists which shapes to swap for other shapes, and when.

[**GPOS**](../text-for-digital-products-and-the-web/gpos.md)

GPOS is the part of a font file that tells software where to place each shape in relation to the shapes around it.

[**Ligature**](../text-for-digital-products-and-the-web/ligature.md)

A ligature is a single glyph, a shape in a font, that stands for two or more characters at once.

[**Reordering**](../text-for-digital-products-and-the-web/reordering.md)

Reordering is a step in drawing text in which software draws some symbols in a different order from the order they are stored in.

### Where to go next

* Many of the instructions shaping relies on live inside the font file: see [Fonts](../../design-terms/fonts/).
* The characters going into shaping are covered in [Text in software](../text-in-software/).
* Which direction a line runs, and what happens when two directions meet, is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
