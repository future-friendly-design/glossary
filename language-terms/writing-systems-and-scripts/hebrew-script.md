---
term: Hebrew script
slug: hebrew-script
aliases:
  - hebrew
  - hebrew alphabet
level: intermediate
depth: core
summary: >-
  The Hebrew script is used to write Hebrew, Yiddish, Ladino, and other Jewish
  languages.
related:
  - abjad
  - arabic-script
  - right-to-left
  - bidirectional-text
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Hebrew Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/hebrew
    type: code
  - title: Noto Sans Hebrew (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Hebrew
    type: design-tool
  - title: Unicode Hebrew code chart (U+0590)
    url: https://www.unicode.org/charts/PDF/U0590.pdf
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Hebrew script

## Definition

The Hebrew [script](script.md) is used to write Hebrew, Yiddish, Ladino, and other Jewish languages.<sup>1</sup> It is an [abjad](abjad.md): vowels are normally left unwritten, though they can be shown with optional points added to the consonants.<sup>2</sup>

For example, the greeting שלום ("shalom", "hello") is written right to left, ending in ם, the form the letter mem takes at the end of a word.

{% hint style="info" %}
This glossary doesn't cover every Hebrew script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Hebrew script profile

These properties of the Hebrew script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Hebrew script                                                                                                                   |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../../terms/autonym.md) | אלף־בית עברי                                                                                                                    |
| Languages                         | Hebrew, Yiddish, Ladino (Judezmo), and others                                                                                   |
| Letter case                       | None (no uppercase and lowercase)                                                                                               |
| [Marks](mark.md)                  | Vowel points (niqqud), the dagesh, and cantillation marks, positioned above, below, or within the consonants as combining marks, e.g. שלום shown with niqqud as שָׁלוֹם |
| Numerals                          | Common ASCII digits, written left to right; a traditional additive system using Hebrew letters is also used                     |
| Script type                       | [Abjad](abjad.md)                                                                                                               |
| [Symbols](symbol.md)              | Consonants, five of which take a distinct word-final form (see Marks for how vowels can be shown)                               |

### Hebrew script rules and digital use considerations

If your design system supports languages that use the Hebrew script, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in the Hebrew script                                                                                                             | Design systems                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complex text layout](../../terms/complex-text-layout.md) | Yes, shaping required                                                                                                                         | Unlike the [Arabic script](arabic-script.md), Hebrew letters do not join, so a letter keeps its shape wherever it sits and spacing is less constrained than in a cursive script;<sup>3</sup> even so, the right-to-left and bidirectional order, the final forms, and any vowel-point (niqqud) placement are carried by the font's [OpenType](../../terms/opentype.md) rules and applied at render time by the platform's [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), so getting the direction or final forms wrong makes the text read incorrectly, not just unstyled<sup>4</sup> |
| Dagesh                                                     | A dot placed inside a letter; it is not a vowel, it is a [mark](mark.md) that changes how the consonant is pronounced (in ב, כ, and פ it switches the sound; in most other letters it marks a doubled consonant)<sup>5</sup> | Optional and often omitted, like niqqud: the same word may render with or without it, so treat both forms as the same word in search and matching, the same issue [harakat](harakat.md) creates for [Arabic](arabic-script.md) |
| Final letterforms                                         | Five consonants (final kaf, mem, nun, pe, and tsadi) take a distinct form at the end of a word<sup>6</sup>                                    | These are separate encoded characters, so confirm the font renders them and test a word that ends in a final-form letter                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Niqqud (vowel points)                                     | Optional vowel [marks](mark.md), positioned above, below, or within the consonants and normally omitted outside liturgical and learning texts | When points are shown they are combining marks that have to stay correctly positioned on their consonants, handled by the OpenType mark feature, so test point placement, not just the base consonants<sup>7</sup>. Cantillation marks follow the same combining-mark mechanics but are liturgical-only, used for chanting biblical text;<sup>8</sup> most products never need them, but test them too if you support religious-text use cases                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [Text direction](text-direction.md)                       | [Right to left](right-to-left.md)<sup>9</sup>                                                                                                     | The whole layout mirrors, not just the text: icons, alignment, and spacing should use logical CSS properties (start/end) instead of physical left/right, so the same component works in both directions<sup>10</sup>. A number or an embedded Latin word that shares a line is [bidirectional](bidirectional-text.md) and has to be reordered by the Unicode bidirectional algorithm to read correctly<sup>11</sup>                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| [Unicode](../../terms/unicode.md) block                   | Hebrew, [U+0590 to U+05FF](https://www.unicode.org/charts/PDF/U0590.pdf)                                                                      | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block, including the final forms and vowel points                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Hebrew glyphs AND the [shaping rules](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) (the five final forms, and vowel-point placement if you show points), not just the base consonants. [Noto Sans Hebrew](https://fonts.google.com/noto/specimen/Noto+Sans+Hebrew) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word that ends in a final-form letter, such as שלום, and confirm the final form renders; then test a line that mixes a Hebrew phrase with a Latin name or a number and confirm the [bidirectional](bidirectional-text.md) order holds. Tool support for [complex text layout](../../terms/complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** Hebrew, Yiddish, and Ladino all use the Hebrew script and still differ in how they use it, down to how each handles vowels. Do not hardcode one language's choices; pull them from [locale](../../terms/locale.md) data. Unicode's [CLDR](../../terms/cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abjad](abjad.md) · [Arabic script](arabic-script.md) · [Autonym](../../terms/autonym.md) · [Bidirectional text](bidirectional-text.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Harakat](harakat.md) · [Language](../linguistics/language.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Right-to-left](right-to-left.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Hebrew Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/hebrew)
* Design tools: [Noto Sans Hebrew (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Hebrew)
* Foundations: [Unicode Hebrew code chart (U+0590)](https://www.unicode.org/charts/PDF/U0590.pdf)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The Hebrew script is used for writing the Hebrew language as well as Yiddish, Judezmo (Ladino), and a number of other languages - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
2. In Hebrew, vowels and other marks are written as points applied to the consonantal base letters, and these marks are usually omitted except in liturgical texts and other special applications - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
3. Arabic, Syriac, and Mandaic are cursive scripts even when typeset, unlike Hebrew and Samaritan, where the letters are unconnected - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
4. In this specification, font developers will learn how to encode complex script features in their fonts, choose character sets, organize font information, and use existing tools to produce Hebrew fonts - Developing OpenType Fonts for Hebrew Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/hebrew](https://learn.microsoft.com/en-us/typography/script-development/hebrew)
5. Dagesh is a dot that appears inside the letter it affects; it is not a vowel but a diacritic that affects the pronunciation of a consonant - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
6. Variant forms of five Hebrew letters are encoded as separate characters and are generally used in place of the nominal letterforms at the end of words - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
7. In Hebrew most diacritic marks (nikud) are optional and omitted in most text; when they occur they need to be correctly positioned relative to the base character, which the shaping engine handles with the OpenType mark (mark-to-base) feature - Developing OpenType Fonts for Hebrew Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/hebrew](https://learn.microsoft.com/en-us/typography/script-development/hebrew)
8. Cantillation marks are used in publishing liturgical texts, including the Bible - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
9. The Hebrew script is written from right to left - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
10. In right-to-left layouts, directional UI icons such as back and forward should be mirrored, while not all elements mirror (for example, charts can keep a left-to-right orientation) - Bidirectionality and RTL (Material Design 3) [https://m3.material.io/foundations/layout/bidirectionality-rtl](https://m3.material.io/foundations/layout/bidirectionality-rtl)
11. In addition to digits, embedded words from English and other scripts are also written from left to right, also producing bidirectional text - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
