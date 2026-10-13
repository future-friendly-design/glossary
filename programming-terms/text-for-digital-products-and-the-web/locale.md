---
term: Locale
slug: locale
aliases: []
tags: [i18n-engineering]
level: intermediate
depth: core
summary: A locale is a named set of preferences for one language as it is used in one place, which software uses to decide how to show things such as dates, numbers and sorted lists.
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

A locale is a named set of preferences for one language as it is used in one place, which software uses to decide how to show things such as dates, numbers and sorted lists.<sup>1</sup>

The name is a short code such as `en-IN`, which means English as used in India. That code is a [language tag](language-tag.md). The two are easy to mix up, so hold on to this: the language tag is the label, and the locale is the set of preferences the label selects.

### Why it matters in design systems

Write the date `03/04/2026` and show it to two people. A reader in the United States sees March 4,<sup>2</sup> and a reader in the United Kingdom sees 3 April.<sup>3</sup>

Neither reader is wrong. Each is following the habit of the place they live in, and software that shows a date has to follow somebody's habit, because there is no neutral way to write one. The locale is how the software is told whose habits to follow.

Dates are only one of those habits. A locale also covers how numbers and money are written, which units of measurement are used, what order a list is sorted in, and what languages, countries and time zones are called in the reader's own language.<sup>4</sup> Sorting has its own entry, [collation](collation.md).

Here is one number, 123456.789, shown for three locales:

| Locale    | What the label means | How the number is shown    |
| --------- | -------------------- | -------------------------- |
| `de-DE`   | German, Germany      | `123.456,789`<sup>5</sup>  |
| `en-IN`   | English, India       | `1,23,456.789`<sup>6</sup> |
| `ar-EG`   | Arabic, Egypt        | `١٢٣٤٥٦٫٧٨٩`<sup>7</sup>   |

The German row swaps the jobs of the comma and the period. The Indian row groups the digits in twos after the first three. The Egyptian row uses a different set of digits. No word was translated in any of the three, and that is the first thing a locale teaches: adapting a product for a place, which is called [localization](localization.md), is a good deal more than translating it.

A locale carries more than a language. The two date readers at the top of this page share a language, and what differs between them is the place. The locale holds both. Sometimes even language and place together are not enough: German has one sort order for dictionaries and another for phone books, and a German reader may want either.<sup>8</sup> So think of a locale as a bundle of separate preferences that usually travel together, and not as a single fact about a person.

In everyday use the two words blur. The same short code that labels the language of a piece of text is also used to choose a locale, and most software treats the two kinds of code as one thing.<sup>9</sup> That works, as long as you remember that two different questions are hiding in it. "What language is this text in?" is a question about the content. "How does this reader expect a date to look?" is a question about the person.

The software does not invent these preferences. They are looked up in a shared public collection of each language's conventions, called [CLDR](cldr.md), which every modern operating system and browser includes.<sup>10</sup> The looking up is done by ready-made code that developers build into a product, and one widely used example is called [ICU](icu.md).<sup>11</sup>

A locale is also only a starting guess. People can usually override single items in it, choosing metric units or a different date style while keeping everything else.<sup>12</sup> And a guess made from the language a person's browser asks for can simply be wrong, which is why the advice is to let people change it and say what they want more exactly.<sup>13</sup>

For a design system, this changes what counts as content. A date, a number or a price is not fixed text in a component. It is a value that the software will format for each reader, and it can come out longer, shorter, in another order or in other digits, so the component has to leave room for all of those. Leaving them as values in the first place is part of [internationalization](internationalization.md), the work of preparing a product to hold any language. And where a product lets people choose, offer the language and the regional habits as separate choices, because a person can read one language and live by another place's calendar.

***

### Related terms and mentions

[CLDR](cldr.md) · [Collation](collation.md) · [ICU](icu.md) · [Internationalization](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Localization](localization.md) · [Text expansion](text-expansion.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Intl.Locale (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale)
* Foundations: [What is a Locale? (Unicode Technical Standard #35)](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)

### Sources

1. "a locale is an identifier (id) that refers to a set of user preferences that tend to be shared across significant swaths of the world" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
2. "US English uses month-day-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
3. "British English uses day-month-year order" - Intl.DateTimeFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
4. "the data associated with this id provides support for formatting and parsing of dates, times, numbers, and currencies; for measurement units, for sort-order (collation), plus translated names for time zones, languages, countries (regions), and scripts" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
5. "German uses comma as decimal separator and period for thousands" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
6. "India uses thousands/lakh/crore separators" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
7. "Arabic in most Arabic speaking countries uses real Arabic digits" - Intl.NumberFormat: Using locales (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
8. "a German language user might want to choose between the sort ordering used in a dictionary versus that used in a phone book" - Language Tags and Locale Identifiers for the World Wide Web, W3C Working Draft [https://www.w3.org/TR/ltli/](https://www.w3.org/TR/ltli/)
9. "in practice, language codes and locale codes are treated interchangeably" - Unicode Technical Standard #35, version 48.2: Unicode Language and Locale IDs [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Language_and_Locale_IDs)
10. "CLDR is incorporated into all modern operating systems and browsers" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
11. "Format numbers, dates, times and currency amounts according the conventions of a chosen locale" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
12. "preferences can typically set to override particular items, such as setting the date format for 2002.03.15, or using metric or Imperial measurement units" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
13. "using the Accept-Language value to infer regional settings may be a good starting point, but be sure to allow them to change the language as needed and specify their cultural settings more exactly if necessary" - Accept-Language used for locale setting, W3C Internationalization [https://www.w3.org/International/questions/qa-accept-lang-locales](https://www.w3.org/International/questions/qa-accept-lang-locales)
