---
term: Writing system
slug: writing-system
aliases: []
level: foundational
depth: deep
summary: "A writing system is a script applied to a specific language, together with the orthographic rules for writing it."
related:
  - language
  - script
  - orthography
  - latin-script
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Writing system (Wikipedia)
    url: https://en.wikipedia.org/wiki/Writing_system
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Writing system

## Definition

A writing system is a script applied to a specific language, together with the orthographic rules for writing it.&#x20;

Symbols belong to a script, and they follow their own script rules regardless of the language they are applied to.&#x20;

When a community sets rules for how a script is used to write their specific language, that becomes an orthography.&#x20;

A single language may use more than one script within one writing system (Japanese mixes four scripts: kanji, hiragana, katakana, and Latin<sup>1</sup>), or more than one writing system (Serbian can be written in either Cyrillic or Latin script depending on context<sup>2</sup>).&#x20;

### Why it matters in design systems

The goal is to zoom in and look at a part of a writing system, identify which typography properties it maps to, and make user-friendly decisions when working with text in a design system.

This is especially important when working with languages that are not commonly documented inside digital design systems.&#x20;

#### Example

For example, both French and Vietnamese languages use the Latin script in their writing systems. However, the orthography of each calls for differences in the marks used to modify the Latin symbols, which map to the line-height typographic property.

* French - one mark per letter
* Vietnamese - stacks multiple marks per letter<sup>3</sup>

Stacked marks take up more vertical space on a letter.<sup>4</sup> That extra height needs room between lines, which is what line height controls. That would mean a larger value for the line-height when working with the Vietnamese language compared to French.&#x20;



Or returning to the Serbian example from above, websites with automatic translations may assign the Latin script to render when Serbia as a location is detected from the user's profile. However, understanding that there is an alternate writing system of Cyrillic may change the website to allow for a user setting to choose between Latin and Cyrillic for a more optimal user experience.&#x20;



### Common mistake

> "We support the Latin alphabet, so we can easily support Vietnamese." - Some well intentioned team member who didn't know better

Checking that a font has the right glyphs at the script level and stopping there without checking the writing system layered on top of it.&#x20;

The glyphs render, so the language looks supported, right up until Vietnamese's stacked vowel-and-tone marks collide with a line-height you set for English. Later on you get complaints that the quotation marks are incorrect when the website is in French.&#x20;

The script was covered; the writing system was not. That is two different checks, and only one of them passed.



### In practice

Check support at both levels, because a font passing the script check tells you nothing about the writing-system check.&#x20;

* Script level: can the font draw and position the symbols and marks at all.&#x20;
* Writing-system level: does the language's own behavior survive, line-height room for stacked marks, plus locale-correct casing, hyphenation, quotation marks, and number formatting.

For multi-language design systems, map out all the font properties that need to change for each language, line-height is going to be one of them. Vietnamese needs more vertical room than French at the same size; if line-height is a single hardcoded number, the language with the tallest mark stacks is the one that clips.

When a language has more than one writing system, let the reader choose instead of guessing from location. A Serbian reader may want Cyrillic or Latin; detecting "Serbia" and forcing one script decides for them. A setting beats a guess.

***

### Related terms

* [Language](../linguistics/language.md)
* [Latin script](../../terms/latin-script.md)
* [Orthography](orthography.md)
* [Script](script.md)



### Further reading

* Foundations: [Writing system (Wikipedia)](https://en.wikipedia.org/wiki/Writing_system) <!-- NEEDS EXPERT REVIEW: Wikipedia is an interim authority; replace with a primary source for the writing-system concept when the cohort confirms one. -->
* Resource library: [Language support in fonts (Google Fonts Knowledge)](https://fonts.google.com/knowledge/using_type/language_support_in_fonts)



### Sources

1. Japanese script overview - W3C [https://www.w3.org/TR/jpan-lreq/#h\_script\_overview](https://www.w3.org/TR/jpan-lreq/#h_script_overview)
2. Serbian Unicode CLDR - [https://cldr.unicode.org/translation/displaynames/script-names](https://cldr.unicode.org/translation/displaynames/script-names)
3. Vietnamese vowel and tone stacking - W3C [https://www.w3.org/International/questions/qa-html-css-normalization.en.html](https://www.w3.org/International/questions/qa-html-css-normalization.en.html)
4. Vietnamese needs more vertical space - Google Fonts Knowledge [https://fonts.google.com/knowledge/using_type/language_support_in_fonts](https://fonts.google.com/knowledge/using_type/language_support_in_fonts)
