---
term: Locale
slug: locale
aliases: []
tags: [i18n-engineering]
level: intermediate
depth: core
summary: A locale is a set of regional preferences (language plus country and conventions) that software uses to format text correctly.
related: [internationalization, localization, collation, text-expansion]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Locale (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale
    type: code
  - title: "Language tags in HTML and XML (W3C)"
    url: https://www.w3.org/International/articles/language-tags/
    type: authority
license: CC-BY-4.0
---

## Definition
A locale is a set of regional preferences (language plus country and conventions) that software uses to format text correctly.

## Why it matters
A locale governs far more than translation: casing, sorting order ([collation](collation.md)), number and date formats, currency, and quotation marks all depend on it. The same language can have several locales, so a locale is usually a language tag like `pt-BR` or `pt-PT`, not just a language. Choosing and threading the right locale through formatting and sorting is the mechanism that makes [localization](localization.md) actually work at runtime.

## Example
`en-US` shows 6/17/2026 while `en-GB` shows 17/06/2026.

## Related terms
[Internationalization](internationalization.md) · [Localization](localization.md) · [Collation](collation.md) · [Text expansion](text-expansion.md)

## Further reading
- Code & specs: [Intl.Locale (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale)
- Foundations: [Language tags in HTML and XML (W3C)](https://www.w3.org/International/articles/language-tags/)
