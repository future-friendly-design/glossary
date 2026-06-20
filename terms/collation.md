---
term: Collation
slug: collation
aliases: [sort order, Unicode Collation Algorithm, UCA]
tags: [i18n-engineering]
level: intermediate
depth: deep
summary: Collation is the rules that determine the correct order for sorting and comparing text in a given language.
related: [locale, icu, cldr, localization]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Collator (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator
    type: code
  - title: "UTS #10: Unicode Collation Algorithm"
    url: https://unicode.org/reports/tr10/
    type: authority
license: CC-BY-4.0
---

## Definition
Collation is the rules that determine the correct order for sorting and comparing text in a given language.

## Why it matters
Sorting is not as simple as comparing character codes, because the "right" order is language-specific. The Unicode Collation Algorithm (UTS #10) handles this by assigning multi-level weights to characters and producing comparable sort keys. Languages genuinely disagree: Swedish sorts å, ä, ö after z, while German treats ä roughly like "ae", so there is no single correct order, only the correct order for a [locale](locale.md).

## Example
In a Swedish sort, "Åström" comes after "Zetterberg" because å is ordered at the end of the alphabet.

## Common mistake
Sorting strings by their raw code points (the default in most languages' built-in sort) and assuming it is correct. It puts "Z" before "a" (uppercase code points are lower), botches accented letters, and ignores language-specific order entirely. The result looks fine in an English smoke test and is wrong everywhere else.

## In practice
- **Use a locale-aware comparator:** in JavaScript, `Intl.Collator(locale).compare` (or `localeCompare`) sorts correctly per locale; server-side, lean on [icu](icu.md) rather than a naive string compare. See [Intl.Collator (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator).
- **Pick the locale deliberately:** the same list sorts differently in `sv` vs `de`, so sort by the user's locale, and keep database/collation settings consistent with the app's expectations.
- **Sort keys for performance:** when sorting large sets repeatedly, generate collation sort keys once instead of comparing pairwise every time.

## Related terms
[Locale](locale.md) · [ICU](icu.md) · [CLDR](cldr.md) · [Localization](localization.md)

## Further reading
- Code & specs: [Intl.Collator (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator)
- Foundations: [UTS #10: Unicode Collation Algorithm](https://unicode.org/reports/tr10/)
