---
term: Devanagari script
slug: devanagari
aliases:
  - Nagari
level: intermediate
depth: core
summary: >-
  Devanagari is a script used to write Hindi, Marathi, Sanskrit, Nepali, and
  many other South Asian languages.
related:
  - abugida
  - brahmic-scripts
  - bengali-assamese
  - matra
  - shirorekha
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-07-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: code
  - title: Noto Sans Devanagari (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari
    type: design-tool
  - title: Unicode Devanagari code chart (U+0900)
    url: https://www.unicode.org/charts/PDF/U0900.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Devanagari script

## Definition

Devanagari is a [script](script.md) used to write Hindi, Marathi, Sanskrit, Nepali, and many other South Asian languages.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](abugida.md): each consonant carries an inherent vowel that added marks can override.<sup>2</sup>

For example, हिन्दी ("Hindi") stacks two consonants into a conjunct (न्द) and reorders a left-side i-matra (ि) so it displays before its consonant, the way the script combines and reorders its marks throughout.

{% hint style="info" %}
This glossary doesn't cover every Devanagari property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Devanagari profile

These properties of Devanagari apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                             | Devanagari                                                                                                                            |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../linguistics/autonym.md) | देवनागरी                                                                                                                              |
| Languages                            | Hindi, Marathi, Sanskrit, Nepali, and many others                                                                                     |
| Letter case                          | None (no uppercase and lowercase)                                                                                                     |
| [Marks](mark.md)                     | Dependent vowels ([matra](matra.md)), the [virama](virama.md), the [nukta](nukta.md), and nasalization marks (anusvara, chandrabindu) |
| Numerals                             | Devanagari digits ० to ९ (alongside common ASCII digits)                                                                              |
| Script type                          | [Abugida](abugida.md)                                                                                                                 |
| [Symbols](symbol.md)                 | Consonants carrying an inherent vowel, plus independent vowels                                                                        |

### Devanagari rules and digital use considerations

If your design system supports languages that use Devanagari, here are some considerations to keep in mind:

| Rule or feature                                                                                             | How it works in Devanagari                                                                                                                                                                                                                                                                                                             | Design systems                                                                                                                                                                                                                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md)                                                                 | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it                                                                                                                                                                          | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>3</sup>                                                                                                                                                           |
| [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) | Yes, shaping required                                                                                                                                                                                                                                                                                                                  | Handled by the font's [OpenType](../../design-terms/typography/opentype.md) rules and applied at render time by the platform's [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md); see the OpenType and Text shaping rows below for what your font needs to support. Get it wrong and the text renders incorrectly, not just unstyled |
| [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) (open source)                 | [Noto Sans Devanagari](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari) is a free, open-source font from Google's [Noto](../../design-terms/typography/noto-fonts.md) project, covering the script's characters and the OpenType features they need (see OpenType and Text shaping)                                        | Treat the typeface as a foundational choice, and confirm it covers every language you support that uses the script (see [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md)), not just one                                                                                                                                           |
| [Hanging baseline](hanging-baseline.md)                                                                     | Symbols hang from the shirorekha rather than sitting on a bottom baseline<sup>4</sup>                                                                                                                                                                                                                                                  | Devanagari does not sit on a bottom baseline, so do not align it to one by eye                                                                                                                                                                                                                                                                                                   |
| [OpenType](../../design-terms/typography/opentype.md)                                                       | The font must include the specific [OpenType features](../../design-terms/typography/opentype-features.md) for conjunct and half-form composition, reordering of the pre-base (left-side) i-matra, nukta composition, and positioning of the dependent-vowel and other marks above and below the base, beyond plain glyph substitution | A font can cover the characters and still leave these features out, so confirm it actually ships them, not just the base glyphs<sup>5</sup>. See the Text shaping row below                                                                                                                                                                                                      |
| [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md)                   | A left-side i-matra (dependent vowel) is typed after its consonant but displays before it, so the renderer reorders it<sup>6</sup>                                                                                                                                                                                                     | A tool or font that cannot reorder places the vowel in the wrong position, so test a word with a left-side [matra](matra.md)                                                                                                                                                                                                                                                     |
| [Shirorekha](shirorekha.md)                                                                                 | A headline stroke runs along the top of the symbols, joining them across a word<sup>7</sup>                                                                                                                                                                                                                                            | The headline has to join cleanly across a word, so you cannot add [letter spacing](../../design-terms/typography/letter-spacing.md) that breaks it                                                                                                                                                                                                                               |
| [Stacking](stacking-script.md)                                                                              | Consonant clusters combine into [conjunct](conjunct.md) forms<sup>8</sup>                                                                                                                                                                                                                                                              | Confirm the font forms conjunct glyphs; if a full conjunct is unavailable the documented fallback is half-form glyphs, not the cluster shown as separate symbols<sup>9</sup>                                                                                                                                                                                                     |
| [Text direction](text-direction.md)                                                                         | [Left to right](left-to-right.md)<sup>10</sup>                                                                                                                                                                                                                                                                                         | Left-aligned text as the default                                                                                                                                                                                                                                                                                                                                                 |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)               | Shaping happens at render time: the platform's [shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) reads the font's OpenType features (see OpenType above) and reorders the i-matra, forms the conjuncts, and positions the marks for correct display                                    | A correct font is necessary but not sufficient: a tool or pipeline that places glyphs without shaping renders the script wrong even with a fully-featured font. Test in the actual design tools your team uses, not just the browser                                                                                                                                             |
| [Unicode](../../programming-terms/text-in-software/unicode.md) block                                        | Devanagari, [U+0900 to U+097F](https://www.unicode.org/charts/PDF/U0900.pdf) (plus Devanagari Extended)                                                                                                                                                                                                                                | No special handling beyond ensuring [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) of the block, including the conjunct and matra forms                                                                                                                                                                                         |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Devanagari glyphs AND the [shaping rules](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) that position them, not just the base symbols. See [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word with a conjunct and a left-side matra and confirm they form and reorder; tool support for [complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share Devanagari and still differ in which symbols they use and how. Do not hardcode one language's choices; pull them from [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) data. Unicode's [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](abugida.md) · [Autonym](../linguistics/autonym.md) · [Baseline](../../design-terms/typography/baseline.md) · [Bengali-Assamese script](bengali-assamese.md) · [Bidirectional text](bidirectional-text.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) · [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) · [Conjunct](conjunct.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Hanging baseline](hanging-baseline.md) · [Language](../linguistics/language.md) · [Left-to-right](left-to-right.md) · [Letter spacing](../../design-terms/typography/letter-spacing.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Mark](mark.md) · [Matra](matra.md) · [Noto fonts](../../design-terms/typography/noto-fonts.md) · [Nukta](nukta.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../design-terms/typography/typeface.md) · [Unicode](../../programming-terms/text-in-software/unicode.md) · [Virama](virama.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
* Design tools: [Noto Sans Devanagari (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari)
* Foundations: [Unicode Devanagari code chart (U+0900)](https://www.unicode.org/charts/PDF/U0900.pdf)

### Sources

1. Devanagari is written left to right and used for Sanskrit, Hindi, Marathi, Nepali, and many other languages - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
2. Devanagari and the other Indic scripts are abugidas, a cross between syllabic and alphabetic writing systems, in which each consonant carries an inherent vowel - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. Devanagari has a so-called 'hanging' baseline - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
5. A font's OpenType rules select and position the correct Devanagari forms (conjuncts, matra reordering, mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
6. Indic-script rendering must reorder elements from the logical (character) store to the visual (glyph) order, which is why a left-side matra stored after its consonant displays before it - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
7. Glyphs 'hang' from a top bar (shiroreka) that runs across a word, and which can sometimes be treated as a baseline - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
8. A consonant cluster is normally depicted with a conjunct glyph when the font provides one - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
9. If the coded character sequence would normally render with a full conjunct, but such a conjunct is not available, the fallback rendering is to use half-forms - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
10. Devanagari text runs left to right in horizontal lines - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
