---
term: Script
slug: script
aliases: []
level: foundational
depth: deep
summary: A script is the set of visual symbols, marks, and rules used to write one or more languages.
related:
  - alphabet
  - abugida
  - abjad
  - syllabary
  - logographic
  - featural-alphabet
  - brahmic-scripts
  - font-coverage
  - writing-system
  - script-typeface
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Script'
    url: https://www.unicode.org/glossary/#script
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Script

{% hint style="info" %}
This is the writing-systems sense of "script." For the type-design classification, see [Script (typeface)](../../terms/script-typeface.md); the computing sense (a program) is out of scope in this glossary. A script applied to one language with its spelling and punctuation rules is a [writing system](writing-system.md).
{% endhint %}

## Definition

A script is the set of visual [symbols](symbol.md), [marks](mark.md), and [rules](script-rules.md) used to write one or more languages.

### Why it matters in design systems

Script and language are not the same thing, and conflating them is one of the most common mistakes in interface work. A single script can serve many languages (the [Latin script](../../terms/latin-script.md) writes languages as varied as English, Vietnamese, and Swahili<sup>1</sup>), and a single language can be written in more than one script.

In a design system, the script is the unit that drives your typography decisions. The scripts you support determine which [typefaces](../../terms/typeface.md) and [fonts](../../terms/font.md) you can use (a font only helps if it has [coverage](../../terms/font-coverage.md) for the script), the [line height](../../terms/line-height.md) and spacing the text needs, the [text direction](../../terms/text-direction.md) it runs in, and the [shaping](../../terms/text-shaping.md) and input it requires. So "we support English and Hindi" is not one job done twice; it is two scripts with different fonts, different vertical metrics, and different layout behavior.

Scripts are classified by what each symbol represents, and each type behaves differently across those properties: [alphabets](../../terms/alphabet.md), [abjads](../../terms/abjad.md), [abugidas](../../terms/abugida.md), [alphasyllabaries](../../terms/alphasyllabary.md), [syllabaries](../../terms/syllabary.md), [logographic](../../terms/logographic.md), [logosyllabary](../../terms/logosyllabary.md), [ideographic](../../terms/ideographic.md), [featural](../../terms/featural-alphabet.md), and [pictographic](../../terms/pictographic.md) systems, plus families like [Brahmic scripts](../../terms/brahmic-scripts.md) and [CJK](../../terms/cjk.md). The scripts you choose to cover define the typographic and engineering work ahead.

#### Example

English, Vietnamese, and Turkish are all written with the same script (Latin) but are different languages. Conversely, Serbian is written in both Cyrillic and Latin.<sup>2</sup>

### Common mistake

Treating "languages supported" as the planning unit and assuming a font or layout that works for one language works for the rest. Coverage is per script: a typeface that handles English fine may have no glyphs for Devanagari or Arabic, and a layout that works left to right may break entirely for a right-to-left or [stacking](../../terms/stacking-script.md) script.

### In practice

* **Plan support by script, then verify** [**font coverage**](../../terms/font-coverage.md)**:** the question "do we support Hindi?" is really "do our fonts and shaping cover Devanagari, and does our layout handle its reordering and conjuncts?" Pick fonts with genuine coverage for every script you ship, not just Latin.
* **Do not assume Latin defaults:** spacing, capitalization, line breaking, and input all vary by script. What looks correct in English is not evidence the script is rendering correctly.
* **Confirm the script before the font:** which script a language uses is not always obvious, and some languages use more than one, so verify the script-to-language mapping from a reliable source before committing fonts and layout.

***

### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Abugida](../../terms/abugida.md) · [Alphabet](../../terms/alphabet.md) · [Alphasyllabary](../../terms/alphasyllabary.md) · [Arabic script](../../terms/arabic-script.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [CJK](../../terms/cjk.md) · [Conjunct](../../terms/conjunct.md) · [Cyrillic](../../terms/cyrillic.md) · [Devanagari](../../terms/devanagari.md) · [Featural alphabet](../../terms/featural-alphabet.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ideographic](../../terms/ideographic.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Keyboard layout](../../terms/keyboard-layout.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Logographic](../../terms/logographic.md) · [Logosyllabary](../../terms/logosyllabary.md) · [Mark](mark.md) · [Pictographic](../../terms/pictographic.md) · [Reordering](../../terms/reordering.md) · [Script (typeface)](../../terms/script-typeface.md) · [Script rules](script-rules.md) · [Segmentation](../../terms/segmentation.md) · [Shaping engine](../../terms/shaping-engine.md) · [Stacking script](../../terms/stacking-script.md) · [Syllabary](../../terms/syllabary.md) · [Symbol](symbol.md) · [Text direction](../../terms/text-direction.md) · [Text shaping](../../terms/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Writing system](writing-system.md) · [Writing systems & scripts](README.md)

### Further reading

* Foundations: [Unicode Glossary: Script](https://www.unicode.org/glossary/#script)

### Sources

1. A script serves multiple languages - Unicode Glossary: Script [https://www.unicode.org/glossary/#script](https://www.unicode.org/glossary/#script)
2. Serbian script names - Unicode CLDR [https://cldr.unicode.org/translation/displaynames/script-names](https://cldr.unicode.org/translation/displaynames/script-names)
