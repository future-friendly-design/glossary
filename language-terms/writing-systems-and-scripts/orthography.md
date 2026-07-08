---
term: Orthography
slug: orthography
aliases:
  - spelling system
level: intermediate
depth: deep
summary: >-
  Orthography is the set of language-specific rules for using a script to write
  a particular language: its spelling, capitalization, and punctuation
  conventions.
related:
  - dialect
  - script
  - writing-system
  - segmentation
  - input-method-editor
  - autonym
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: W3C Internationalization (i18n)
    url: https://www.w3.org/International/
    type: authority
  - title: CSS Color Module Level 4
    url: https://www.w3.org/TR/css-color-4/
    type: code
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Orthography

## Definition

Orthography is the set of language-specific rules for using a script to write a particular language: its spelling, capitalization, and punctuation conventions.

A [writing system](writing-system.md) is made of two parts: a [script](script.md) and an orthography. The script supplies the [symbols](symbol.md); the orthography is the language-specific layer that decides how one language uses them.

Two languages can share the same script and still follow different orthographies.\
\
Here are some of the rules an orthography sets, with examples of how the same script (Latin) changes between languages:

| Rule included in orthography | What it sets               | Example                        | Differs between        |
| ---------------------------- | -------------------------- | ------------------------------ | ---------------------- |
| Spelling                     | Which letters spell a word | `color` vs `colour`            | US and British English |
| Capitalization               | Which words take a capital | every noun capitalized, or not | German and English     |
| Punctuation                  | Which marks, placed how    | `"…"` vs `« … »`               | English and French     |
| Numbers                      | How digits are grouped     | `1,000.5` vs `1 000,5`         | English and French     |

### Why it matters in design systems

Orthography is rarely where you make a decision on its own. It matters because each discipline a design system spans handles the language layer differently, and a script the font can render is still not a language the system writes correctly.

To a linguist, the orthography is the set of rules a community agrees on for writing their language: how words are spelled, what gets a capital, which marks separate a sentence.

To typography, those rules decide which shapes actually appear: the quotation marks French expects are not the ones English expects, and a capital letter is a different [glyph](../../terms/glyph.md) from its lowercase form.

To a computer, the orthography lives in [locale](../../terms/locale.md) data, not in the font or the script. [Unicode](../../terms/unicode.md)'s [CLDR](../../terms/cldr.md) publishes per-language conventions, such as quotation marks and number formats, as machine-readable data.

So getting the script on screen is necessary, not sufficient. The symbols render, but the spelling, casing, and punctuation rules a native speaker reads as correct all live in the orthography on top.

#### Example

American and British English share one language and the same [Latin script](latin-script.md), but follow different orthographies: `color` and `organize` in one, `colour` and `organise` in the other.<sup>1</sup> Same words, same letters available, different spelling rules. Orthographies can differ more deeply than spelling, down to the script itself: Serbian is written in both [Cyrillic](cyrillic.md) and Latin,<sup>2</sup> which makes it two writing systems for one language.

### Common mistake

**The right script does not mean the right language support.** A font with full Latin glyphs has no opinion on whether the spelling is `color` or `colour`, whether every noun is capitalized (in German, it is), or which quotation marks French expects.<sup>3</sup> Those live in the orthography, not the script. Choosing a script gets the symbols on screen; it says nothing about the spelling, casing, and punctuation rules a language expects. A language code alone does not settle it either, since some languages (Serbian, Kurdish) use more than one orthography.

**Code has its own orthography, and it does not follow the user's locale.** The text a person reads should follow their language: a Canadian reader should see `colour` and `centre`, not `color` and `center`. But the CSS property that sets text colour is spelled `color`, the US way, in every stylesheet in the world, no matter what language the page is in.<sup>4</sup> A design-token type named `color` is the same. The mistake is "correcting" `color` to `colour` in the code because the site is Canadian. The browser does not recognize a property called `colour`, so it throws the whole rule away and the colour silently never applies.<sup>5</sup>

So orthography forks into two layers that must not be mixed. The words a person reads follow their locale. The words the computer reads follow the code's own fixed spelling, which never changes for anyone.

### In practice

* **Localize the human-facing text, not the code:** pull UI spelling, quotation marks, and capitalization from locale data, and keep CSS properties, token names, and identifiers in their canonical form. The two layers never merge, no matter how the rest of the site is spelled.
* **Treat orthography as configurable, not implied:** where a language has more than one orthography, let the choice be set (a locale variant, a user preference) rather than assuming it from the language or the script. This connects to [segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) (line-breaking and capitalization rules differ by orthography) and [input methods](../../terms/input-method-editor.md) (how users type the orthography they want).
* **Punctuation and casing are orthography, not afterthoughts:** quotation marks, decimal separators, and capitalization conventions vary by language, so they belong in localization data, not hardcoded UI strings.
* **Orthographies change:** which orthography a language uses, and which is current or preferred, is community-specific and shifts over time (spelling reforms, script revivals), so treat a language's current convention as something to verify with its speakers, not a constant you hardcode once.

***

### Related terms and mentions

[CLDR](../../terms/cldr.md) · [Cyrillic](cyrillic.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Locale](../../terms/locale.md) · [Localization](../../terms/localization.md) · [Script](script.md) · [Segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Symbol](symbol.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)
* Code & specs: [CSS Color Module Level 4](https://www.w3.org/TR/css-color-4/)

### Sources

1. American and British English spelling differences - Britannica Dictionary [https://www.britannica.com/dictionary/eb/qa/what-are-the-differences-between-British-and-American-English](https://www.britannica.com/dictionary/eb/qa/what-are-the-differences-between-British-and-American-English)
2. Serbian script names - Unicode CLDR [https://cldr.unicode.org/translation/displaynames/script-names](https://cldr.unicode.org/translation/displaynames/script-names)
3. French and English mark quotations with different characters: French uses guillemets « » where English uses curly quotes - W3C: Quotation marks and how to mark them up [https://www.w3.org/Style/2013/quote-marks](https://www.w3.org/Style/2013/quote-marks)
4. The CSS property that sets foreground colour is spelled `color` - W3C: CSS Color Module Level 4 [https://www.w3.org/TR/css-color-4/](https://www.w3.org/TR/css-color-4/)
5. A declaration whose property name the user agent does not recognize is invalid and is ignored - W3C: CSS Syntax Module Level 3 [https://www.w3.org/TR/css-syntax-3/](https://www.w3.org/TR/css-syntax-3/)
