---
term: ICU
slug: icu
aliases: [International Components for Unicode, ICU4C, ICU4J]
tags: [i18n-engineering]
level: advanced
depth: core
summary: ICU is a widely used software library that provides ready-made tools for Unicode handling and internationalization.
related: [cldr, collation, segmentation, locale]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "ICU: International Components for Unicode"
    url: https://icu.unicode.org/
    type: authority
license: CC-BY-4.0
---

## Definition
ICU is a widely used software library that provides ready-made tools for Unicode handling and internationalization.

## Why it matters
International Components for Unicode gives developers reusable services for formatting dates, numbers, and currencies, sorting text ([collation](collation.md)), segmenting text ([segmentation](segmentation.md)), and converting between encodings, so they do not have to reimplement these per language. It is maintained as a technical committee of the Unicode Consortium and draws its locale data from [cldr](cldr.md). Because ICU is built into many operating systems, browsers, and programming languages, a lot of the i18n behavior you rely on is ICU underneath.

## Example
Java's and .NET's date and number formatting are backed by ICU and CLDR data.

## Related terms
[cldr](cldr.md) · [collation](collation.md) · [segmentation](segmentation.md) · [locale](locale.md)

## Further reading
- Foundations: [ICU: International Components for Unicode](https://icu.unicode.org/)
