---
term: Arabic script
slug: arabic-script
aliases:
  - arabic
  - arabic alphabet
level: intermediate
depth: core
summary: >-
  The Arabic script is used to write Arabic, Persian, Urdu, and many other
  languages of the Middle East, South Asia, and Africa.
related:
  - abjad
  - hebrew-script
  - joining
  - harakat
  - bidirectional-text
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Arabic Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/arabic
    type: code
  - title: Noto Sans Arabic (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Arabic
    type: design-tool
  - title: Unicode Arabic code chart (U+0600)
    url: https://www.unicode.org/charts/PDF/U0600.pdf
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Arabic script

## Definition

The Arabic [script](script.md) is used to write Arabic, Persian, Urdu, and many other languages of the Middle East, South Asia, and Africa.<sup>1</sup> It is an [abjad](abjad.md): short vowels are normally left out for the reader to supply, though they can be shown with optional marks.<sup>2</sup>

For example, the greeting مرحبا ("marhaba", "hello") is written as a run of consonants, most of them joining into cursive forms the way the script does throughout.

{% hint style="info" %}
This glossary doesn't cover every Arabic script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Arabic script profile

These properties of the Arabic script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Arabic script                                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| [Autonym](../../terms/autonym.md) | الأبجدية العربية                                                                                                               |
| Languages                         | Arabic, Persian, Urdu, Pashto, Sindhi, Uyghur, and many others                                                                 |
| Letter case                       | None (no uppercase and lowercase)                                                                                              |
| [Marks](mark.md)                  | [harakat](harakat.md) (short-vowel marks) and other tashkil such as shadda and sukun, e.g. كتب ("ktb") shown with harakat as كَتَبَ |
| Numerals                          | Arabic-Indic digits ٠ to ٩ (Persian and Urdu use a separate Extended Arabic-Indic set ۰ to ۹), written left to right even though embedded in right-to-left running text (see Bidirectional text below); common ASCII digits also appear |
| Script type                       | [Abjad](abjad.md) for Arabic, where short vowels are omitted; the same script works as a full [alphabet](alphabet.md) for languages such as Kashmiri and Uyghur, where every vowel is written<sup>3</sup> |
| [Symbols](symbol.md)              | Consonants and long vowels, with short vowels normally unwritten                                                               |

### Arabic script rules and digital use considerations

If your design system supports languages that use the Arabic script, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in the Arabic script                                                                                                                 | Design systems                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md)                | Arabic text commonly shares a line with embedded Latin brand names, numbers, or URLs, which run left to right inside the right-to-left line       | Any embedded left-to-right word or number needs the Unicode bidirectional algorithm to reorder it correctly, or the line reads scrambled<sup>4</sup>. Isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text |
| [Complex text layout](../../terms/complex-text-layout.md) | Yes, shaping required                                                                                                                             | Handled by the font's [OpenType](../../terms/opentype.md) rules and applied at render time by the platform's [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md); see the OpenType and Text shaping rows below for what your font needs to support. Get it wrong and the text renders incorrectly, not just unstyled |
| [Harakat](harakat.md)                                     | Optional short-vowel [marks](mark.md) sit above and below the consonants and are normally omitted                                                 | When they are shown, they have to stay correctly positioned on their consonants, so test mark placement, not just the base letters. And because they are normally omitted, the same word may be typed or stored with or without them (كتب vs. كَتَبَ): treat both as the same word in search, autocomplete, and duplicate checks                                                                                              |
| [Joining](joining.md)                                     | Letters connect cursively, most taking an isolated, initial, medial, or final form depending on their position in the word<sup>5</sup>            | The join is structural, not decorative: you cannot add [letter spacing](../../terms/letter-spacing.md) that pulls the joined letters apart                                                                                                                                                                                                                                                                                       |
| [Ligature](../../terms/ligature.md) (lam-alef)            | The lam-alef combination (ل + ا) forms an obligatory ligature (لا), not two separate letters, where the font's style supports it<sup>6</sup>      | Confirm the font ships it; it is expected, not optional                                                                                                                                                                                                                                                                                                                                                                          |
| [OpenType](../../terms/opentype.md)                        | This script needs specific [OpenType features](../../terms/opentype-features.md) to render correctly, beyond plain glyph substitution                                                 | Font and rendering stack must support positional-form substitution for joining (see Joining), the lam-alef ligature (see Ligature), and mark positioning for harakat (see Harakat)<sup>7</sup>. Confirm all of these render together in real text, not just individually |
| [Text direction](text-direction.md)                       | [Right to left](right-to-left.md)<sup>8</sup>                                                                                                     | The base direction of the whole document or component is right to left, so the layout is mirrored: navigation, alignment, and spacing flip to the opposite side. Use logical CSS properties (start/end) instead of physical left/right, so one component serves both directions. Not everything flips, though: elements like charts and media-player controls keep their orientation<sup>9</sup>. See Bidirectional text above for embedded content that runs the other way |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) | The platform's [shaping engine](../../terms/shaping-engine.md) applies the font's OpenType rules to select positional forms, form the lam-alef ligature, and position harakat marks correctly (see Joining, Ligature, Harakat, and OpenType above) | The font must ship these shaping rules, not just the base glyphs; plain glyph substitution is not enough. See In practice below for a free, verified font recommendation |
| [Unicode](../../terms/unicode.md) block                   | Arabic, [U+0600 to U+06FF](https://www.unicode.org/charts/PDF/U0600.pdf), plus [Arabic Supplement](https://www.unicode.org/charts/PDF/U0750.pdf), [Arabic Extended-A](https://www.unicode.org/charts/PDF/U08A0.pdf), and [Arabic Presentation Forms A](https://www.unicode.org/charts/PDF/UFB50.pdf) and [B](https://www.unicode.org/charts/PDF/UFE70.pdf) | A font can cover the base Arabic block and still be missing characters some of this script's languages need (Persian, Urdu, Pashto, Sindhi, and Uyghur, among others, each rely on characters outside the base block), and the Presentation Forms blocks hold legacy precomposed shapes some older systems still expect. Check [font coverage](../../terms/font-coverage.md) across all of them for the languages you support, not just the base block |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Arabic glyphs AND the [shaping rules](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) (the four positional forms, the lam-alef ligature, mark placement), not just the base letters. [Noto Sans Arabic](https://fonts.google.com/noto/specimen/Noto+Sans+Arabic) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Test with a real word, not a glyph grid:** type a connected word such as كتب and confirm the letters join and pick up their positional forms; then test a line that mixes an Arabic phrase with a Latin name or a number and confirm the [bidirectional](bidirectional-text.md) order holds. Tool support for [complex text layout](../../terms/complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** Arabic, Persian, and Urdu all use the Arabic script and still differ in which symbols and digits they use and how they are set. Do not hardcode one language's choices; pull them from [locale](../../terms/locale.md) data. Unicode's [CLDR](../../terms/cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abjad](abjad.md) · [Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Bidirectional text](bidirectional-text.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Harakat](harakat.md) · [Hebrew script](hebrew-script.md) · [Joining](joining.md) · [Language](../linguistics/language.md) · [Letter spacing](../../terms/letter-spacing.md) · [Ligature](../../terms/ligature.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [OpenType features](../../terms/opentype-features.md) · [Orthography](orthography.md) · [Right-to-left](right-to-left.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../terms/shaping-engine.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Arabic Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/arabic)
* Design tools: [Noto Sans Arabic (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Arabic)
* Foundations: [Unicode Arabic code chart (U+0600)](https://www.unicode.org/charts/PDF/U0600.pdf)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The Arabic script is used for the Arabic language and has been extended to represent a number of other languages such as Persian, Urdu, Pashto, Sindhi, and Uyghur, as well as many African languages - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
2. The Middle Eastern scripts are mostly abjads; vowels and other marks may be written as combining marks called tashkil applied to the consonants, but in normal writing these marks are omitted - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
3. "When this script is used to represent the Arabic language, short vowels diacritics are omitted. In that case, the Arabic script is referred to as an 'abjad'... when this script is used to write some other languages (such as Kashmiri, Uighur, and most African languages), all vowels are represented, including short vowels. The Arabic script is then an 'alphabet'." - W3C: An Introduction to Writing Systems & Unicode [https://www.w3.org/International/questions/qa-scripts](https://www.w3.org/International/questions/qa-scripts)
4. In addition to digits, embedded words from English and other scripts are also written from left to right, also producing bidirectional text - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
5. The contextual analysis engine determines the correct contextual form a letter should take (isolated, initial, medial, or final) from the letters before and after it, and maps each to the OpenType isol, init, medi, and fina features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
6. When supported by the style of the font, lam-alef ligatures are considered obligatory - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
7. A font's OpenType rules select and position the correct Arabic forms (the positional forms, required ligatures such as lam-alef, and mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
8. The Arabic script is written from right to left - The Unicode Standard, Version 17.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-9/)
9. In right-to-left layouts, directional UI icons such as back and forward should be mirrored, while not all elements mirror (for example, charts can keep a left-to-right orientation) - Bidirectionality and RTL (Material Design 3) [https://m3.material.io/foundations/layout/bidirectionality-rtl](https://m3.material.io/foundations/layout/bidirectionality-rtl)
