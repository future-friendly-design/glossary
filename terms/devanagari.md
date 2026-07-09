---
term: Devanagari
slug: devanagari
aliases:
  - Nagari
level: intermediate
depth: core
summary: Devanagari is a script used to write Hindi, Marathi, Sanskrit, Nepali, and many other South Asian languages.
related:
  - abugida
  - brahmic-scripts
  - bengali-assamese
  - matra
  - shirorekha
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: code
  - title: Noto Sans Devanagari (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari
    type: design-tool
  - title: 'Unicode Devanagari code chart (U+0900)'
    url: https://www.unicode.org/charts/PDF/U0900.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Devanagari

## Definition

Devanagari is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Hindi, Marathi, Sanskrit, Nepali, and many other South Asian languages.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](../language-terms/writing-systems-and-scripts/abugida.md): each consonant carries an inherent vowel that added marks can override.<sup>2</sup>

For example, हिन्दी ("Hindi") stacks two consonants into a conjunct (न्द) and reorders a left-side i-matra (ि) so it displays before its consonant, the way the script combines and reorders its marks throughout.

{% hint style="info" %}
This glossary doesn't cover every Devanagari property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Devanagari profile

These properties of Devanagari apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Devanagari |
| --- | --- |
| [Autonym](autonym.md) | देवनागरी |
| Languages | Hindi, Marathi, Sanskrit, Nepali, and many others |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Dependent vowels ([matra](../language-terms/writing-systems-and-scripts/matra.md)), the [virama](../language-terms/writing-systems-and-scripts/virama.md), the [nukta](../language-terms/writing-systems-and-scripts/nukta.md), and nasalization marks (anusvara, chandrabindu) |
| Numerals | Devanagari digits ० to ९ (alongside common ASCII digits) |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Consonants carrying an inherent vowel, plus independent vowels |

### Devanagari rules and digital use considerations

If your design system supports languages that use Devanagari, here are some considerations to keep in mind:

| Rule or feature | How it works in Devanagari | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | The reordering and conjuncts are shaping requirements carried by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), so a tool or font that cannot shape renders the text incorrectly, not just unstyled;<sup>3</sup> you need a [typeface](typeface.md) and [font](font.md) with Devanagari coverage before any of it will render |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right<sup>4</sup> | Left-aligned text as the default |
| [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) | a left-side i-matra (dependent vowel) is typed after its consonant but displays before it, so the renderer reorders it<sup>5</sup> | A tool or font that cannot reorder places the vowel in the wrong position, so test a word with a left-side [matra](../language-terms/writing-systems-and-scripts/matra.md) |
| [Stacking](../language-terms/writing-systems-and-scripts/stacking-script.md) | consonant clusters combine into [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) forms<sup>6</sup> | Confirm the font forms conjunct glyphs; if a full conjunct is unavailable the documented fallback is half-form glyphs, not the cluster shown as separate symbols<sup>7</sup> |
| [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) | a headline stroke runs along the top of the symbols, joining them across a word<sup>8</sup> | The headline has to join cleanly across a word, so you cannot add [letter spacing](letter-spacing.md) that breaks it |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | symbols hang from the shirorekha rather than sitting on a bottom baseline<sup>9</sup> | Devanagari does not sit on a Latin bottom baseline, so do not align it to one by eye |
| [Unicode](unicode.md) block | Devanagari, [U+0900 to U+097F](https://www.unicode.org/charts/PDF/U0900.pdf) (plus Devanagari Extended) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block, including the conjunct and matra forms |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Devanagari glyphs AND the shaping rules (conjuncts, matra reordering), not just the base symbols. [Noto Sans Devanagari](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word with a conjunct and a left-side matra and confirm they form and reorder; tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share Devanagari and still differ in which symbols they use and how. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Baseline](../design-terms/typography/baseline.md) · [Bengali-Assamese](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Language](../language-terms/linguistics/language.md) · [Letter spacing](letter-spacing.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [Nukta](../language-terms/writing-systems-and-scripts/nukta.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
* Design tools: [Noto Sans Devanagari (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari)
* Foundations: [Unicode Devanagari code chart (U+0900)](https://www.unicode.org/charts/PDF/U0900.pdf)

### Sources

1. Devanagari is written left to right and used for Sanskrit, Hindi, Marathi, Nepali, and many other languages - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
2. Devanagari and the other Indic scripts are abugidas, a cross between syllabic and alphabetic writing systems, in which each consonant carries an inherent vowel - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
3. A font's OpenType rules select and position the correct Devanagari forms (conjuncts, matra reordering, mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
4. Devanagari text runs left to right in horizontal lines - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
5. Indic-script rendering must reorder elements from the logical (character) store to the visual (glyph) order, which is why a left-side matra stored after its consonant displays before it - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
6. A consonant cluster is normally depicted with a conjunct glyph when the font provides one - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
7. If the coded character sequence would normally render with a full conjunct, but such a conjunct is not available, the fallback rendering is to use half-forms - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
8. Glyphs 'hang' from a top bar (shiroreka) that runs across a word, and which can sometimes be treated as a baseline - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
9. Devanagari has a so-called 'hanging' baseline - Devanagari (r12a script notes) [https://r12a.github.io/scripts/deva/hi.html](https://r12a.github.io/scripts/deva/hi.html)
</content>
</invoke>
