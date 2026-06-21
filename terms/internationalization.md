---
term: Internationalization
slug: internationalization
aliases: [i18n]
tags: [i18n-engineering]
level: foundational
depth: deep
summary: Internationalization is designing and building software so it can be adapted to different languages and regions without re-engineering it later.
related: [localization, locale, text-expansion, pseudolocalization]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Internationalization (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Glossary/Internationalization
    type: code
  - title: "Localization vs. Internationalization (W3C)"
    url: https://www.w3.org/International/questions/qa-i18n
    type: authority
license: CC-BY-4.0
---

# Internationalization

## Definition
Internationalization is designing and building software so it can be adapted to different languages and regions without re-engineering it later.

## Why it matters
Often abbreviated "i18n" (18 letters between the i and the n), internationalization is the up-front work that makes [localization](localization.md) possible at all. It covers separating translatable text from code, supporting Unicode, allowing for variable text length, and never hard-coding date, number, or currency formats. It happens before any translation, and skipping it is what turns "just add another language" into a rebuild.

## Example
Storing UI strings in an external file instead of writing "Submit" directly in the button code.

## Common mistake
Treating internationalization as translation, or as something to bolt on later. It is neither: it is architecture done before translation, and retrofitting it (pulling hard-coded strings out, fixing assumptions that text is short, LTR, and ASCII) is far more expensive than building it in from the start.

## In practice
- **The i18n checklist:** externalize all user-facing strings, use Unicode (UTF-8) end to end, format dates/numbers/currency through a [locale](locale.md)-aware library rather than by hand, and design layouts that tolerate [text-expansion](text-expansion.md) and [bidirectional-text](bidirectional-text.md).
- **Don't concatenate translatable strings:** word order differs by language, so building sentences from fragments produces nonsense once translated. Use whole, parameterized messages.
- **Verify early:** test with [pseudolocalization](pseudolocalization.md) before real translations exist, so missing i18n shows up while it is cheap to fix. See [Localization vs. Internationalization (W3C)](https://www.w3.org/International/questions/qa-i18n).

## Related terms
[Localization](localization.md) · [Locale](locale.md) · [Text expansion](text-expansion.md) · [Pseudolocalization](pseudolocalization.md)

## Further reading
- Code & specs: [Internationalization (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Internationalization)
- Foundations: [Localization vs. Internationalization (W3C)](https://www.w3.org/International/questions/qa-i18n)
