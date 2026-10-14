---
term: Locale
slug: locale
aliases: []
tags: [i18n-engineering]
level: intermediate
depth: core
summary: A locale is a short code that names a language and a specific location, so that software can look up the conventions used there for writing things such as dates, numbers and sorted lists.
related: [internationalization, localization, collation, text-expansion]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Locale (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale
    type: code
  - title: "What is a Locale? (Unicode Technical Standard #35)"
    url: https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale
    type: authority
license: CC-BY-4.0
---

# Locale

## Definition

A locale is a short code that names a language and a specific location, so that software can look up the conventions used there for writing things such as dates, numbers and sorted lists.<sup>1</sup>

Locales are one of the tools of [internationalization (i18n)](internationalization.md), the design and development work that makes a product able to be adapted to other languages and places.<sup>2</sup>

For example, in the code `en-US`, the first part, `en`, means the English [language](../../language-terms/linguistics/language.md), and the last part, `US`, means the United States as the specific location. This matters because English is written with different conventions in different locations. In United States English (`en-US`), a date is written with the month first.<sup>3</sup> In United Kingdom English (`en-GB`), it is written with the day first.<sup>4</sup> Canadian English (`en-CA`) is a third locale, with conventions of its own.

The same kind of code has a second job. Put on a piece of text, it says what language the text is in, and it is then called a [language tag](language-tag.md).<sup>5</sup> Used as a locale, it says what the reader expects. For example, `fr-CA` on a paragraph says the paragraph is in French as it is used in Canada. As a reader's locale, the same code says the reader expects dates and numbers written the way they are in Canada. People also say "locale" for those conventions themselves, not only for the code that names them.<sup>6</sup>

### Why it matters in design systems

Write the date `03/04/2026` and show it to two people. A reader in the United States sees March 4,<sup>7</sup> and a reader in the United Kingdom sees 3 April.<sup>8</sup>

Neither reader is wrong. Each is following the habit of the place they live in, and software that shows a date has to follow somebody's habit. The locale is how the software is told whose habits to follow.

Dates are only one of those habits. A locale also covers how numbers and money are written, which units of measurement are used, what order a list is sorted in, and what languages, countries and time zones are called in the reader's own language.<sup>9</sup> Sorting has its own entry, [collation](collation.md).

Here is one number, 123456.789, shown for three locales:

| Locale    | What the code means  | How the number is shown    |
| --------- | -------------------- | -------------------------- |
| `de-DE`   | German, Germany      | `123.456,789`<sup>10</sup>  |
| `en-IN`   | English, India       | `1,23,456.789`<sup>11</sup> |
| `ar-EG`   | Arabic, Egypt        | `١٢٣٬٤٥٦٫٧٨٩`<sup>12</sup>  |

<!-- The three outputs were produced with Intl.NumberFormat (Node 26.9, ICU 78.3, CLDR 48) on 2026-10-13. The ar-EG string includes U+066C ARABIC THOUSANDS SEPARATOR; the comment on the MDN page still shows an older output without it. -->

The German row uses a period to group the digits and a comma before the decimals. The Indian row uses the comma and the period the other way round, keeps the last three digits together, and groups the rest in twos. The Egyptian row uses the digits of the [Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md), with separators of their own. No word was translated in any of the three, and that is the first thing a locale teaches: adapting a product for a place, which is called [localization](localization.md), is a good deal more than translating it.

A locale stands for more than a language. The two date readers at the top of this page share a language, and what differs between them is the place. The locale covers both. Sometimes even language and place together are not enough: German has one sort order for dictionaries and another for phone books, and a German reader may want either.<sup>13</sup> So think of a locale as pointing to a bundle of separate preferences that usually travel together, and not to a single fact about a person.

In everyday use the two words blur. The same short code that labels the language of a piece of text is also used to choose a locale, and most software treats the two kinds of code as one thing.<sup>14</sup> That works, as long as you remember that two different questions are hiding in it. "What language is this text in?" is a question about the content. "How does this reader expect a date to look?" is a question about the person.

The software does not invent these preferences. They are looked up in a shared public collection of each language's conventions, called [CLDR](cldr.md), which every modern operating system and browser includes.<sup>15</sup> The looking up is done by ready-made code that developers build into a product, and one widely used example is called [ICU](icu.md).<sup>16</sup>

A locale is also only a starting guess. People can usually override single items in it, choosing metric units or a different date style while keeping everything else.<sup>17</sup> And a guess made from the language a person's browser asks for can simply be wrong, which is why the advice is to let people change it and say what they want more exactly.<sup>18</sup>

For a design system, this changes what counts as content. A date, a number or a price is not fixed text in a component. It is a value that the software will format for each reader, and it can come out longer, shorter, in another order or in other digits, so the component has to leave room for all of those. Leaving them as values in the first place is part of internationalization, the work of preparing a product to hold any language. And where a product lets people choose, offer the language and the regional habits as separate choices, because a person can read one language and live by another place's calendar.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [CLDR](cldr.md) · [Collation](collation.md) · [ICU](icu.md) · [Internationalization (i18n)](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Localization (l10n)](localization.md) · [Text expansion](text-expansion.md) · [Unicode](../text-in-software/unicode.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Intl.Locale (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale)
* Foundations: [What is a Locale? (Unicode Technical Standard #35)](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)

### Sources

1. "a locale is an identifier (id) that refers to a set of user preferences that tend to be shared across significant swaths of the world" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
2. "Enabling code to support local, regional, language, or culturally related preferences" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
3. "US English uses month-day-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
4. "British English uses day-month-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
5. "An identifier (such as a language tag) for a set of international preferences" - Internationalization Glossary, W3C Group Note: Locale [https://www.w3.org/TR/i18n-glossary/#dfn-locale](https://www.w3.org/TR/i18n-glossary/#dfn-locale)
6. "That does not imply that a locale is a collection of data; it is simply shorthand for "the set of data associated with the locale id X"" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
7. The `en-US` example on the page formats 19 December 2012 as "12/19/2012" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
8. The `en-GB` example on the page formats the same date as "19/12/2012" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
9. "the data associated with this id provides support for formatting and parsing of dates, times, numbers, and currencies; for measurement units, for sort-order (collation), plus translated names for time zones, languages, countries (regions), and scripts" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
10. "German uses comma as decimal separator and period for thousands" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
11. "India uses thousands/lakh/crore separators" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
12. "Arabic in most Arabic speaking countries uses real Arabic digits" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
13. "a German language user might want to choose between the sort ordering used in a dictionary versus that used in a phone book" - Language Tags and Locale Identifiers for the World Wide Web, W3C Working Draft [https://www.w3.org/TR/ltli/](https://www.w3.org/TR/ltli/)
14. "in practice, language codes and locale codes are treated interchangeably" - Unicode Technical Standard #35, version 48.2: Unicode Language and Locale IDs [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs)
15. "CLDR is incorporated into all modern operating systems and browsers" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
16. "Format numbers, dates, times and currency amounts according the conventions of a chosen locale" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
17. "preferences can typically set to override particular items, such as setting the date format for 2002.03.15, or using metric or Imperial measurement units" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
18. "using the Accept-Language value to infer regional settings may be a good starting point, but be sure to allow them to change the language as needed and specify their cultural settings more exactly if necessary" - Accept-Language used for locale setting, W3C Internationalization [https://www.w3.org/International/questions/qa-accept-lang-locales](https://www.w3.org/International/questions/qa-accept-lang-locales)
