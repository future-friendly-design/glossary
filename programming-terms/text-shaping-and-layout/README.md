# Text shaping & layout

## How stored characters become the right shapes

Between the characters a system stores and the text a person reads, something has to decide which shapes to draw and where to put them.
That step is called shaping.

For a lot of Latin text, shaping looks like it does nothing: one character comes in, one glyph goes out, placed to the right of the last one.
For most of the world's scripts it does a great deal.
Letters change shape depending on their neighbours, marks are positioned over or under a base, pairs merge into a single form, and some vowel marks are drawn in a different order than they were typed.

### Why it matters

This is the step that explains a failure designers meet often and rarely have a name for: the font is correct, the characters are correct, and the text still renders wrong.
A font that contains every shape a script needs is necessary but not sufficient.
A tool that places glyphs without shaping them will render Arabic as disconnected letters and Devanagari with its vowel marks in the wrong place, using a font that is perfectly capable of doing better.

That is why the advice throughout this glossary is to test in the real design tools and the real browser, not only to confirm that a font covers a script.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every shaping feature; its coverage follows the scripts and questions that came up in the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### The shaping step

What shaping is, what does it, and which scripts need more of it than others.

* [Complex text layout](../text-for-digital-products-and-the-web/complex-text-layout.md)
* [Shaping engine](../text-for-digital-products-and-the-web/shaping-engine.md)
* [Text shaping](../text-for-digital-products-and-the-web/text-shaping.md)

#### What shaping does to the glyphs

Shaping either swaps glyphs for other glyphs, or moves them relative to one another. Those two jobs have names, because a font has to carry the instructions for each separately.

* [GPOS](../text-for-digital-products-and-the-web/gpos.md)
* [GSUB](../text-for-digital-products-and-the-web/gsub.md)
* [Ligature](../text-for-digital-products-and-the-web/ligature.md)
* [Reordering](../text-for-digital-products-and-the-web/reordering.md)

### Where to go next

* The instructions shaping relies on live inside the font file: see [Fonts](../../design-terms/fonts/).
* The characters going into shaping are covered in [Text in software](../text-in-software/).
* Which direction a line runs, and what happens when two directions meet, is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
