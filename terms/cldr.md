---
term: CLDR
slug: cldr
aliases: [Common Locale Data Repository, Unicode CLDR]
tags: [i18n-engineering]
level: advanced
depth: core
summary: CLDR is Unicode's shared database of locale data, such as how each language formats dates, numbers, and currencies.
related: [icu, locale, collation, internationalization]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode CLDR Project"
    url: https://cldr.unicode.org/
    type: authority
license: CC-BY-4.0
---

## Definition
CLDR is Unicode's shared database of locale data, such as how each language formats dates, numbers, and currencies.

## Why it matters
The Common Locale Data Repository is the largest standard repository of [locale](locale.md) data, covering well over 100 languages, and it is what lets software behave naturally wherever users live. It supplies date, time, number, and currency formats, translated names for languages and regions, sorting rules, and measurement preferences. It underpins libraries like [icu](icu.md) as well as modern operating systems and browsers, so when an app formats a date "the local way," CLDR is usually the source of that knowledge.

## Example
CLDR records that en-US uses "M/D/YYYY" while much of Europe uses "DD/MM/YYYY", so apps can format dates correctly per locale.

## Related terms
[icu](icu.md) · [locale](locale.md) · [collation](collation.md) · [internationalization](internationalization.md)

## Further reading
- Foundations: [Unicode CLDR Project](https://cldr.unicode.org/)
