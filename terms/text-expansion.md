---
term: Text expansion
slug: text-expansion
aliases: [string expansion]
tags: [i18n-engineering]
level: foundational
depth: deep
summary: Text expansion is the tendency for translated text to take up more space than the original, which can break layouts.
related: [localization, internationalization, pseudolocalization]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Text size in translation (W3C)"
    url: https://www.w3.org/International/articles/article-text-size
    type: authority
license: CC-BY-4.0
---

## Definition
Text expansion is the tendency for translated text to take up more space than the original, which can break layouts.

## Why it matters
Translation frequently makes text longer (German and Finnish are common offenders, though some languages shrink). The growth is largest for the shortest strings: the W3C, citing IBM's figures, puts expansion at roughly 200 to 300 percent for source strings up to 10 characters, tapering to around 130 percent for long passages. So a tiny button label can double or triple in width while a paragraph grows modestly. Designers and engineers have to leave room, or translated text overflows, clips, or wraps badly.

## Example
The English "Save" can become the German "Speichern", and short labels like this sit exactly where expansion is largest.

## Common mistake
Sizing buttons, labels, tabs, and containers to fit the English text. A control that perfectly fits "Save" clips "Speichern" and far longer equivalents in other locales. Because the squeeze only shows up after translation, English-only testing hides it completely.

## In practice
- **Design for reflow:** avoid fixed-width, single-line, or tightly packed containers; let text wrap and let containers grow. Give the most generous slack to the shortest labels, where growth is highest. See [Text size in translation (W3C)](https://www.w3.org/International/articles/article-text-size).
- **Separate content from presentation** so font size, line height, and wrapping can adapt per locale rather than being baked into a fixed box.
- **Test before translations arrive:** [pseudolocalization](pseudolocalization.md) pads strings to simulate expansion, surfacing overflow while the design is still cheap to change.

## Related terms
[localization](localization.md) · [internationalization](internationalization.md) · [pseudolocalization](pseudolocalization.md)

## Further reading
- Foundations: [Text size in translation (W3C)](https://www.w3.org/International/articles/article-text-size)
