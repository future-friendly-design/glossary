---
term: Enclosing mark
slug: enclosing-mark
aliases: []
tags: [characters-encoding]
level: advanced
depth: core
summary: "An enclosing mark is a combining character that surrounds the base character it attaches to, such as an enclosing circle or square."
related: [combining-mark, mark, spacing-combining-mark, grapheme-cluster]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Enclosing Mark (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#enclosing_mark
    type: authority
license: CC-BY-4.0
---

# Enclosing mark

## Definition
An enclosing mark is a combining character that surrounds the base character it attaches to, such as an enclosing circle or square.

## Why it matters
The enclosing mark is the third and last member of Unicode's Mark category, alongside the nonspacing [combining mark](combining-mark.md) and the [spacing combining mark](spacing-combining-mark.md). General Category Me, it is a kind of nonspacing mark that wraps around its base rather than sitting above or beside it, producing things like a digit inside a circle. For software the same rule applies as for other combining marks: the base and the enclosing mark together are a single [grapheme cluster](grapheme-cluster.md), so cursor movement, selection, and counting should treat them as one unit, not two.

## Example
A keycap or "circled" character, where a circle or square encloses the letter or digit inside it, is produced with an enclosing mark over a base character.

## Related terms
[Combining mark](combining-mark.md) · [Mark](mark.md) · [Spacing combining mark](spacing-combining-mark.md) · [Grapheme cluster](grapheme-cluster.md)

## Further reading
- Foundations: [Enclosing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#enclosing_mark)
