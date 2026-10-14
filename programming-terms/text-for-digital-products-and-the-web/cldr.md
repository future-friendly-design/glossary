---
term: CLDR
slug: cldr
aliases: [Common Locale Data Repository, "Common Locale Data & Rules", Unicode CLDR]
tags: [i18n-engineering]
level: advanced
depth: core
summary: CLDR is a shared public collection of data that records how each language writes things such as dates, numbers and sorted lists in each place it is used, so that software can look those conventions up instead of every product working them out.
related: [icu, locale, collation, internationalization]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode CLDR Project"
    url: https://cldr.unicode.org/
    type: authority
license: CC-BY-4.0
---

# CLDR

## Definition

CLDR is a shared public collection of data that records how each language writes things such as dates, numbers and sorted lists in each place it is used, so that software can look those conventions up instead of every product working them out.<sup>1</sup>

CLDR is one of the tools of [internationalization (i18n)](internationalization.md), the design and development work that makes a product able to be adapted to other languages and places.<sup>2</sup>

The letters stand for Common Locale Data Repository in the project's specification,<sup>3</sup> and for Common Locale Data & Rules on the project's own site.<sup>4</sup> A [locale](locale.md) is a short code, such as `en-US` for English as used in the United States, that names a language and a specific location.

CLDR sits beside [Unicode](../text-in-software/unicode.md), the standard that gives every [character](../text-in-software/character.md) a number. Unicode covers the characters themselves, and CLDR covers the languages that use them and how each language differs from one place to another.<sup>5</sup>

<!-- NEEDS EXPERT REVIEW: the expansion of the name is in transition. cldr.unicode.org (fetched 2026-10-13) says "Common Locale Data & Rules" and titles the specification "UTS #35: Unicode Common Locale Data & Rules (CLDR)"; the released UTS #35 v48.2 and the proposed v49 draft (tr35-79, 2026-09-24) both still say "Common Locale Data Repository", as do icu.unicode.org and the W3C Internationalization Glossary. Re-check when CLDR 49 is released. -->

### Why it matters in design systems

Look at a list of files on a phone. Each file has a date beside it, a size, and a place in alphabetical order.<sup>6</sup> Change the phone's language and all three change. The people who built the file list probably worked out none of it themselves, because all three are usually supplied by CLDR.<sup>7</sup>

There are far too many of these conventions for one product team to collect, and they are easy to get wrong for a language nobody on the team reads. So the collecting is done once, in public, and every product shares the result.

Counting shows how much there is to get wrong. English has two forms for a counted thing, "1 day" and "2 days", and a team that only knows English tends to build exactly that into a product. CLDR records how many forms each language needs:

| Language | Forms recorded for counting things |
| -------- | ---------------------------------- |
| Japanese | One form, used for every number<sup>8</sup> |
| English  | Two forms: one for 1, and one for everything else<sup>9</sup> |
| Arabic   | Six forms, which CLDR labels zero, one, two, few, many and other<sup>10</sup> |

A label such as "3 items" is therefore not a number with a fixed word after it. In Arabic the word after the number can take six forms, and software that only knows about two will pick the wrong one.

Plural forms are one kind of entry among many. CLDR also holds how each language writes dates, numbers, money and units of measurement,<sup>11</sup> and the order in which it sorts a list.<sup>12</sup> This glossary covers sorting under [collation](collation.md).

CLDR is data, and data does nothing by itself. Software has to read it and apply it. One widely used piece of software that does so is [ICU](icu.md), a collection of ready-made code that developers build into their products. The pair is easy to confuse. CLDR is the record of the conventions, and ICU is software that uses the record. The usual path is a chain. An app asks the operating system to format a date, the operating system calls ICU, and ICU reads CLDR.<sup>13</sup> That is why most developers use CLDR without ever opening it.<sup>14</sup>

The data is written by people. Speakers of each language enter and check it through a website called the Survey Tool.<sup>15</sup> The tool is usually open once a year.<sup>16</sup> Members of the public are invited to take part, and that includes proposing data for a language that is not in CLDR yet.<sup>17</sup> Anyone can look at the data for a language without an account, and an account is needed only to propose a change.<sup>18</sup> A native speaker of a language other than American English who does not belong to a member organization can get a guest account.<sup>19</sup>

For a language community this is one of the most direct routes into everyday software. A convention entered once in CLDR can reach every product that reads it. A language that is not there yet gets none of this for free, and each product has to supply the formats itself or go without.

<!-- NEEDS EXPERT REVIEW: the last sentence above is an inference from how CLDR is used, not a statement read in a primary source. Confirm the wording with someone who has shipped a product in a language absent from CLDR. -->

For design work, two habits follow. When a date, a number or a plural looks wrong in one language, the fault may not be in your product at all. Check which locale the software was given, then check the data, because an error in CLDR can be reported and fixed for everyone.<sup>20</sup> And do not treat a formatted date or number as fixed text in a design or a test. The data is revised on a regular schedule, with two rounds a year,<sup>21</sup> so the exact output can change underneath a product that has not changed at all.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Collation](collation.md) · [ICU](icu.md) · [Internationalization (i18n)](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Locale](locale.md) · [Localization (l10n)](localization.md) · [Unicode](../text-in-software/unicode.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Foundations: [Unicode CLDR Project](https://cldr.unicode.org/)

### Sources

1. "Formatting dates, numbers, currencies, and units of measurement is far more complicated across different languages and regions than most people recognize. Part of the goal of CLDR is to provide the foundation for APIs that handle that complexity without developers needing to know about 100+ languages" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
2. "Typically this involves incorporating predefined localization data and features derived from existing libraries or user preferences" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
3. "This format is used in the Unicode Common Locale Data Repository" - Unicode Technical Standard #35, version 48.2: Summary [https://www.unicode.org/reports/tr35/tr35-78/tr35.html](https://www.unicode.org/reports/tr35/tr35-78/tr35.html)
4. "CLDR (Common Locale Data & Rules)" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
5. "Just as Unicode has standards for handling characters, writing systems, and their properties, CLDR is focused on languages and their regional variations (collectively referred to as locales)" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
6. "You’ll see the format of the dates (like the creation date), numbers, units (like the size of the file), and the alphabetical order of the files" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
7. "all of these are usually supplied by CLDR" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
8. The Japanese row lists a single cardinal category, "other", and no others - Language Plural Rules, CLDR 48 charts [https://www.unicode.org/cldr/charts/48/supplemental/language_plural_rules.html](https://www.unicode.org/cldr/charts/48/supplemental/language_plural_rules.html)
9. "Some languages have two forms, like English; some languages have only a single form; and some languages have multiple forms" - Plural Rules, Unicode CLDR Project [https://cldr.unicode.org/index/cldr-spec/plural-rules](https://cldr.unicode.org/index/cldr-spec/plural-rules)
10. The Arabic row lists six cardinal categories: "zero", "one", "two", "few", "many" and "other" - Language Plural Rules, CLDR 48 charts [https://www.unicode.org/cldr/charts/48/supplemental/language_plural_rules.html](https://www.unicode.org/cldr/charts/48/supplemental/language_plural_rules.html)
11. "the data associated with this id provides support for formatting and parsing of dates, times, numbers, and currencies; for measurement units" - Unicode Technical Standard #35, version 48.2: What is a Locale? [https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale](https://www.unicode.org/reports/tr35/tr35-78/tr35.html#Locale)
12. "it also describes how plurals work in various languages and variations in how lists are alphabetized" - Unicode CLDR Project: What is CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
13. "an application uses an operating system service (eg, to format a date), which calls an ICU library (Unicode’s production code for C, C++, Java, and Rust), which then uses CLDR" - Unicode CLDR Project: Who uses CLDR? [https://cldr.unicode.org/](https://cldr.unicode.org/)
14. "Most developers will use CLDR indirectly, via a set of software libraries" - Unicode CLDR Project: How to Use? [https://cldr.unicode.org/](https://cldr.unicode.org/)
15. "gathered and processed via what is called the Survey Tool, an online tool that can be used to view data for different languages and propose additions or changes" - CLDR Survey Tool, Unicode CLDR Project [https://cldr.unicode.org/index/survey-tool](https://cldr.unicode.org/index/survey-tool)
16. "The Survey Tool is usually open once a year to gather data for new structure, and make corrections in previously-released data" - Unicode CLDR Project: How to Contribute? [https://cldr.unicode.org/](https://cldr.unicode.org/)
17. "contributors from Unicode Consortium members, other organizations and the public at large are invited to review the data for their languages and countries, and propose new translations of terms or modifications, including language translations entirely new to the repository" - CLDR Survey Tool, Unicode CLDR Project [https://cldr.unicode.org/index/survey-tool](https://cldr.unicode.org/index/survey-tool)
18. "You don’t need an account to view data for a particular language. If you wish to propose changes or additions, you will need an account" - CLDR Survey Tool, Unicode CLDR Project [https://cldr.unicode.org/index/survey-tool](https://cldr.unicode.org/index/survey-tool)
19. "If you don’t belong to a Unicode member organization, and are a native speaker of a language other than American English, you can obtain a guest account" - Survey Tool Accounts, Unicode CLDR Project [https://cldr.unicode.org/index/survey-tool/survey-tool-accounts](https://cldr.unicode.org/index/survey-tool/survey-tool-accounts)
20. "People may file tickets with bug fixes or feature requests" - Unicode CLDR Project: How to Contribute? [https://cldr.unicode.org/](https://cldr.unicode.org/)
21. "CLDR has a regular schedule, with two cycles per year" - Unicode CLDR Project: What is the Schedule? [https://cldr.unicode.org/](https://cldr.unicode.org/)
