---
term: Enclosing mark
slug: enclosing-mark
aliases: []
level: advanced
depth: core
summary: >-
  An enclosing mark is a combining character that surrounds the base character
  it attaches to, such as an enclosing circle or square.
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

An enclosing mark is a combining [character](../../terms/character.md) that surrounds the base character it attaches to, such as an enclosing circle or square.

For example, the keycap `1️⃣` is the digit `1` plus an enclosing mark that draws the box around it.

### Why it matters in design systems

The enclosing mark is the third and last member of [Unicode](../../terms/unicode.md)'s Mark category, alongside the nonspacing [combining mark](combining-mark.md) and the [spacing combining mark](spacing-combining-mark.md). General Category Me, it is a kind of nonspacing mark that wraps around its base rather than sitting above or beside it, producing things like a digit inside a circle.<sup>1</sup> For software the same rule applies as for other combining marks: the base and the enclosing mark together are a single [grapheme cluster](../../terms/grapheme-cluster.md), so cursor movement, selection, and counting should treat them as one unit, not two.

***

### Related terms and mentions

[Character](../../terms/character.md) · [Combining mark](combining-mark.md) · [Grapheme cluster](../../terms/grapheme-cluster.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Spacing combining mark](spacing-combining-mark.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Enclosing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#enclosing_mark)

### Sources

1. An enclosing mark is a nonspacing mark with the General Category Enclosing Mark (Me), a subclass that surrounds the base character - Unicode Glossary: Enclosing Mark [https://www.unicode.org/glossary/#enclosing\_mark](https://www.unicode.org/glossary/#enclosing_mark)
