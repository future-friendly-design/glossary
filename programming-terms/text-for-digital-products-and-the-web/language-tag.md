---
term: Language tag
slug: language-tag
aliases: [BCP 47 language tag, IETF language tag]
tags: [i18n-engineering]
level: foundational
depth: deep
summary: A language tag is a short code that labels a piece of text with the language it is in.
related: [locale, iso-639-3, script, internationalization]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "lang global attribute (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/lang
    type: code
  - title: "Language tags in HTML and XML (W3C)"
    url: https://www.w3.org/International/articles/language-tags/
    type: authority
license: CC-BY-4.0
---

# Language tag

## Definition

A language tag is a short code that labels a piece of text with the language it is in.<sup>1</sup>

The code is built from pieces joined by hyphens.<sup>2</sup> The first piece always names the language.<sup>3</sup> Each piece after it narrows the meaning.<sup>4</sup> Two kinds of later piece matter most in design work. One names the [script](../../language-terms/writing-systems-and-scripts/script.md), the set of symbols the text is written in, such as Latin or Cyrillic. The other names a region, for the version of the language used in one place.

### Why it matters in design systems

A person can usually tell what language a sentence is in by reading it. Software is in a weaker position, and with short text it has very little to go on: `chat` is a conversation in English and a cat in French. So the text carries a label that says which language it is. On a web page the label is written into the page's code, in a setting called the `lang` attribute, and its value has to be a language tag.<sup>5</sup>

The label is not decoration. Software reads it and changes what it does with the text:

| What the reader notices | What the software does with the tag |
| ----------------------- | ----------------------------------- |
| The shapes of the characters | Chinese, Japanese and Korean text can be stored as the same character, yet readers of each language expect it to be drawn a little differently.<sup>6</sup> Some browsers use the tag to choose a font with the shapes that language expects.<sup>7</sup> |
| Words broken across two lines | Breaking a long word with a hyphen follows rules that differ by language, so a browser is only expected to do it for text whose language it has been told.<sup>8</sup> |
| Text read aloud | A screen reader is software that reads the screen aloud, used by people who cannot see it. The tag tells it which language's pronunciation rules to load.<sup>9</sup> |
| Spelling | A spelling checker can check the text against the right language, or leave alone text in a language it does not know.<sup>10</sup> |

Leave the tag off, or leave the wrong one on, and each of these goes wrong quietly. The page still appears. It is read aloud in the wrong accent, set in shapes meant for a neighbouring language, and never hyphenated.

A language tag is often confused with a [locale](locale.md). A locale is a set of preferences for one language as used in one place, covering things such as how dates and numbers are written, and it is named by a code that is usually a language tag.<sup>11</sup> So one code can do two jobs. As a language tag it describes the text: this paragraph is in French. As the name of a locale it describes the reader: this person expects dates the way they are written in Canada. A design has to get both right, and they are not always the same code.

### Examples

Each row below adds one piece to the tag.

| Tag | Pieces | What it says |
| --- | ------ | ------------ |
| `fr` | language | French<sup>12</sup> |
| `ast` | language | Asturian. The code has three letters because this language has no two-letter code.<sup>13</sup> |
| `fr-CA` | language, region | French as used in Canada<sup>14</sup> |
| `az-Latn` | language, script | Azerbaijani written in the Latin script. Azerbaijani can also be written in the Arabic or Cyrillic script, so the script is worth stating.<sup>15</sup> |
| `zh-Hant-HK` | language, script, region | Chinese in Traditional characters, as used in Hong Kong<sup>16</sup> |

The order is fixed: language first, then script, then region.<sup>17</sup> The capital letters are a habit that makes tags easier to read, with the language in lower case, the script starting with a capital and the region in capitals, and they do not change the meaning.<sup>18</sup>

A longer tag is not a better one. The rule is to keep the tag as short as possible and to add a piece only when it separates this text from something else.<sup>19</sup> Japanese is `ja`, not `ja-JP`, unless it matters that this is the Japanese of Japan.

The pieces are not made up by each product. They are all listed in one public file, the IANA Language Subtag Registry.<sup>20</sup> The language pieces follow an international standard list of language codes called ISO 639.<sup>21</sup> A language gets its two-letter code if it has one, and a three-letter code if it does not.<sup>22</sup> Thousands of those three-letter codes come from the part of that standard called [ISO 639-3](../../language-terms/linguistics/iso-639-3.md).<sup>23</sup> This is the point that matters most to a language community: a language with no two-letter code is not a language that cannot be tagged.

### Common mistake

Using a region to stand in for a script. For years, Chinese text was labelled `zh-CN`, which means Chinese as spoken in China, when what people meant was "written in Simplified characters", even for text from Singapore.<sup>24</sup> A region says where a language is used. A script says which symbols it is written in. When the difference you care about is the writing, say so with a script piece: `zh-Hans` for Simplified and `zh-Hant` for Traditional.<sup>25</sup>

### In practice

* **Label the page, then label the exceptions.** Give the whole page one tag for its main language, which accessibility guidelines require.<sup>26</sup> Then give a separate tag to any part in another language: a quoted phrase, a person's name, each language's own name in a language picker.<sup>27</sup>
* **Look the pieces up; do not guess them.** A language code and a country code can look alike and mean different things. `ja` is the language Japanese,<sup>28</sup> and `JP` is the region Japan.<sup>29</sup> Search the registry for the language by its English name and check that the entry you found is the right type.
* **Write the tag into the design.** When a component shows text in more than one language, note the tag for each part in the handoff, next to the font and the colour. A tag is easy to add while the content is being made and hard to add afterwards.<sup>30</sup>

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [CLDR](cldr.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Font](font.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Internationalization](internationalization.md) · [ISO 639-3](../../language-terms/linguistics/iso-639-3.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Macrolanguage](../../language-terms/linguistics/macrolanguage.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [lang global attribute (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/lang)
* Foundations: [Language tags in HTML and XML (W3C)](https://www.w3.org/International/articles/language-tags/)

### Sources

1. "Language tags are used to help identify languages, whether spoken, written, signed, or otherwise signaled, for the purpose of communication" - RFC 5646: Tags for Identifying Languages, section 2 [https://www.rfc-editor.org/rfc/rfc5646](https://www.rfc-editor.org/rfc/rfc5646)
2. "distinguished and separated from other subtags in a tag by a hyphen" - RFC 5646: Tags for Identifying Languages, section 2.1 [https://www.rfc-editor.org/rfc/rfc5646](https://www.rfc-editor.org/rfc/rfc5646)
3. "All language tags must begin with a primary language subtag" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
4. "each of which refines or narrows the range of language identified by the overall tag" - RFC 5646: Tags for Identifying Languages, section 2.1 [https://www.rfc-editor.org/rfc/rfc5646](https://www.rfc-editor.org/rfc/rfc5646)
5. "Its value must be a valid BCP 47 language tag, or the empty string" - HTML Standard, WHATWG: The lang and xml:lang attributes [https://html.spec.whatwg.org/multipage/dom.html#the-lang-and-xml:lang-attributes](https://html.spec.whatwg.org/multipage/dom.html#the-lang-and-xml:lang-attributes)
6. "text in Simplified Chinese, Traditional Chinese, Japanese, and Korean languages may share the same code point for an ideographic character, but speakers of these languages expect the glyphs used to vary in small details from language to language" - Why use the language attribute?, W3C Internationalization [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)
7. "some browsers automatically assign appropriate fonts according to the language of the content" - Why use the language attribute?, W3C Internationalization [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)
8. "The UA must therefore only automatically hyphenate text for which the content language is known and for which it has an appropriate hyphenation resource" - CSS Text Module Level 3, W3C [https://www.w3.org/TR/css-text-3/#hyphens-property](https://www.w3.org/TR/css-text-3/#hyphens-property)
9. "Screen readers can load the correct pronunciation rules" - Understanding Success Criterion 3.1.1: Language of Page, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/language-of-page.html](https://www.w3.org/WAI/WCAG22/Understanding/language-of-page.html)
10. "Authoring tools can adapt spelling and grammar checking based on the language of the content, or ignore content that is not in the language of the spelling checker" - Why use the language attribute?, W3C Internationalization [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)
11. "An identifier (such as a language tag) for a set of international preferences" - Internationalization Glossary, W3C: Locale [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
12. "Type: language Subtag: fr Description: French" - IANA Language Subtag Registry [https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry](https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry)
13. "ast (Asturian - no two-letter code exists for Asturian in the ISO lists)" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
14. "to create a tag fr-CA (French as used in Canada)" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
15. "az-Latn (Azerbaijani, written in Latin script - since Azerbaijani can also be written using the Arabic or Cyrillic script)" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
16. "zh-Hant-HK (Traditional Chinese as used in Hong Kong)" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
17. "Only one region subtag can appear in a language tag, and it must appear after the language subtag and any extlang and script subtags" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
18. "language tags are lower case, alphabetic region subtags are upper case, and script subtags begin with an initial capital. This is only a convention!" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
19. "The golden rule when creating language tags is to keep the tag as short as possible. Avoid region, script or other subtags except where they add useful distinguishing information" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
20. "now you can find all subtags in the IANA Language Subtag Registry" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
21. "These codes come from, and are kept up to date with, ISO 639 language codes" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
22. "If a two-letter ISO code is available, this will be the one in the registry. Otherwise the registry will contain one three-letter code" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
23. "When RFC 5646 was published, over 7,000 new ISO 639-3 three-letter codes were added to the Subtag Registry" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
24. "People had to bend something like zh-CN (meaning Chinese as spoken in China) to mean Simplified Chinese, even in Singapore" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
25. "The availability of zh-Hans and zh-Hant for Chinese written in Simplified and Traditional scripts should improve consistency and accuracy" - Language tags in HTML and XML, W3C Internationalization [https://www.w3.org/International/articles/language-tags/](https://www.w3.org/International/articles/language-tags/)
26. "The default human language of each web page can be programmatically determined" - Understanding Success Criterion 3.1.1: Language of Page, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/language-of-page.html](https://www.w3.org/WAI/WCAG22/Understanding/language-of-page.html)
27. "When the page contains content in another language, add a language attribute to an element surrounding that content" - Declaring language in HTML, W3C Internationalization [https://www.w3.org/International/questions/qa-html-language-declarations](https://www.w3.org/International/questions/qa-html-language-declarations)
28. "Type: language Subtag: ja Description: Japanese" - IANA Language Subtag Registry [https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry](https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry)
29. "Type: region Subtag: JP Description: Japan" - IANA Language Subtag Registry [https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry](https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry)
30. "It is simple to do when creating content, but more difficult to retrofit later" - Why use the language attribute?, W3C Internationalization [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)
