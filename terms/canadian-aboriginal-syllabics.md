---
term: Canadian Aboriginal Syllabics
slug: canadian-aboriginal-syllabics
aliases:
  - CAS
  - UCAS
  - Cree syllabics
level: advanced
depth: core
summary: Canadian Aboriginal Syllabics is a script used to write several Indigenous languages of Canada.
related:
  - syllabary
  - abugida
  - featural-alphabet
  - hangul
  - endangered-language
status: voice-passed
version_added: 0.1
updated: 2026-07-08T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Canadian Aboriginal (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Canadian+Aboriginal
    type: design-tool
  - title: Unicode Unified Canadian Aboriginal Syllabics code chart (U+1400)
    url: https://www.unicode.org/charts/PDF/U1400.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Canadian Aboriginal Syllabics

## Definition

Canadian Aboriginal Syllabics is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write several Indigenous languages of Canada. It is a [syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) that unifies the local syllabaries of those languages into a single repertoire,<sup>1</sup> and its distinctive feature is orientation: a consonant's symbol points a different way for each following vowel, down for /e/, up for /i/, right for /o/, and left for /a/.<sup>2</sup> Because the orientation of a symbol systematically encodes the vowel, it is often described as [featural](../language-terms/writing-systems-and-scripts/featural-alphabet.md), like [Hangul](hangul.md), and it works much like an [abugida](../language-terms/writing-systems-and-scripts/abugida.md). The syllabics were invented in the late 1830s by the missionary James Evans for the Algonquian languages,<sup>3</sup> and the communities who use them have carried and extended the script since.

For example, the consonant p is a chevron: ᐱ (pi) points up, ᐯ (pe) points down, ᐸ (pa) points left, and ᐳ (po) points right.

{% hint style="info" %}
This glossary doesn't cover every Canadian Aboriginal Syllabics property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Canadian Aboriginal Syllabics profile

These properties of Canadian Aboriginal Syllabics apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Canadian Aboriginal Syllabics |
| --- | --- |
| [Autonym](autonym.md) | No single autonym: the script is shared across many languages, each with its own name for it |
| Languages | Cree, Ojibwe, Inuktitut, and other Algonquian, Inuit, and Athabaskan (Dene) languages |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | None (vowel-modified forms are separate symbols, not a base plus a combining mark) |
| Numerals | common ASCII digits |
| Script type | [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) (often described as a featural syllabary or featural [abugida](../language-terms/writing-systems-and-scripts/abugida.md)) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | syllabic symbols, each a consonant plus a vowel (or a standalone vowel), where the symbol's orientation shows the vowel; separate final and standalone-consonant symbols too |

### Canadian Aboriginal Syllabics rules and digital use considerations

If your design system supports languages that use Canadian Aboriginal Syllabics, here are some considerations to keep in mind:

| Rule or feature | How it works in Canadian Aboriginal Syllabics | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required: each syllable is its own precomposed symbol, rendered directly | Each syllable is its own symbol, not a base plus a [combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md),<sup>4</sup> so there is no reordering or contextual shaping; the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each symbol straight to its glyph |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right | Left-aligned text as the default |
| Vowel by orientation | a consonant's symbol rotates or reflects to show the following vowel (down for /e/, up for /i/, right for /o/, left for /a/); each resulting syllable is a separate symbol | Orientation carries meaning, so never rotate, flip, or mirror these glyphs for effect: a mirrored ᐱ (pi) is not a styled p, it is ᐯ (pe), a different syllable |
| [Unicode](unicode.md) block | Unified Canadian Aboriginal Syllabics, [U+1400 to U+167F](https://www.unicode.org/charts/PDF/U1400.pdf) (plus Extended and Extended-A) | The primary user community spans several Indigenous groups across Canada,<sup>5</sup> and the symbols spread across a base block and extensions, so confirm [font coverage](font-coverage.md) for the specific language, not just the common Cree set |

### In practice

* **Cover the specific language, not "syllabics" in general:** confirm the font carries the symbols that language uses across the base and Extended blocks, not just the common Cree set. [Noto Sans Canadian Aboriginal](https://fonts.google.com/noto/specimen/Noto+Sans+Canadian+Aboriginal) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Never rotate or mirror the glyphs for style:** orientation encodes the vowel, so a flipped or turned symbol becomes a different syllable. Test with a real word and confirm each symbol points the right way.
* **Check the orthography, and which writing system a community uses:** several of these languages are also written in the [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md), and each has its own conventions, so do not assume one system or one language's symbols. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes, and defer to the community.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced language the conventions may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [CLDR](cldr.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Complex text layout](complex-text-layout.md) · [Endangered language](endangered-language.md) · [Featural script](../language-terms/writing-systems-and-scripts/featural-alphabet.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hangul](hangul.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Canadian Aboriginal (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Canadian+Aboriginal)
* Foundations: [Unicode Unified Canadian Aboriginal Syllabics code chart (U+1400)](https://www.unicode.org/charts/PDF/U1400.pdf)

### Sources

1. The characters in this block are a unification of various local syllabaries of Canada into a single repertoire based on character appearance - The Unicode Standard, Version 16.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/)
2. Typically the shape points down when the consonant is combined with the vowel /e/, up when combined with the vowel /i/, right when combined with the vowel /o/, and left when combined with the vowel /a/ - The Unicode Standard, Version 16.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/)
3. The syllabics were invented in the late 1830s by James Evans for Algonquian languages - The Unicode Standard, Version 16.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/)
4. Such modified characters are considered unique syllables; they are not decomposed into base characters and one or more diacritics - The Unicode Standard, Version 16.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/)
5. The primary user community for this script consists of several aboriginal groups throughout Canada, including Algonquian, Inuktitut, and Athapascan language families - The Unicode Standard, Version 16.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-20/)
</content>
</invoke>
