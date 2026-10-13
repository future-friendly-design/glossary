---
term: Case mapping
slug: case-mapping
aliases: [case conversion, uppercasing, lowercasing]
tags: [i18n-engineering]
level: intermediate
depth: deep
summary: Case mapping is the process software uses to change text from one letter case to another, such as from lowercase to uppercase.
tool_names:
  css: text-transform
related: [locale, internationalization, orthography]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "text-transform (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform
    type: code
  - title: "The Unicode Standard 18.0, Chapter 5: Implementation Guidelines, section 5.18 Case Mappings"
    url: https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/
    type: authority
license: CC-BY-4.0
---

# Case mapping

## Definition

Case mapping is the process software uses to change text from one letter case to another, such as from lowercase to uppercase.<sup>1</sup>

Letter case is the pairing of two forms of the same letter, a capital one and a small one, such as A and a.<sup>2</sup> Only some [scripts](../../language-terms/writing-systems-and-scripts/script.md) have it. Latin, Greek, Cyrillic, and Armenian do, and so do Cherokee<sup>3</sup> and Adlam.<sup>4</sup> Many scripts have no case at all, among them Arabic, Devanagari, Hangul, and Chinese characters.<sup>5</sup>

### Why it matters in design systems

A button label in capital letters, a small heading above a card, a row of navigation tabs: design systems set text in all capitals everywhere. Usually nobody retypes the words. A text style carries an uppercase setting, and the software changes the letters at the moment it shows them. The setting sits beside the font size and the weight, so it reads as one more visual choice.

It is a different kind of choice. Size and weight change how the same characters are drawn, while uppercase replaces them with other characters, and which characters those are depends on the language the text is written in. An uppercase style that was designed and checked with English words is an English rule.

Here is what happens to six words when their case is changed:

| Text | Change | Result | What happened |
| ---- | ------ | ------ | ------------- |
| Turkish `istanbul` | To uppercase | `İSTANBUL` | Turkish has two separate letters, i with a dot and ı without, and each keeps its dot or its lack of one as a capital.<sup>6</sup> English rules give `ISTANBUL`, which is the capital of the other letter. Azerbaijani follows the same rule as Turkish.<sup>7</sup> |
| German `straße` | To uppercase | `STRASSE` | The letter ß becomes two letters, so the word is one character longer.<sup>8</sup> |
| Greek `άσπρος` ("white") | To uppercase | `ΑΣΠΡΟΣ` | With Greek rules, a vowel loses its accent when the whole word is in capitals, so the accent on ά is dropped.<sup>9</sup> Rules that do not know this give `ΆΣΠΡΟΣ`. The word also holds two shapes of one small letter, σ inside a word and ς at the end of one, and both become the same capital, Σ.<sup>10</sup> Going back to small letters is harder: nothing in the capitals says where the accent was.<sup>11</sup> |
| Dutch `ijsland` | Capital on the first letter | `IJsland` | In Dutch the pair ij works as one unit at the start of a word, so both letters become capitals.<sup>12</sup> Rules that do not know this give `Ijsland`. |
| Georgian `აკაკი` | To uppercase | `ᲐᲙᲐᲙᲘ` | Unicode, the shared list of characters that software uses, pairs each everyday Georgian letter with a capital from a separate set of characters, called Mtavruli, which Georgian writing uses for headlines and emphasis.<sup>13</sup> Not all software makes this change. Web browsers have differed on it, and some leave Georgian text as it was.<sup>14</sup> Georgian does not put a capital at the start of a word or a sentence, so a "capitalize each word" setting has nothing to change.<sup>15</sup> |
| Hindi `नमस्ते`, written in Devanagari | To uppercase | `नमस्ते` | Devanagari has no case, so nothing changes.<sup>16</sup> |

<!-- NEEDS EXPERT REVIEW: source 14. Browser handling of Georgian under text-transform: uppercase is data that ages. The W3C results were recorded on 28 March 2019 (Firefox 65 fail, Chrome 73 fail, Safari 12.1 pass). Checked again on 2026-10-13: headless Chrome 155 left Mkhedruli unchanged with and without lang="ka", and with lang="nl" it gave "Ijsland" for text-transform: capitalize. Current Firefox and Safari were not checked. CSS Text Level 3 has no Georgian exception, so by the specification uppercase should give Mtavruli. -->

Three things in that table reach into layout and [tokens](../../design-terms/design-token.md). Text can get longer, and a single character can become as many as three.<sup>17</sup> The same letters need different capitals in different languages. And in a script without case the setting does nothing, so a style that people recognize only because it is in capitals stops being recognizable.

On the web, the uppercase setting is the CSS property `text-transform`. It changes what is shown and leaves the stored text as it was typed.<sup>18</sup> It applies the rules of a particular language only when the page says which language the text is in.<sup>19</sup>

That is where case mapping meets [locale](locale.md), and where the two differ. A locale is the setting that tells software which language and regional conventions a person wants. Case mapping is one of the behaviours that needs to know a language, but the language it needs is the language of the text, which may not be the language of the screen around it. A Turkish name on an English page still needs Turkish capitals.

Two neighbours are easy to mistake for case mapping. A "capitalize each word" setting is not title case, because which words take a capital in a title depends on the language.<sup>20</sup> And matching text while ignoring capitals, as a search box does, is a separate operation called case folding. It is made for comparing text, where case mapping is made for showing it.<sup>21</sup>

### Also called

CSS: `text-transform`

### Common mistake

Changing the case of the text that is stored, on the assumption that it can be changed back. It cannot.<sup>22</sup> A German street name saved as `STRASSE` comes back as `strasse`: the ß is gone, and nothing in the data says it was ever there. A database of customer names saved in capitals has lost the same kind of information for every name in it. Keep text the way its author wrote it, and change the case only when showing it.

### In practice

* **Mark the language of the text, not only of the page.** Names, addresses, and anything people type can be in a different language from the interface. A component that shows such text in capitals needs to pass the language along with the words, or the capitals will follow the wrong rules.
* **Give every all-capitals style a second plan.** In a script without case, decide what carries the emphasis instead: weight, size, colour, or spacing. Write that decision into the description of the text style or token, so that the style still does its job in Arabic, Hindi, Chinese, and Korean.
* **Test with the words that break.** Try `istanbul` marked as Turkish, `straße`, `ijsland` marked as Dutch, a Greek word with an accent, a Georgian word, and a word in a script without case. Check the letters first, in each browser and app the product supports, because they do not all apply the same rules. Then check the width of the component, because the text may have grown. If the Georgian word changed, check that the font in use has shapes for the Georgian capitals.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Armenian script](../../language-terms/writing-systems-and-scripts/armenian-script.md) · [Character](../text-in-software/character.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Design token](../../design-terms/design-token.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Georgian script (Mkhedruli)](../../language-terms/writing-systems-and-scripts/georgian-script.md) · [Greek script](../../language-terms/writing-systems-and-scripts/greek-script.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Hangul script](../../language-terms/writing-systems-and-scripts/hangul.md) · [Internationalization](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Orthography](../../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Unicode](../text-in-software/unicode.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [text-transform (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
* Foundations: [The Unicode Standard 18.0, Chapter 5: Implementation Guidelines, section 5.18 Case Mappings](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)

### Sources

1. Case mapping: "The process of transforming characters to a specific case, such as UPPER, lower, or Titlecase" - Internationalization Glossary, W3C Group Note [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
2. "Case is a normative property of characters in specific alphabets such as Latin, Greek, Cyrillic, Armenian, and archaic Georgian, whereby characters are considered to be variants of a single letter" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18 Case Mappings [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
3. "Starting with Version 8.0, the Unicode Standard includes a set of lowercase Cherokee syllables to accommodate the need to represent casing distinctions in Cherokee text" - The Unicode Standard, Version 18.0, Chapter 20, section 20.1 Cherokee [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-20/)
4. "Adlam is a casing script with right-to-left directionality" - The Unicode Standard, Version 18.0, Chapter 19, section 19.9 Adlam [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-19/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-19/)
5. No character assigned to the Arabic, Devanagari, Hangul, or Han script has an uppercase, lowercase, or titlecase mapping in the Unicode Character Database, checked by script against the 18.0 data files - UnicodeData.txt, Unicode Character Database 18.0 [https://www.unicode.org/Public/18.0.0/ucd/UnicodeData.txt](https://www.unicode.org/Public/18.0.0/ucd/UnicodeData.txt)
6. "The principal example of a case mapping that depends on the locale is Turkish, where U+0131 “ı” LATIN SMALL LETTER DOTLESS I maps to U+0049 “I” LATIN CAPITAL LETTER I and U+0069 “i” LATIN SMALL LETTER I maps to U+0130 “İ” LATIN CAPITAL LETTER I WITH DOT ABOVE" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.2 Complications for Case Mapping [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
7. "I and i-dotless; I-dot and i are case pairs in Turkish and Azeri" - SpecialCasing.txt, Unicode Character Database 18.0 [https://www.unicode.org/Public/18.0.0/ucd/SpecialCasing.txt](https://www.unicode.org/Public/18.0.0/ucd/SpecialCasing.txt)
8. "the German character U+00DF ß LATIN SMALL LETTER SHARP S expands when uppercased to the sequence of two characters “SS”" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.2 Complications for Case Mapping [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
9. "In Greek (el), vowels lose their accent when the whole word is in uppercase" - MDN Web Docs, text-transform [https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
10. "U+03A3 “Σ” GREEK CAPITAL LETTER SIGMA typically lowercases to U+03C3 “σ” GREEK SMALL LETTER SIGMA if it is followed by another letter, but typically lowercases to U+03C2 “ς” GREEK SMALL LETTER FINAL SIGMA if it is not" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.2 Complications for Case Mapping [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
11. "Automatically converting from ALL-CAPS Greek to lowercase is very difficult, since there are no indications about where the tonos accent needs to appear" - Summarized test results: case conversion, W3C Internationalization [https://www.w3.org/International/i18n-tests/results/case-conversion](https://www.w3.org/International/i18n-tests/results/case-conversion)
12. "In Dutch (nl), the ij digraph becomes IJ, even with text-transform: capitalize, which only puts the first letter of a word in uppercase" - MDN Web Docs, text-transform [https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
13. "For most of modern Mkhedruli writing, Mtavruli has been used as an emphatic or headline style. In Version 11.0 of the Unicode Standard, that usage was broadened to define formal case pair mappings between these forms, with Mkhedruli serving as lowercase and Mtavruli serving as uppercase" - The Unicode Standard, Version 18.0, Chapter 7, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
14. "These tests check whether mkedruli characters are converted to mtavruli characters (new in Unicode v11) when text-transform:uppercase is applied to the former", with recorded results of fail for Firefox and for Chrome and pass for Safari - Summarized test results: case conversion, W3C Internationalization [https://www.w3.org/International/i18n-tests/results/case-conversion](https://www.w3.org/International/i18n-tests/results/case-conversion)
15. "Georgian casing established in Version 11.0 does not extend to title casing, as the Georgian script does not have title casing for individual words or sentences" - The Unicode Standard, Version 18.0, Chapter 7, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
16. "a caseless letter always case maps to itself" - The Unicode Standard, Version 18.0, Chapter 4, section 4.2 Case [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-4/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-4/)
17. "The maximum string expansion as a result of case mapping in the Unicode Standard is three" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.2 Complications for Case Mapping [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
18. "This property transforms text for styling purposes. It has no effect on the underlying content" - CSS Text Module Level 3, W3C Candidate Recommendation Draft, section 2.1 [https://www.w3.org/TR/css-text-3/#text-transform-property](https://www.w3.org/TR/css-text-3/#text-transform-property)
19. "If (and only if) the content language of the element is, according to the rules of the document language, known, then any appropriate language-specific rules must be applied as well" - CSS Text Module Level 3, W3C Candidate Recommendation Draft, section 2.1.1 Mapping Rules [https://www.w3.org/TR/css-text-3/#text-transform-property](https://www.w3.org/TR/css-text-3/#text-transform-property)
20. "The choice of which words to titlecase in headings and titles is dependent on language and local conventions" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.1 Titlecasing [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
21. Case folding "is meant for the purpose of string matching. This is distinct from case mapping, which is primarily meant for display purposes" - Internationalization Glossary, W3C Group Note [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
22. "No casing operations are reversible" - The Unicode Standard, Version 18.0, Chapter 5, section 5.18.3 Reversibility [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
