---
term: Tamil script
slug: tamil-script
aliases:
  - tamil
level: intermediate
depth: core
summary: The Tamil script is used to write the Tamil language and minority languages such as Badaga, in India, Sri Lanka, Singapore, and Malaysia.
related:
  - abugida
  - brahmic-scripts
  - devanagari
  - matra
  - reordering
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Tamil Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/tamil
    type: code
  - title: Noto Sans Tamil (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Tamil
    type: design-tool
  - title: 'Unicode Tamil code chart (U+0B80)'
    url: https://www.unicode.org/charts/PDF/U0B80.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Tamil script

## Definition

The Tamil [script](../language-terms/writing-systems-and-scripts/script.md) is used to write the Tamil language and minority languages such as Badaga, in India, Sri Lanka, Singapore, and Malaysia.<sup>1</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md) in the [Brahmic](brahmic-scripts.md) family: each consonant carries an inherent vowel, which a visible dot called the pulli (the [virama](../language-terms/writing-systems-and-scripts/virama.md)) cancels where a consonant has no vowel.<sup>2</sup>

For example, தமிழ் ("Tamil") ends in ழ் carrying that pulli dot, showing the final consonant has no vowel, the way the script marks a bare consonant throughout.

{% hint style="info" %}
This glossary doesn't cover every Tamil script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Tamil script profile

These properties of the Tamil script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Tamil script |
| --- | --- |
| [Autonym](autonym.md) | தமிழ் அரிச்சுவடி |
| Languages | Tamil, Badaga, and others |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | dependent vowels ([matra](../language-terms/writing-systems-and-scripts/matra.md), some written to the left of the consonant) and the pulli, the visible [virama](../language-terms/writing-systems-and-scripts/virama.md) that cancels the inherent vowel |
| Numerals | common ASCII digits; traditional Tamil digits ௦ to ௯ and number symbols exist but are largely archaic |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | consonants carrying an inherent vowel, plus independent vowels |

### Tamil script rules and digital use considerations

If your design system supports languages that use the Tamil script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Tamil script | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | The reordering, the split vowel marks, and the pulli placement are shaping requirements carried by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), so a tool or font that cannot shape renders the vowels in the wrong place and the text incorrectly, not just unstyled;<sup>3</sup> you need a [typeface](typeface.md) and [font](font.md) with Tamil coverage before any of it will render |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right<sup>4</sup> | Left-aligned text as the default |
| [Baseline](../design-terms/typography/baseline.md) | symbols sit on the alphabetic baseline, like Latin, not hanging from a headstroke ([shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md)) as in Devanagari<sup>5</sup> | Tamil aligns to the same baseline as Latin, so a line that mixes Tamil and Latin shares one baseline |
| [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) | a left-side vowel mark is typed after its consonant but displays before it, and a two-part vowel mark is split to sit on both sides, so the renderer reorders and splits them<sup>6</sup> | A tool or font that cannot reorder or split places the vowel wrongly, so test a left-side vowel and a two-part vowel; loose [letter spacing](letter-spacing.md) can also pull a vowel mark or the pulli away from its consonant |
| [Conjuncts](../language-terms/writing-systems-and-scripts/conjunct.md) | Tamil forms very few conjuncts, writing most consonant clusters with a visible pulli instead<sup>7</sup> | A cluster that Devanagari would fuse stays as separate letters marked with the pulli, so do not expect heavy conjunct behaviour |
| [Unicode](unicode.md) block | Tamil, [U+0B80 to U+0BFF](https://www.unicode.org/charts/PDF/U0B80.pdf) (plus Tamil Supplement) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block |

### In practice

* **Cover the script before you commit a typeface:** confirm the font reorders the left-side vowel marks, splits the two-part vowels, and places the pulli, not just the base consonants. [Noto Sans Tamil](https://fonts.google.com/noto/specimen/Noto+Sans+Tamil) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a syllable with a left-side vowel mark and one with a two-part vowel and confirm they reorder and split; type தமிழ் and confirm the pulli shows on the final letter. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** the Tamil script serves more than one language, and they can differ in which symbols they use and how. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Baseline](../design-terms/typography/baseline.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Language](../language-terms/linguistics/language.md) · [Letter spacing](letter-spacing.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Tamil Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/tamil)
* Design tools: [Noto Sans Tamil (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Tamil)
* Foundations: [Unicode Tamil code chart (U+0B80)](https://www.unicode.org/charts/PDF/U0B80.pdf)

### Sources

1. The Tamil script is used to write the Tamil language of the southern Indian state of Tamil Nadu, minority languages such as Badaga, and is also used in Sri Lanka, Singapore, and parts of Malaysia - Developing OpenType Fonts for Tamil Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/tamil](https://learn.microsoft.com/en-us/typography/script-development/tamil)
2. Tamil is an abugida in which each consonant letter represents a syllable with an inherent vowel; the sign that suppresses that inherent vowel is called the pulli in Tamil - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
3. A font's OpenType rules select and position the correct Tamil forms, which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Tamil Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/tamil](https://learn.microsoft.com/en-us/typography/script-development/tamil)
4. Tamil, in common with the other scripts of the Indic family, is written from left to right - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
5. Tamil uses the so-called alphabetic baseline, which is the same as for Latin and many other scripts - Tamil (r12a script notes) [https://r12a.github.io/scripts/taml/ta.html](https://r12a.github.io/scripts/taml/ta.html)
6. The Tamil shaping engine reorders a pre-base (left-side) vowel mark before its base consonant and decomposes a two-part (split) matra into pieces placed on both sides of the base - Developing OpenType Fonts for Tamil Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/tamil](https://learn.microsoft.com/en-us/typography/script-development/tamil)
7. The Tamil script has fewer consonants than other Indic scripts and has only one consonant conjunct - Developing OpenType Fonts for Tamil Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/tamil](https://learn.microsoft.com/en-us/typography/script-development/tamil)
</content>
