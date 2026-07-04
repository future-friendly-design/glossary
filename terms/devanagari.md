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
updated: 2026-06-18T00:00:00.000Z
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

Devanagari is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Hindi, Marathi, Sanskrit, Nepali, and many other South Asian languages.<sup>1</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md): each consonant carries an inherent vowel that added marks change.<sup>2</sup>

For example, the greeting नमस्ते ("namaste") stacks and reorders its marks the way the script does throughout.

Devanagari is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Devanagari |
| --- | --- |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| Autonym | देवनागरी |
| Symbols | consonants carrying an inherent vowel, plus independent vowels |
| Marks | [matra](../language-terms/writing-systems-and-scripts/matra.md) (dependent vowels), [virama](../language-terms/writing-systems-and-scripts/virama.md), [nukta](../language-terms/writing-systems-and-scripts/nukta.md), and nasalization marks (anusvara, chandrabindu) |
| Case | None |
| Numerals | Devanagari digits ० to ९ (alongside common ASCII digits) |
| Unicode block | Devanagari, U+0900 to U+097F (plus Devanagari Extended) |
| Complex text layout | Yes, shaping required |
| Languages | Hindi, Marathi, Sanskrit, Nepali, and many others |

### Script rules and features

Script rules apply to any language that uses Devanagari in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page. Where a rule isn't documented for a script yet, that is noted here, and a contribution is welcome.

| Rule or feature | How it works in Devanagari |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) | a headline stroke runs along the top of the letters, joining them across a word |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | letters hang from the shirorekha rather than sitting on a bottom baseline |
| [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) | a left-side i-matra is typed after its consonant but displays before it, so the renderer reorders it |
| [Stacking](../language-terms/writing-systems-and-scripts/stacking-script.md) | consonant clusters combine into [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) forms |

### Why it matters in design systems

Treat this entry as a starting playbook for Devanagari, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Devanagari coverage, because the rules above will not render without it.

Where you cannot be creative is the script rules. Text runs left to right; a left-side [matra](../language-terms/writing-systems-and-scripts/matra.md) has to reorder;<sup>3</sup> consonant clusters have to form conjuncts;<sup>4</sup> and the [shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) has to join cleanly across a word. These are shaping requirements, carried by the font's OpenType rules and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), not styling choices. Skip them, with a tool or font that cannot shape, and the text is wrong, not merely plain.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the script allows (you cannot add letter spacing that breaks the headline). And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Devanagari glyphs AND the shaping rules (conjuncts, matra reordering), not just the base letters. [Noto Sans Devanagari](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word with a conjunct and a left-side matra and confirm they form and reorder; tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share Devanagari and still differ in which symbols they use and how. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and contribute them upstream so the next team can find them.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Bengali-Assamese](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Locale](locale.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [Nukta](../language-terms/writing-systems-and-scripts/nukta.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
* Design tools: [Noto Sans Devanagari (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Devanagari)
* Foundations: [Unicode Devanagari code chart (U+0900)](https://www.unicode.org/charts/PDF/U0900.pdf)

### Sources

1. Devanagari is written left to right and used for Sanskrit, Hindi, Marathi, Nepali, and many other languages - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. Devanagari and the other Indic scripts are abugidas, a cross between syllabic and alphabetic writing systems, in which each consonant carries an inherent vowel - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
3. Indic-script rendering must reorder elements from the logical (character) store to the visual (glyph) order, which is why a left-side matra stored after its consonant displays before it - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
4. A consonant cluster is normally depicted with a conjunct glyph when the font provides one - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
