---
term: Tibetan script
slug: tibetan-script
aliases:
  - tibetan
level: intermediate
depth: core
summary: The Tibetan script is a script used to write Tibetan, Dzongkha, Ladakhi, and other languages of the Himalayas.
related:
  - abugida
  - brahmic-scripts
  - stacking-script
  - tsheg
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Tibetan Text Layout Requirements (W3C)
    url: https://www.w3.org/TR/tibt-lreq/
    type: code
  - title: Noto Sans Tibetan (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan
    type: design-tool
  - title: 'Unicode Tibetan code chart (U+0F00)'
    url: https://www.unicode.org/charts/PDF/U0F00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Tibetan script

## Definition

The Tibetan script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Tibetan, Dzongkha, Ladakhi, and other languages of the Himalayas.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](../language-terms/writing-systems-and-scripts/abugida.md) of thirty consonants, each carrying an inherent vowel that vowel marks can change.<sup>2</sup>

For example, the Tibetan script's own name for itself, བོད་ཡིག, places a dot called a tsheg between its two syllables, བོད and ཡིག, because Tibetan marks syllable boundaries with the tsheg rather than spacing between words.

The Tibetan script is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Tibetan script |
| --- | --- |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| Autonym | བོད་ཡིག |
| Symbols | thirty consonants carrying an inherent vowel, plus vowel marks |
| Marks | four vowel [marks](../language-terms/writing-systems-and-scripts/mark.md) placed above and below the consonant, and subjoined consonant forms that build a stack |
| Letter case | None (no uppercase and lowercase) |
| Numerals | Tibetan digits ༠ to ༩ (alongside common ASCII digits) |
| Unicode block | Tibetan, [U+0F00 to U+0FFF](https://www.unicode.org/charts/PDF/U0F00.pdf) |
| [Complex text layout](complex-text-layout.md) | Yes, shaping and syllable segmentation required |
| Languages | Tibetan, Dzongkha, Ladakhi, and others |

### Script rules and features

Script rules apply to any language that uses the Tibetan script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Tibetan script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| [Stacking](../language-terms/writing-systems-and-scripts/stacking-script.md) | consonant clusters are built as vertical stacks: subjoined consonants pile below a root consonant, and a superscript consonant can sit above it |
| [Tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) | a dot (the tsheg) marks syllable boundaries; Tibetan spaces syllables rather than words, so line breaking keys on the tsheg rather than on whitespace |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | glyphs hang from a strong top edge |

### Why it matters in design systems

Treat this entry as a starting playbook for the Tibetan script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Tibetan coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right.<sup>3</sup> Consonant clusters are not placed side by side but built into vertical stacks, a root consonant with others subjoined below and sometimes one above, so the word རྒྱུད ("rgyud") is a single stack read top to bottom.<sup>4</sup> A stack can be several letters tall, so the line has to leave room for it. Tibetan also spaces syllables rather than words: a dot called the tsheg marks the boundary, and line breaking keys on the tsheg rather than on whitespace.<sup>5</sup> The text between two tshegs is a syllable unit that segmentation has to work on.<sup>6</sup> Building the stacks is shaping work, carried by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), the step that turns stored characters into positioned glyphs; the segmentation is a separate layout step. These are not styling choices: get the stacks or the line breaking wrong and the text renders or wraps incorrectly, not just unstyled.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script allows (line height has to clear the tallest stacks, and you cannot break a line mid-stack) and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font builds the vertical stacks (subjoined and superscript consonants) and places the vowel marks, not just the base consonants. [Noto Sans Tibetan](https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Give the line room and test real stacks:** because a stack can be several consonants tall, set line height from real stacked text, not from a single row of base letters, and confirm the stacks build rather than sitting side by side. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Break on the tsheg, not on spaces or characters:** line breaking, search, and truncation key on the tsheg and its syllable units, so do not split Tibetan on spaces or mid-stack. Pull the conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Language](../language-terms/linguistics/language.md) · [Line height](line-height.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Tibetan Text Layout Requirements (W3C)](https://www.w3.org/TR/tibt-lreq/)
* Design tools: [Noto Sans Tibetan (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan)
* Foundations: [Unicode Tibetan code chart (U+0F00)](https://www.unicode.org/charts/PDF/U0F00.pdf)

### Sources

1. The Tibetan script is used for writing Tibetan in several countries and regions throughout the Himalayas, and is also used in Bhutan to write Dzongkha - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
2. The Tibetan script has 30 consonants, each represented by a discrete written character, and vowel marks are applied to indicate vowels other than the inherent one - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
3. Tibetan text runs left to right in horizontal lines - Tibetan Text Layout Requirements (W3C) [https://www.w3.org/TR/tibt-lreq/](https://www.w3.org/TR/tibt-lreq/)
4. A base or root consonant can be written singly or have other consonants added above or below it to make a vertically stacked letter - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
5. The primary line-break character in Tibetan is the interword tsheg (U+0F0B), which separates syllables; whitespace can appear in Tibetan text, but lines break after the tsheg rather than at spaces - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
6. Tibetan words comprise units called tsheg-bar, basically phonological syllables, separated by the tsheg, and it is these units that line breaking operates on - Tibetan Text Layout Requirements (W3C) [https://www.w3.org/TR/tibt-lreq/](https://www.w3.org/TR/tibt-lreq/)
