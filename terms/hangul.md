---
term: Hangul
slug: hangul
aliases:
  - Hangeul
  - Korean alphabet
level: intermediate
depth: core
summary: Hangul is a script used to write Korean.
related:
  - featural-alphabet
  - alphabet
  - syllabary
  - cjk
  - normalization
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Korean Hangul Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/hangul
    type: code
  - title: Noto Sans Korean (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+KR
    type: design-tool
  - title: 'Unicode Hangul Syllables code chart (U+AC00)'
    url: https://www.unicode.org/charts/PDF/UAC00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Hangul

## Definition

Hangul is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Korean.<sup>1</sup> It is a [featural script](../language-terms/writing-systems-and-scripts/featural-alphabet.md): the Unicode Standard calls Hangul a featural syllabic script, its syllables formed from a set of alphabetic letters (jamo) in a regular way and grouped into square blocks.<sup>2</sup> What makes it featural, beyond that block grouping, is that the jamo shapes themselves are patterned on the sounds they represent, so related sounds share related shapes, rather than each letter being an arbitrary form. Hangul was developed under King Sejong, completed in 1443 and promulgated in the Hunminjeongeum in 1446.<sup>3</sup>

For example, 한글 ("Hangul") is two syllable blocks, 한 (han) and 글 (geul), each one built from letters stacked into a square rather than written in a line.

{% hint style="info" %}
This glossary doesn't cover every Hangul property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Hangul profile

These properties of Hangul apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Hangul |
| --- | --- |
| [Autonym](autonym.md) | 한글 |
| Languages | Korean |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | None (Hangul has no combining vowel or tone marks; the jamo themselves compose the syllable) |
| Numerals | common ASCII digits (Korean also has native and Sino-Korean number words) |
| Script type | [Featural script](../language-terms/writing-systems-and-scripts/featural-alphabet.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | letters (jamo: an initial consonant, a vowel, and an optional final consonant) grouped into syllable blocks |

### Hangul rules and digital use considerations

If your design system supports languages that use Hangul, here are some considerations to keep in mind:

| Rule or feature | How it works in Hangul | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required for precomposed Modern Hangul; Yes, shaping required to compose conjoining jamo (Old Hangul) into blocks<sup>4</sup> | Hangul's letters are not laid out one after another but composed into square syllable blocks; the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) composes conjoining jamo into blocks at render time, so the composition, not styling, is what has to be right, or the text renders incorrectly |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right; traditionally it could also be set in vertical columns<sup>5</sup> | Left-aligned text as the default; support vertical layout only if your text calls for it |
| Syllable blocks | letters (jamo: an initial consonant, a vowel, and an optional final consonant) are composed into square syllable blocks<sup>6</sup> | The syllable block, not the single letter, is the unit that has to sit consistently in its square; a font has to fit those components into a consistent square, which is a different problem from placing letters in a row |
| [Normalization](normalization.md) | Unicode stores modern text either as precomposed blocks or as conjoining jamo, so the same syllable can be represented either way<sup>7</sup> | Comparing or searching Korean text needs normalization to remove the alternate representations and treat the two forms as equal,<sup>8</sup> or identical-looking text will fail to compare equal |
| [Unicode](unicode.md) block | Hangul Syllables, [U+AC00 to U+D7A3](https://www.unicode.org/charts/PDF/UAC00.pdf) (plus Hangul Jamo and Hangul Compatibility Jamo) | No special handling beyond ensuring [font coverage](font-coverage.md) of the blocks your data uses, including conjoining jamo if present |

### In practice

* **Cover the script before you commit a typeface:** confirm the font renders the syllable blocks cleanly (and composes conjoining jamo, if your data uses them), not just isolated letters. [Noto Sans Korean](https://fonts.google.com/noto/specimen/Noto+Sans+KR) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with real text, not a letter grid:** set real Korean and confirm the blocks compose and sit evenly; if any of your data is stored as conjoining jamo, confirm it composes into blocks rather than showing a run of half-width letters. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Normalize before you compare, search, or de-duplicate:** the same Korean word can be stored as precomposed syllables or as separate jamo, so apply [normalization](normalization.md) (composing to blocks) before matching, or identical-looking text will fail to compare equal. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Featural script](../language-terms/writing-systems-and-scripts/featural-alphabet.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Normalization](normalization.md) · [Noto fonts](noto-fonts.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Unicode Standard](unicode-standard.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Korean Hangul Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/hangul)
* Design tools: [Noto Sans Korean (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+KR)
* Foundations: [Unicode Hangul Syllables code chart (U+AC00)](https://www.unicode.org/charts/PDF/UAC00.pdf)

### Sources

1. The Koreans developed an alphabetic system, Hangul, to write the Korean language - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
2. Korean Hangul may be considered a featural syllabic script, and as opposed to many other syllabic scripts its syllables are formed from a set of alphabetic components in a regular fashion - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
3. The Hunminjeongeum manuscript, published in 1446, contains King Sejong's promulgation of the Korean alphabet now called Hangul, the development of which he completed in 1443 - UNESCO Memory of the World: Hunminjeongum Manuscript [https://www.unesco.org/en/memory-world/hunminjeongum-manuscript](https://www.unesco.org/en/memory-world/hunminjeongum-manuscript)
4. It is important to note that if any of the Jamo sequences being analyzed is capable of forming a Modern Hangul Syllable, the shaping engine does not apply OpenType features to shape them - Developing OpenType Fonts for Korean Hangul Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/hangul](https://learn.microsoft.com/en-us/typography/script-development/hangul)
5. East Asian scripts, including Hangul, were traditionally written in vertical lines running top to bottom and arranged from right to left across the page, but a horizontal left-to-right layout has become common - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
6. In Hangul the syllables are formed from a set of alphabetic components (jamo) in a regular fashion and grouped into square blocks - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
7. The Unicode Standard contains both the complete set of precomposed modern Hangul syllable blocks and a set of conjoining Hangul jamo, so the same syllable can be represented either way - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
8. Normalization removes alternate representations of equivalent sequences from text so that the data can be binary-compared for equivalence - Unicode Glossary: Normalization [https://www.unicode.org/glossary/#normalization](https://www.unicode.org/glossary/#normalization)
</content>
