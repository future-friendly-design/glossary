---
term: Enclosing mark
slug: enclosing-mark
aliases: []
level: advanced
depth: core
summary: An enclosing mark is a character that draws a shape around the character before it, such as a circle or a box.
related:
  - combining-mark
  - mark
  - character
  - spacing-combining-mark
  - grapheme-cluster
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Enclosing Mark (Unicode Glossary)
    url: https://www.unicode.org/glossary/#enclosing_mark
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Enclosing mark

## Definition

An enclosing mark is a [character](character.md) that draws a shape around the character before it, such as a circle or a box.

For example, the keycap `1️⃣` is three characters: the digit `1`, an invisible character that asks for the emoji style (U+FE0F), and an enclosing mark (U+20E3) that draws the box around it.<sup>1</sup>

### Why it matters in design systems

Some text puts a ring or a box around something and expects the two to travel together: a digit inside a circle, a key on a keyboard drawn as a labelled square. One way the computer can store that is as separate characters: the thing being enclosed, and a second character whose only job is to wrap around whatever came before it. The enclosing mark is that second character, and like any [combining mark](combining-mark.md) it cannot stand on its own.

That makes it the third and last member of [Unicode](unicode.md)'s Mark category, alongside the nonspacing combining mark, which adds no width, and the [spacing combining mark](spacing-combining-mark.md), which does.<sup>2</sup> General Category Me, it is a kind of nonspacing mark that wraps around its base rather than sitting above or beside it.<sup>3</sup> For software the same rule applies as for other combining marks: the base and the enclosing mark together are a single [grapheme cluster](grapheme-cluster.md), one unit as far as a reader is concerned, so cursor movement, selection, and counting should treat them as one, not two.<sup>4</sup>

***

### Related terms and mentions

[Character](character.md) · [Combining mark](combining-mark.md) · [Grapheme cluster](grapheme-cluster.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Spacing combining mark](spacing-combining-mark.md) · [Unicode](unicode.md) · [Text encoding & character terms](./)

### Further reading

* Foundations: [Enclosing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#enclosing_mark)

### Sources

1. An emoji keycap sequence is a digit (or `#` or `*`) followed by U+FE0F and U+20E3; U+FE0F is the emoji presentation selector, "used to request an emoji presentation for an emoji character" - Unicode Technical Standard #51: Unicode Emoji, definitions ED-9 and ED-14c [https://www.unicode.org/reports/tr51/#def\_emoji\_keycap\_sequence](https://www.unicode.org/reports/tr51/#def_emoji_keycap_sequence)
2. Unicode's Mark category (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
3. An enclosing mark is a nonspacing mark with the General Category Enclosing Mark (Me), a subclass that surrounds the base character - Unicode Glossary: Enclosing Mark [https://www.unicode.org/glossary/#enclosing\_mark](https://www.unicode.org/glossary/#enclosing_mark)
4. Enclosing marks have the Grapheme\_Cluster\_Break value Extend, and the rule for that value begins "Do not break before extending characters", so an enclosing mark stays in the same grapheme cluster as its base - Unicode Standard Annex #29: Unicode Text Segmentation [https://www.unicode.org/reports/tr29/#Grapheme\_Cluster\_Boundaries](https://www.unicode.org/reports/tr29/#Grapheme_Cluster_Boundaries)
