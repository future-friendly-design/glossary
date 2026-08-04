# Text in software

## How software stores text

When a person writes, they produce visible symbols and marks on a surface.
When software stores that same writing, it becomes numbers, and those numbers become bytes.

Nothing in that trip is one to one.
What a reader counts as one character may be several numbers underneath, and the shape on screen is drawn by a font that was never involved in the storing.
Most text bugs come from treating one of those layers as if it were another.

### Why it matters

Almost every text problem a design system runs into is a layer confusion: a name field that cuts an accented letter in half, a search that fails to match two spellings that look identical, a character limit that counts one emoji as four.
Knowing which layer you are standing on tells you which tool fixes the problem.

#### The layers, from writing to bytes

Each row is a different answer to the question "how many characters is this?", using the accented letter é as the example.

| Layer | What it is | é |
|---|---|---|
| [Grapheme](../text-for-digital-products-and-the-web/grapheme.md) | the unit of writing itself, before software | one grapheme |
| [Character](../text-for-digital-products-and-the-web/character.md) | the unit Unicode encodes | one character, or two |
| [Code point](../text-for-digital-products-and-the-web/code-point.md) | the number Unicode assigns | U+00E9, or U+0065 followed by U+0301 |
| [Grapheme cluster](../text-for-digital-products-and-the-web/grapheme-cluster.md) | what a reader counts as one character | one cluster, either way |
| [Glyph](../text-for-digital-products-and-the-web/glyph.md) | the shape a font draws | whatever that font contains |
| [Character encoding](../text-for-digital-products-and-the-web/character-encoding.md) | the bytes it is stored as | two bytes, or three |

The gap between the rows widens outside the Latin script.
In Devanagari, नमस्ते is six characters that a reader sees as three written units, so a "six character" limit and a reader counting on their fingers will disagree.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every part of the text model; its coverage follows the questions that came up in the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### Unicode and its numbers

Unicode is the shared agreement that gives every character a number, so text can move between systems without falling apart.

* [Code point](../text-for-digital-products-and-the-web/code-point.md)
* [Plane / Basic Multilingual Plane](../text-for-digital-products-and-the-web/plane-bmp.md)
* [Surrogate pair](../text-for-digital-products-and-the-web/surrogate-pair.md)
* [Unicode](../text-for-digital-products-and-the-web/unicode.md)
* [Unicode Standard](../text-for-digital-products-and-the-web/unicode-standard.md)

#### Storing text as bytes

A code point is a number, not a file. An encoding is the rule that turns those numbers into bytes and back again, and the reason a file opened with the wrong rule comes out as garbage.

* [Character encoding](../text-for-digital-products-and-the-web/character-encoding.md)
* [UTF-8](../text-for-digital-products-and-the-web/utf-8.md)
* [UTF-16](../text-for-digital-products-and-the-web/utf-16.md)

#### Characters that combine

Some characters attach to the one before them instead of standing on their own, which is how an accent, a vowel mark, or an enclosing shape is encoded. The same visible letter can often be stored either as one character or as a base plus a mark, and normalization is what makes those two forms compare as equal.

* [Combining mark](../text-for-digital-products-and-the-web/combining-mark.md)
* [Enclosing mark](../text-for-digital-products-and-the-web/enclosing-mark.md)
* [Normalization](../text-for-digital-products-and-the-web/normalization.md)
* [Precomposed character](../text-for-digital-products-and-the-web/precomposed-character.md)
* [Spacing combining mark](../text-for-digital-products-and-the-web/spacing-combining-mark.md)

#### Counting and splitting text

Where one "character" ends and the next begins is a question with several answers, and picking the wrong one is what slices an emoji or an accented letter in half.

* [Grapheme](../text-for-digital-products-and-the-web/grapheme.md)
* [Grapheme cluster](../text-for-digital-products-and-the-web/grapheme-cluster.md)
* [Segmentation](../text-for-digital-products-and-the-web/segmentation.md)

#### Character forms

Some characters exist in more than one width or form, which affects how text lines up in a column.

* [Full-width](../text-for-digital-products-and-the-web/full-width.md)

### Where to go next

* The shapes these characters turn into are covered in [Text shaping & layout](../text-shaping-and-layout/) and [Fonts](../../design-terms/fonts/).
* The writing systems being represented are covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/).
* Building a product for more than one language is covered in [Multi-language products](../multi-language-products/).
