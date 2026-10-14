---
term: ICU
slug: icu
aliases:
  - International Components for Unicode
  - ICU4C
  - ICU4J
level: advanced
depth: core
summary: ICU is a widely used collection of ready-made code that products reuse to handle text and local conventions in many languages, such as formatting a date or sorting a list.
related:
  - cldr
  - collation
  - segmentation
  - locale
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: "Formatting Messages (ICU User Guide)"
    url: https://unicode-org.github.io/icu/userguide/format_parse/messages/
    type: code
  - title: "ICU: International Components for Unicode"
    url: https://icu.unicode.org/
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# ICU

## Definition

ICU is a widely used collection of ready-made code that products reuse to handle text and local conventions in many languages, such as formatting a date or sorting a list.<sup>1</sup>

ICU is one of the tools of [internationalization (i18n)](internationalization.md), the design and development work that makes a product able to be adapted to other languages and places.<sup>2</sup>

The name ICU stands for International Components for Unicode.<sup>3</sup> [Unicode](../text-in-software/unicode.md) is the standard that gives every character a number. ICU carries the Unicode name too: one of Unicode's own websites calls it Unicode's production code for four programming languages, C, C++, Java and Rust.<sup>4</sup> Developers call a collection of reusable code like this one a library.

### Why it matters in design systems

Your phone shows today's date the way you expect it, in most apps, including apps made by people who have never seen your language. Those people did not study how your language writes a date. Their code asked for "this date, for this reader", and something else handed back the finished text. Often that something is ICU.

The reader is described by a [locale](locale.md), a short code that names the preferences of one language as it is used in one place. Give ICU a value and a locale, and it does jobs like these:

| Job | What ICU does |
| --- | ------------- |
| Formatting | Writes a number, a date, a time or an amount of money the way the locale expects, including the names of months and days in that language.<sup>5</sup> |
| Sorting | Compares two pieces of text by the conventions of a language or a region, so that a list comes out in the order its readers expect.<sup>6</sup> This is called [collation](collation.md). |
| Calendars | Works with calendars other than the Gregorian one, the calendar of twelve months that runs from January to December.<sup>7</sup> |
| Finding boundaries | Finds where words and sentences begin and end, and where a line of text may be broken.<sup>8</sup> This is called [segmentation](../text-in-software/segmentation.md). |

ICU is the code. The conventions it follows when it sorts and formats come from somewhere else: a shared public collection of each language's conventions called [CLDR](cldr.md). ICU's sorting uses the rules recorded there,<sup>9</sup> and so does its formatting.<sup>10</sup> The two names are often used together, so keep them apart like this: CLDR is the data, and ICU is software that uses the data. A wrong month name is a data question. A product that ignores the reader's locale altogether is a code question.

Most products reach ICU indirectly. An app asks the operating system to format a date, the operating system calls ICU, and ICU reads CLDR.<sup>11</sup> ICU is also not the only code that reads CLDR, since other programming languages have libraries of their own that do the same job.<sup>12</sup> Web pages get a similar set of services from the browser, covering comparing text, formatting numbers, and formatting dates and times.<sup>13</sup>

The place a designer or a writer is most likely to meet ICU by name is in the text sent to translators. ICU has a way of writing one message that holds several versions of a sentence, and the software picks a version by a number, following the plural rules of the language.<sup>14</sup> One message can hold both `{host} invites {guest} to her party.` and `{host} invites {guest} and # other people to her party.`<sup>15</sup> The words in curly brackets and the `#` are slots, filled in when the message is shown.

This is where ICU reaches into design. A message has to be written and translated as one whole unit, because translators move the slots around to suit the grammar of their language.<sup>16</sup> A component that builds a sentence out of separate pieces, a number here and a fixed word there, takes that freedom away, and the result reads wrongly in languages whose word order or plural forms differ from the one it was designed in. So design text components to hold whole sentences with slots in them, and write each version of the sentence out in full.<sup>17</sup>

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [CLDR](cldr.md) · [Collation](collation.md) · [Internationalization (i18n)](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Locale](locale.md) · [Localization (l10n)](localization.md) · [Segmentation](../text-in-software/segmentation.md) · [Unicode](../text-in-software/unicode.md) · [Internationalization & localization terms](../internationalization-and-localization/)

### Further reading

* Code & specs: [Formatting Messages (ICU User Guide)](https://unicode-org.github.io/icu/userguide/format_parse/messages/)
* Foundations: [ICU: International Components for Unicode](https://icu.unicode.org/)

### Sources

1. "ICU is a mature, widely used set of C/C++ and Java libraries providing Unicode and Globalization support for software applications" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
2. "The software internationalization development process uses libraries (such as the International Components for Unicode (ICU) libraries)" - Introduction to ICU, ICU User Guide [https://unicode-org.github.io/icu/userguide/icu/](https://unicode-org.github.io/icu/userguide/icu/)
3. Page title "ICU - International Components for Unicode" - ICU: International Components for Unicode [https://icu.unicode.org/](https://icu.unicode.org/)
4. "Unicode’s production code for C, C++, Java, and Rust" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
5. "Format numbers, dates, times and currency amounts according the conventions of a chosen locale. This includes translating month and day names into the selected language" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
6. "Compare strings according to the conventions and standards of a particular language, region or country" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
7. "Multiple types of calendars are provided beyond the traditional Gregorian calendar" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
8. "Locate the positions of words, sentences, paragraphs within a range of text, or identify locations that would be suitable for line wrapping when displaying the text" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
9. "ICU's collation is based on the Unicode Collation Algorithm plus locale-specific comparison rules from the Common Locale Data Repository" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
10. "This data also comes from the Common Locale Data Repository" - ICU: International Components for Unicode, What is ICU? [https://icu.unicode.org/](https://icu.unicode.org/)
11. "an application uses an operating system service (eg, to format a date), which calls an ICU library (Unicode’s production code for C, C++, Java, and Rust), which then uses CLDR" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
12. "There are other libraries for other programming languages, such as Babel (Python), TwitterCLDR (Ruby), and Unicode::CLDR (Perl)" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
13. "the ECMAScript Internationalization API, which provides language sensitive string comparison, number formatting, date and time formatting, and more" - Intl (MDN) [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl)
14. "Use a "plural" argument to select sub-messages based on a numeric value, together with the plural rules for the specified language" - Formatting Messages, ICU User Guide [https://unicode-org.github.io/icu/userguide/format_parse/messages/](https://unicode-org.github.io/icu/userguide/format_parse/messages/)
15. "=1 {{host} invites {guest} to her party.}" and "other {{host} invites {guest} and # other people to her party.}" - Formatting Messages, ICU User Guide [https://unicode-org.github.io/icu/userguide/format_parse/messages/](https://unicode-org.github.io/icu/userguide/format_parse/messages/)
16. "a message has to be written and translated as a single unit, typically a string with placeholder syntax for the variable elements" - Formatting Messages, ICU User Guide [https://unicode-org.github.io/icu/userguide/format_parse/messages/](https://unicode-org.github.io/icu/userguide/format_parse/messages/)
17. "use complex arguments as the outermost structure of a message, and write full sentences in their sub-messages" - Formatting Messages, ICU User Guide [https://unicode-org.github.io/icu/userguide/format_parse/messages/](https://unicode-org.github.io/icu/userguide/format_parse/messages/)
