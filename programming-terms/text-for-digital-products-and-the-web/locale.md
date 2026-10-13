---
term: Locale
slug: locale
aliases: []
tags: [i18n-engineering]
level: intermediate
depth: core
summary: A locale is a short code that names a set of preferences, usually those of one language as it is used in one place, so that software can show things such as dates, numbers and sorted lists the way a reader expects.
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

A locale is a short code that names a set of preferences, usually those of one language as it is used in one place, so that software can show things such as dates, numbers and sorted lists the way a reader expects.<sup>1</sup>

The code looks like `en-IN`, which stands for English as used in India. A code of this kind is also called a [language tag](language-tag.md).<sup>2</sup> The two are easy to mix up, so remember this: as a language tag, the code says what language a piece of text is in, and as a locale, it says whose habits the software should follow.

People also use the word "locale" for the preferences themselves. That is a shorthand. Strictly, the locale is the code, and the preferences are what it points to.<sup>3</sup>

### Why it matters in design systems

Write the date `03/04/2026` and show it to two people. A reader in the United States sees March 4,<sup>4</sup> and a reader in the United Kingdom sees 3 April.<sup>5</sup>

Neither reader is wrong. Each is following the habit of the place they live in, and software that shows a date has to follow somebody's habit. The locale is how the software is told whose habits to follow.

Dates are only one of those habits. A locale also covers how numbers and money are written, which units of measurement are used, what order a list is sorted in, and what languages, countries and time zones are called in the reader's own language.<sup>6</sup> Sorting has its own entry, [collation](collation.md).

Here is one number, 123456.789, shown for three locales:

| Locale    | What the code means  | How the number is shown    |
| --------- | -------------------- | -------------------------- |
| `de-DE`   | German, Germany      | `123.456,789`<sup>7</sup>  |
| `en-IN`   | English, India       | `1,23,456.789`<sup>8</sup> |
| `ar-EG`   | Arabic, Egypt        | `١٢٣٬٤٥٦٫٧٨٩`<sup>9</sup>  |

<!-- The three outputs were produced with Intl.NumberFormat (Node 26.9, ICU 78.3, CLDR 48) on 2026-10-13. The ar-EG string includes U+066C ARABIC THOUSANDS SEPARATOR; the comment on the MDN page still shows an older output without it. -->

The German row uses a period to group the digits and a comma before the decimals. The Indian row uses the comma and the period the other way round, keeps the last three digits together, and groups the rest in twos. The Egyptian row uses the digits of the Arabic script, with separators of their own. No word was translated in any of the three, and that is the first thing a locale teaches: adapting a product for a place, which is called [localization](localization.md), is a good deal more than translating it.

A locale stands for more than a language. The two date readers at the top of this page share a language, and what differs between them is the place. The locale covers both. Sometimes even language and place together are not enough: German has one sort order for dictionaries and another for phone books, and a German reader may want either.<sup>10</sup> So think of a locale as pointing to a bundle of separate preferences that usually travel together, and not to a single fact about a person.

In everyday use the two words blur. The same short code that labels the language of a piece of text is also used to choose a locale, and most software treats the two kinds of code as one thing.<sup>11</sup> That works, as long as you remember that two different questions are hiding in it. "What language is this text in?" is a question about the content. "How does this reader expect a date to look?" is a question about the person.

The software does not invent these preferences. They are looked up in a shared public collection of each language's conventions, called [CLDR](cldr.md), which every modern operating system and browser includes.<sup>12</sup> The looking up is done by ready-made code that developers build into a product, and one widely used example is called [ICU](icu.md).<sup>13</sup>

A locale is also only a starting guess. People can usually override single items in it, choosing metric units or a different date style while keeping everything else.<sup>14</sup> And a guess made from the language a person's browser asks for can simply be wrong, which is why the advice is to let people change it and say what they want more exactly.<sup>15</sup>

For a design system, this changes what counts as content. A date, a number or a price is not fixed text in a component. It is a value that the software will format for each reader, and it can come out longer, shorter, in another order or in other digits, so the component has to leave room for all of those. Leaving them as values in the first place is part of [internationalization](internationalization.md), the work of preparing a product to hold any language. And where a product lets people choose, offer the language and the regional habits as separate choices, because a person can read one language and live by another place's calendar.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [CLDR](cldr.md) · [Collation](collation.md) · [ICU](icu.md) · [Internationalization](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Localization](localization.md) · [Text expansion](text-expansion.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Intl.Locale (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale)
* Foundations: [What is a Locale? (Unicode Technical Standard #35)](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)

### Sources

1. "a locale is an identifier (id) that refers to a set of user preferences that tend to be shared across significant swaths of the world" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
2. "An identifier (such as a language tag) for a set of international preferences" - Internationalization Glossary, W3C Group Note: Locale [https://www.w3.org/TR/i18n-glossary/#dfn-locale](https://www.w3.org/TR/i18n-glossary/#dfn-locale)
3. "That does not imply that a locale is a collection of data; it is simply shorthand for "the set of data associated with the locale id X"" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
4. "US English uses month-day-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
5. "British English uses day-month-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
6. "the data associated with this id provides support for formatting and parsing of dates, times, numbers, and currencies; for measurement units, for sort-order (collation), plus translated names for time zones, languages, countries (regions), and scripts" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
7. "German uses comma as decimal separator and period for thousands" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
8. "India uses thousands/lakh/crore separators" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
9. "Arabic in most Arabic speaking countries uses real Arabic digits" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
10. "a German language user might want to choose between the sort ordering used in a dictionary versus that used in a phone book" - Language Tags and Locale Identifiers for the World Wide Web, W3C Working Draft [https://www.w3.org/TR/ltli/](https://www.w3.org/TR/ltli/)
11. "in practice, language codes and locale codes are treated interchangeably" - Unicode Technical Standard #35, version 48.2: Unicode Language and Locale IDs [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs)
12. "CLDR is incorporated into all modern operating systems and browsers" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
13. "Format numbers, dates, times and currency amounts according the conventions of a chosen locale" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
14. "preferences can typically set to override particular items, such as setting the date format for 2002.03.15, or using metric or Imperial measurement units" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
15. "using the Accept-Language value to infer regional settings may be a good starting point, but be sure to allow them to change the language as needed and specify their cultural settings more exactly if necessary" - Accept-Language used for locale setting, W3C Internationalization [https://www.w3.org/International/questions/qa-accept-lang-locales](https://www.w3.org/International/questions/qa-accept-lang-locales)
