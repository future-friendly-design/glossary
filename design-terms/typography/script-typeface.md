---
term: Script (typeface)
slug: script-typeface
aliases:
  - script typeface
  - script type
level: foundational
depth: core
summary: A script typeface is a typeface drawn to look like handwriting.
related:
  - typeface
  - typography
  - font
  - script
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: "Generic font families: cursive (CSS Fonts Module Level 3, W3C)"
    url: https://www.w3.org/TR/css-fonts-3/#generic-font-families
    type: code
  - title: A guide to type styles (Monotype)
    url: https://www.monotype.com/resources/guide-type-styles
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Script (typeface)

## Definition

A script typeface is a typeface drawn to look like handwriting.<sup>1</sup>

A [typeface](typeface.md) is the design that a set of letters shares, the look that makes them belong together. In this term, "script" names a style of drawing. It does not mean a [script](../../language-terms/writing-systems-and-scripts/script.md) in the sense used everywhere else in this glossary, which is a set of symbols used to write one or more languages, such as Latin, Arabic or Devanagari. One word, two unrelated meanings.

### Why it matters in design systems

Think of a wedding invitation, a signature used as a logo, or the label on a jar of jam. The looping lettering on all three, where each letter runs into the next as if a pen never left the paper, is usually a script typeface. The letters are often connected and slanted, and the style can be formal, like careful penmanship, or loose and casual.<sup>2</sup>

The trouble starts when the word is used with no noun after it. "Does the brand have a script?" and "Which scripts does the brand font support?" sound like the same subject. They are not:

| What somebody says | What "script" means there | Examples |
| ------------------ | ------------------------- | -------- |
| "A script typeface", "a script font", "set the headline in a script" | A style of typeface that imitates handwriting | Snell Roundhand, Zapfino, Mistral<sup>3</sup> |
| "The Arabic script", "the font supports three scripts", "right-to-left scripts" | A set of symbols used to write languages | Latin, Arabic, Devanagari |

The two meanings even meet inside one definition. The standard for fonts on the web is part of CSS, the code that styles web pages. It has a category called `cursive` for handwriting-style fonts, and describes it like this: "Glyphs in cursive fonts generally use a more informal script style", followed by "CSS uses the term ‘cursive’ to apply to a font for any script".<sup>4</sup> The first "script" is the handwriting style. The second is the writing system. (A glyph is a shape that a font holds for a character.) If the people who write the standard need both meanings within two sentences, a design team will too, so it pays to always say which one you mean.

There is a second thing to know, and it is about where the idea comes from. "Script typeface" is a category from Latin type. The type foundry guide that the definition above comes from presents its list as the most common Latin type styles.<sup>5</sup> In the Latin script, letters normally stand apart in print, and running them together is something handwriting does. So a typeface with connected letters looks handwritten, and "connected" becomes a clue to the style.

That reasoning does not travel. The Arabic script is always connected, in handwriting and in print alike.<sup>6</sup> The letters kāf ك, tāʾ ت and bāʾ ب are written كتب in every Arabic typeface, from the plainest to the most ornate. Connection there is part of how the script is written, a rule called [joining](../../language-terms/writing-systems-and-scripts/joining.md), and no typeface can opt out of it. Calling an Arabic typeface a "script typeface" because its letters connect would describe all of them, and so describe nothing.

Other scripts have handwriting-based styles of their own, with their own names and their own jobs. Kai, a style for Chinese text with clear handwriting features, is commonly used in official documents and textbooks.<sup>7</sup> That is a long way from a wedding invitation. A style that reads as "informal" or "decorative" in one script can be the everyday, formal choice in another.

For your work, this comes down to naming and to not copying a decision across scripts. Write "script typeface" or "handwriting style" in full in guidelines, and keep the bare word "script" for writing systems; a design token, which is a named design decision that tools and code share, will be read both ways by somebody if it is called `script`. And when a brand uses a Latin script typeface for warmth or celebration, do not look for "the script version" in another writing system. Ask a designer who reads that script which style carries the same feeling there. It may not be a handwriting style at all.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../../programming-terms/text-in-software/character.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Typeface](typeface.md) · [Typography](../../terms/typography.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Fonts](../fonts/)

### Further reading

* Code & specs: [Generic font families: cursive (CSS Fonts Module Level 3, W3C)](https://www.w3.org/TR/css-fonts-3/#generic-font-families)
* Foundations: [A guide to type styles (Monotype)](https://www.monotype.com/resources/guide-type-styles)

### Sources

1. "Scripts are based on handwriting styles, and can often be differentiated based on different tools, such as brushes, markers or pointed nibs" - A guide to type styles, Monotype [https://www.monotype.com/resources/guide-type-styles](https://www.monotype.com/resources/guide-type-styles)
2. "The letters are often connected to each other and slanted, like in cursive writing. They can be very formal, based on classical penmanship, or very casual" - A guide to type styles, Monotype [https://www.monotype.com/resources/guide-type-styles](https://www.monotype.com/resources/guide-type-styles)
3. "Examples: Bello, Bickham Script, FS Shepton, FS Sammy, Mistral, Snell Roundhand, Zapfino" - A guide to type styles, Monotype [https://www.monotype.com/resources/guide-type-styles](https://www.monotype.com/resources/guide-type-styles)
4. "Glyphs in cursive fonts generally use a more informal script style, and the result looks more like handwritten pen or brush writing than printed letterwork. CSS uses the term ‘cursive’ to apply to a font for any script" - CSS Fonts Module Level 3, W3C Recommendation, 3.1.1 Generic font families [https://www.w3.org/TR/css-fonts-3/#generic-font-families](https://www.w3.org/TR/css-fonts-3/#generic-font-families)
5. "our guide looks to demystify some useful terminology to help you recognise the most common Latin type styles" - A guide to type styles, Monotype [https://www.monotype.com/resources/guide-type-styles](https://www.monotype.com/resources/guide-type-styles)
6. "The Arabic script is cursive, even in its printed form" - The Unicode Standard, Version 18.0, Chapter 9: West Asia-I, Arabic [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/)
7. "A major typeface, which provides calligraphic styles for Chinese text. It shows notable handwriting features. Kai is commonly used in official documents and textbooks" - CSS Fonts Module Level 4, W3C Working Draft, 2.1.5 Generic font families: generic(kai) [https://www.w3.org/TR/css-fonts-4/#valdef-font-family-generic-kai](https://www.w3.org/TR/css-fonts-4/#valdef-font-family-generic-kai)
