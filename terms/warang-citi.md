---
term: Warang Citi
slug: warang-citi
aliases:
  - Varang Kshiti
  - Warang Kshiti
level: advanced
depth: core
summary: Warang Citi is a script used to write the Ho language, a North Munda language of eastern India.
related:
  - alphabet
  - ol-chiki
  - wancho-script
  - devanagari
  - endangered-language
status: voice-passed
version_added: 0.1
updated: 2026-07-08T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Warang Citi (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Warang+Citi
    type: design-tool
  - title: Unicode Warang Citi code chart (U+118A0)
    url: https://www.unicode.org/charts/PDF/U118A0.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Warang Citi

## Definition

Warang Citi is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write the Ho language, a North Munda language of eastern India. It is a recently devised, left-to-right [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md),<sup>1</sup> used for a language with an emergent literary tradition.<sup>2</sup> It was developed in the 1950s by Lako Bodra; in Ho tradition the script is credited to a thirteenth-century sage, Deowan Turi, which Bodra is said to have revived and modernized.<sup>3</sup>

For example, the script's own name 𑢹𑣗𑣁𑣜𑣊 𑣏𑣂𑣕𑣂 ("Warang Citi") is written left to right, each vowel and consonant its own full letter.

{% hint style="info" %}
This glossary doesn't cover every Warang Citi property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Warang Citi profile

These properties of Warang Citi apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Warang Citi |
| --- | --- |
| [Autonym](autonym.md) | 𑢹𑣗𑣁𑣜𑣊 𑣏𑣂𑣕𑣂 |
| Languages | Ho |
| Letter case | Bicameral (capital and small letters), unusual among the region's scripts |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Vowels are written as full letters, not dependent marks |
| Numerals | Warang Citi digits (U+118E0 to U+118E9), alongside common ASCII digits |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | full letters for consonants and vowels |

### Warang Citi rules and digital use considerations

If your design system supports languages that use Warang Citi, here are some considerations to keep in mind:

| Rule or feature | How it works in Warang Citi | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required: a linear alphabet, rendered directly (no conjuncts or reordering) | Not complex to shape, no reordering or contextual analysis; the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each letter straight to its glyph |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right | Left-aligned text as the default |
| Letter case | it distinguishes capital and small letters (bicameral), unlike most scripts of the region | Casing is real here, so confirm the font ships both the capital and small letters and that casing behaves as the community expects |
| [Unicode](unicode.md) block | Warang Citi, [U+118A0 to U+118FF](https://www.unicode.org/charts/PDF/U118A0.pdf) | Ho has an emergent literary tradition and Warang Citi is a purpose-built community script, so fonts, a [keyboard layout](keyboard-layout.md), and rendering for it are a concrete deliverable; a Latin or [Devanagari](devanagari.md) font will not render it, so confirm [font coverage](font-coverage.md) |

### In practice

* **Cover the script and give people a way to type it:** confirm the font ships the Warang Citi capital and small letters and digits, and pair it with a [keyboard layout](keyboard-layout.md) so the community can enter text. [Noto Sans Warang Citi](https://fonts.google.com/noto/specimen/Noto+Sans+Warang+Citi) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Handle case, and test with a real word:** because the script is bicameral, confirm case behaves as the community expects, then set a real Ho word and confirm the letters render cleanly at your text sizes.
* **Check the orthography, and which script the community uses:** Ho is written in Warang Citi, Devanagari, Ol Chiki, Odia, Telugu, and Latin in different places, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced language the conventions may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Endangered language](endangered-language.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Noto fonts](noto-fonts.md) · [Ol Chiki](ol-chiki.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Wancho script](wancho-script.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Warang Citi (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Warang+Citi)
* Foundations: [Unicode Warang Citi code chart (U+118A0)](https://www.unicode.org/charts/PDF/U118A0.pdf)

### Sources

1. The Warang Citi script is a recently devised left-to-right alphabet - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
2. The script is used to write the Ho language, a North Munda language which has an emergent literary tradition - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
3. Warang Citi was developed in the 1950s by Lako Bodra, who in Ho tradition revived a script credited to the thirteenth-century sage Deowan Turi (secondary source, interim pending an upgrade to a primary attribution) - Warang Citi (Wikipedia) [https://en.wikipedia.org/wiki/Warang\_Citi](https://en.wikipedia.org/wiki/Warang_Citi)
</content>
