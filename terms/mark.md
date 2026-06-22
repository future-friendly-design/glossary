---
term: Mark
slug: mark
aliases: []
tags: [characters-encoding]
level: intermediate
depth: deep
summary: "Mark is an umbrella term for a sign added to or around a base character; in Unicode it is also a top-level character category split into nonspacing, spacing combining, and enclosing marks."
related: [combining-mark, spacing-combining-mark, enclosing-mark, diacritic, nukta, harakat, punctuation-mark]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Standard Annex #44: General Category Values"
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
  - title: "Combining Character (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#combining_character
    type: authority
license: CC-BY-4.0
---

# Mark

## Definition
Mark is an umbrella term for a sign added to or around a base character; in Unicode it is also a top-level character category split into nonspacing, spacing combining, and enclosing marks.

## Why it matters
"Mark" is one of the most overloaded words in typography and text encoding. It gets used in at least four different senses depending on who is talking, so the same word might mean a typographic accent, a Unicode category, a script feature, or a comma, and reaching for it without context invites confusion. This page sorts those senses out and links each to its own entry. The thread that ties the technical senses together is Unicode, which makes "Mark" a top-level General Category (abbreviated M) for characters that combine with a base, split three ways: nonspacing (Mn), spacing combining (Mc), and enclosing (Me).

## The four senses of "mark"
- **Diacritical sense:** a [diacritic](diacritic.md), an accent or similar sign that modifies a letter (the acute in "é", the tilde in "ñ"). This is the visual/typographic sense.
- **Combining / encoding sense:** in Unicode, a character that attaches to the preceding base. This is the General Category M, covered by [combining mark](combining-mark.md) (the nonspacing case), [spacing combining mark](spacing-combining-mark.md), and [enclosing mark](enclosing-mark.md).
- **Script-structural sense:** marks that are part of how a particular script writes, such as the Arabic vowel marks ([harakat](harakat.md)) or the Indic dot ([nukta](nukta.md)) that changes a consonant's value.
- **Punctuation sense:** a [punctuation mark](punctuation-mark.md) such as a comma or question mark, a separate idea that happens to share the word.

## In Unicode
The General Category M groups the combining marks and divides them by how they occupy space. A nonspacing mark (Mn) adds no width and renders on top of its base. A spacing combining mark (Mc) takes its own advance width while still belonging to the base character, common in Indic scripts. An enclosing mark (Me) surrounds its base, like an enclosing circle. These categories drive text segmentation, normalization, and rendering, so software that processes text by category has to handle all three.

## Related terms
[Combining mark](combining-mark.md) · [Spacing combining mark](spacing-combining-mark.md) · [Enclosing mark](enclosing-mark.md) · [Diacritic](diacritic.md) · [Nukta](nukta.md) · [Harakat](harakat.md) · [Punctuation mark](punctuation-mark.md)

## Further reading
- Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
- Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)
