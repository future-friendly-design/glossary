---
term: Localization (l10n)
slug: localization
aliases:
  - l10n
level: foundational
depth: core
summary: Localization is the work of adapting a product to one particular language and place.
related:
  - internationalization
  - locale
  - text-expansion
  - collation
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Localization (MDN)
    url: https://developer.mozilla.org/en-US/docs/Glossary/Localization
    type: code
  - title: Localization vs. Internationalization (W3C)
    url: https://www.w3.org/International/questions/qa-i18n
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Localization (l10n)

## Definition

Localization is the work of adapting a product to one particular language and place.<sup>1</sup>

It is often written "l10n", because there are 10 letters between the l and the n.<sup>2</sup> For example, the English word "views" under a photo is "consultations" in the French version of the same product.<sup>3</sup>

Localization is the second half of a pair. The first half is [internationalization](internationalization.md), the design and development work that makes a product able to be adapted at all. The two are done by different people at different times: designers and developers internationalize a product first, so that translators and localizers, the people who do the adapting, can then localize it.<sup>4</sup>

### Why it matters in design systems

Most people meet localization as a language menu. You choose another language, and the words change. That makes it look like translation, and translation is only one part of it.<sup>5</sup>

A language and a place come with habits that readers there expect a product to follow, and most of them are not words at all. Software has a name for one such set of language and regional preferences: a [locale](locale.md).<sup>6</sup> Here is some of what changes from one locale to the next:

| What changes | An example |
| ------------ | ---------- |
| How a date is written | The date 03/04/02 is read month first in the United States, day first in most of Europe, and year first in Japan<sup>7</sup> |
| The order of a sorted list (see [collation](collation.md)) | Swedish sorts ä as a letter of its own, after z. German sorts it with a<sup>8</sup> |
| The direction of the text | English is written left to right. Arabic and Hebrew are written right to left<sup>9</sup> |
| How a person's name is ordered | In the Chinese name Yao Ming, the family name, Yao, comes first<sup>10</sup> |
| Pictures and icons | An image or icon can be misread, or give offence, in another culture<sup>11</sup> |
| Money and typing | The currency changes, and so does the [keyboard layout](keyboard-layout.md), the arrangement of keys people type with<sup>12</sup> |

Nobody has to work these conventions out again for each product. Many of them are gathered in [CLDR](cldr.md), a shared collection of language and regional information that operating systems and programs read.<sup>13</sup> It is built by contributors, and a person can sign up to supply and check the information for their own language.<sup>14</sup> So a language community does not have to wait for a company to describe its conventions. It can describe them itself.

For a design system, localization is where earlier decisions are tested. A localizer can change the words. A localizer cannot make a button wider, turn a sentence around that was glued together from pieces, or move an icon to the other side of its label, because those things were fixed when the component was designed. How easy a product is to localize depends on the internationalization done before it.<sup>15</sup>

That gives designers two jobs here, even though they are not the ones translating. The first is to build components that can take what a localizer hands back: longer and shorter text (see [text expansion](text-expansion.md)), taller text, text in the other direction. The second is to hand over text that can be translated well. Keep each message whole, because when a sentence is split into pieces a translator may not be able to tell where a message begins and ends.<sup>16</sup>

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [CLDR](cldr.md) · [Collation](collation.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [Internationalization (i18n)](internationalization.md) · [Keyboard layout](keyboard-layout.md) · [Language](../../language-terms/linguistics/language.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Locale](locale.md) · [Pseudolocalization](pseudolocalization.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Text expansion](text-expansion.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Localization (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Localization)
* Foundations: [Localization vs. Internationalization (W3C)](https://www.w3.org/International/questions/qa-i18n)

### Sources

1. "Localization refers to the adaptation of a product, application or document content to meet the language, cultural and other requirements of a specific target market (a locale)" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
2. "Localization is sometimes abbreviated as l10n because there are ten letters between the "L" and the "N" in the English word" - Internationalization Glossary, W3C Group Note: Localization [https://www.w3.org/TR/i18n-glossary/#dfn-localisation](https://www.w3.org/TR/i18n-glossary/#dfn-localisation)
3. Table row "French consultations 2.6", in a table introduced as "comparative lengths of the word Flickr used for 'views' as a ratio" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
4. "Designers and developers internationalize products, so that they can be easily localized by translators and localizers" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
5. "Often thought of only as a synonym for translation of the user interface and documentation, localization is often a substantially more complex issue" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
6. "An identifier (such as a language tag) for a set of international preferences" - Internationalization Glossary, W3C Group Note: Locale [https://www.w3.org/TR/i18n-glossary/#dfn-locale](https://www.w3.org/TR/i18n-glossary/#dfn-locale)
7. "The format MM/DD/YY is unique to the United States (but sometimes used in Canada, too, which can obviously create some confusion there). Most of Europe uses DD/MM/YY. Japan uses YY/MM/DD" - Date formats, W3C Internationalization [https://www.w3.org/International/questions/qa-date-format](https://www.w3.org/International/questions/qa-date-format)
8. "Swedish treats ä as an individual letter, sorting it after z in the alphabet; German, however, sorts it either like ae or like other accented forms of a" - Unicode Technical Standard #10: Unicode Collation Algorithm, Version 18.0.0 [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
9. "English and Portuguese are written from left to right with new lines added below the previous ones. Hebrew and Arabic are right-to-left languages with new lines again being added below the previous ones" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
10. "Yao Ming (family name Yao, given name Ming)" - Personal names around the world, W3C Internationalization [https://www.w3.org/International/questions/qa-personal-names](https://www.w3.org/International/questions/qa-personal-names)
11. "Text and graphics containing references to objects, actions or ideas which, in a given culture, may be subject to misinterpretation or viewed as insensitive" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
12. Localization "can entail customization related to: Numeric, date and time formats Use of currency Keyboard layout and usage" (the first items of a bulleted list) - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
13. "supplies key information and structures critical for programs and operating systems around the world to ensure that they feel natural, no matter which language users speak or where they live" - Unicode CLDR Project [https://cldr.unicode.org/](https://cldr.unicode.org/)
14. "Contribute as an individual (vetter) for your language by setting up an account" - Unicode CLDR Project [https://cldr.unicode.org/](https://cldr.unicode.org/)
15. "Internationalization significantly affects the ease of the product's localization" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
16. "there is also a risk that the translator struggles to identify the beginning and end of such messages, especially if the strings are not supplied to the translator together and in order" - Working with Composite Messages, W3C Internationalization [https://www.w3.org/International/articles/composite-messages/](https://www.w3.org/International/articles/composite-messages/)
