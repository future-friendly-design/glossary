---
term: Ethiopic
slug: ethiopic-script
aliases:
  - ethiopic
  - ethiopic script
  - geez
  - fidel
level: intermediate
depth: core
summary: >-
  Ethiopic is a script used to write Amharic, Tigrinya, Tigre, and other
  languages of Ethiopia and Eritrea, including the classical language Ge'ez.
related:
  - abugida
  - syllabary
  - font-coverage
  - complex-text-layout
  - segmentation
status: voice-passed
version_added: 0.1
updated: 2026-07-06T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Ethiopic Layout Requirements (W3C)
    url: https://www.w3.org/TR/elreq/
    type: code
  - title: Noto Sans Ethiopic (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Ethiopic
    type: design-tool
  - title: Unicode Ethiopic code chart (U+1200)
    url: https://www.unicode.org/charts/PDF/U1200.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Ethiopic script

## Definition

Ethiopic is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Amharic, Tigrinya, Tigre, and other languages of Ethiopia and Eritrea, including the classical language Ge'ez.<sup>1</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md) in which each consonant-and-vowel syllable is a single character whose shape is modified to show the vowel, so one consonant has a series of related forms, one per vowel.<sup>2</sup>

For example, ሰላም ("selam", "peace", a common greeting) is written with three of those syllable characters.

{% hint style="info" %}
This glossary doesn't cover every Ethiopic property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Ethiopic profile

These properties of Ethiopic apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property                                                           | Ethiopic                                                                                                     |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| [Autonym](autonym.md)                                              | ግዕዝ                                                                                                          |
| Languages                                                          | Amharic, Tigrinya, Tigre, Oromo, Ge'ez, and others                                                           |
| Letter case                                                        | None (no uppercase and lowercase)                                                                            |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md)     | No separate vowel or tone marks; the vowel is built into the letterform rather than added as a separate mark |
| Numerals                                                           | Ethiopic numerals ፩, ፪, ፫ … (a traditional system; European digits also common)                              |
| Script type                                                        | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md)                                          |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Consonant-and-vowel syllables, each a single character; one consonant has a form for each vowel              |

### Ethiopic rules and digital use considerations

If your design system supports languages that use Ethiopic, here are some considerations to keep in mind:

| Rule or feature                                                                               | How it works in Ethiopic                                                                                                                                        | Design systems                                                                                                                                                                                                                                                                                     |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complex text layout](complex-text-layout.md)                                                 | Not required                                                                                                                                                    | The structure to plan for is the syllable set: covering Ethiopic means supporting a large character set, hundreds of characters rather than a few dozen letters plus marks, and typing it means composing or selecting whole syllables; without the full set the text is simply missing characters |
| Syllable characters                                                                           | each consonant-and-vowel is one character; the vowel is shown by modifying the consonant's shape, so one consonant has a series of forms<sup>3</sup>            | Plan input and search around syllables, not letters; do not assume letter-by-letter input or vowels that detach from the consonant                                                                                                                                                                 |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md)             | Left to right<sup>4</sup>                                                                                                                                       | Left-aligned text as the default                                                                                                                                                                                                                                                                   |
| [Unicode](unicode.md) block                                                                   | Ethiopic, [U+1200 to U+137F](https://www.unicode.org/charts/PDF/U1200.pdf) (plus Ethiopic Supplement and the Ethiopic Extended blocks)                          | Ensure [font coverage](font-coverage.md) of the block and its extensions; the large syllable set means a partial subset drops real syllables                                                                                                                                                       |
| [Word separation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) | traditionally a wordspace mark separated words;<sup>5</sup> modern Amharic generally uses spaces, so segmentation depends on the text's conventions<sup>6</sup> | Let [segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) follow the text's convention rather than one fixed rule, and pull it from [locale](locale.md) data; search and line breaking depend on it                                                           |

### In practice

* **Cover the whole syllable set, not a subset:** because each consonant-and-vowel is its own character, Ethiopic runs to hundreds of characters, and a font that stops at a partial set drops real syllables. Confirm coverage for the languages you support. [Noto Sans Ethiopic](https://fonts.google.com/noto/specimen/Noto+Sans+Ethiopic) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Plan input and search around syllables, not letters:** text is composed of syllable characters, and word boundaries may use a wordspace mark or spaces, so do not assume letter-by-letter input or space-delimited words. Let [segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) follow the text's convention, and pull it from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **Decide numerals per locale:** Ethiopic has its own numeral system as well as European digits, so choose which to show based on the language and context rather than defaulting to one.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Character](character.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Ethiopic Layout Requirements (W3C)](https://www.w3.org/TR/elreq/)
* Design tools: [Noto Sans Ethiopic (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Ethiopic)
* Foundations: [Unicode Ethiopic code chart (U+1200)](https://www.unicode.org/charts/PDF/U1200.pdf)

### Sources

1. The Ethiopic script is widely used for writing the Semitic languages of Ethiopia and Eritrea, such as Amharic, Tigrinya, and Tigre, and it originally evolved for the classical language Ge'ez - Ethiopic (r12a script notes) [https://r12a.github.io/scripts/ethi/am.html](https://r12a.github.io/scripts/ethi/am.html)
2. The syllables of the Ethiopic script are traditionally presented as a two-dimensional matrix of consonant-vowel combinations, with 43 consonants each crossed with 8 vowels, making 344 conceptual syllables - The Unicode Standard, Version 17.0, Chapter 19: Africa [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-19/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-19/)
3. Each Ethiopic syllable is a single character whose base consonant shape is given small changes to indicate the following vowel, so each consonant has a full series of vowel forms - Ethiopic (r12a script notes) [https://r12a.github.io/scripts/ethi/am.html](https://r12a.github.io/scripts/ethi/am.html)
4. Ethiopic text runs left to right in horizontal lines - Ethiopic (r12a script notes) [https://r12a.github.io/scripts/ethi/am.html](https://r12a.github.io/scripts/ethi/am.html)
5. The traditional word separator in the Ethiopic script is U+1361 ETHIOPIC WORDSPACE - The Unicode Standard, Version 17.0, Chapter 19: Africa [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-19/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-19/)
6. Modern Amharic generally uses spaces to separate words, though the Ethiopic wordspace is still sometimes used - Ethiopic (r12a script notes) [https://r12a.github.io/scripts/ethi/am.html](https://r12a.github.io/scripts/ethi/am.html)
