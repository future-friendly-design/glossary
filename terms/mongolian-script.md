---
term: Mongolian script (traditional)
slug: mongolian-script
aliases:
  - classical Mongolian script
  - Hudum Mongol bichig
level: advanced
depth: core
summary: The traditional Mongolian script is used to write Mongolian, written vertically from top to bottom in columns that run left to right.
related:
  - alphabet
  - cyrillic
  - joining
  - vertical-text
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-08T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Technical Note #57: Encoding and Shaping of the Mongolian Script'
    url: https://www.unicode.org/notes/tn57/
    type: code
  - title: Noto Sans Mongolian (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Mongolian
    type: design-tool
  - title: Unicode Mongolian code chart (U+1800)
    url: https://www.unicode.org/charts/PDF/U1800.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Mongolian script (traditional)

## Definition

The traditional Mongolian [script](../language-terms/writing-systems-and-scripts/script.md) is used to write Mongolian, written vertically from top to bottom in columns that run left to right.<sup>1</sup> It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md), with separate letters for consonants and vowels. The script is cursive, so the letters of a word normally join,<sup>2</sup> and many take different initial, medial, final, and isolate forms depending on their position.<sup>3</sup> It was created around the beginning of the thirteenth century, during the reign of Genghis Khan, and derives from the Old Uyghur script,<sup>4</sup> itself an adaptation of Sogdian Aramaic, a Semitic script written horizontally from right to left.<sup>5</sup>

For example, the script's own name ᠮᠣᠩᠭᠣᠯ ᠪᠢᠴᠢᠭ ("Mongol bichig", "Mongol script") joins its letters into one cursive line. Set properly it runs vertically, top to bottom in a column; many tools, this page included, display it horizontally instead, the very vertical-layout gap the rules below describe.

{% hint style="info" %}
This glossary doesn't cover every Mongolian script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Mongolian script profile

These properties of the traditional Mongolian script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Mongolian script (traditional) |
| --- | --- |
| [Autonym](autonym.md) | ᠮᠣᠩᠭᠣᠯ ᠪᠢᠴᠢᠭ |
| Languages | Mongolian (used especially in Inner Mongolia, China) |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | None (no combining vowel or tone marks); free variation selectors are appended to pick a letter's shape variant |
| Numerals | Mongolian digits (U+1810 to U+1819), alongside common ASCII digits |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) (cursive) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | letters for consonants and vowels, joining cursively, many with initial, medial, final, and isolate forms |

### Mongolian script rules and digital use considerations

If your design system supports languages that use the traditional Mongolian script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Mongolian script | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Yes: vertical layout, cursive joining, positional forms, and variation selectors | Genuinely different work: most layout engines, CSS defaults, and UI components assume horizontal lines. Mongolian's encoding model is, in Unicode's words, "in many respects ... the most complicated" of any script within Unicode,<sup>6</sup> so budget for it rather than treating it as a horizontal script turned sideways |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Vertical, top to bottom, in columns that run left to right (the reverse of the right-to-left column order of [CJK](cjk.md) vertical text)<sup>7</sup> | You cannot reuse horizontal-layout assumptions, and the column order is even the reverse of CJK vertical text, so verify your layout stack can set vertical, left-to-right columns, not just horizontal lines |
| [Joining](../language-terms/writing-systems-and-scripts/joining.md) | letters connect cursively, most taking an initial, medial, final, or isolate form depending on their position in the word | The font's [OpenType](opentype.md) rules select the positional form and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies it at render time, the step that turns stored characters into positioned glyphs |
| Variation selectors | when the correct letter shape cannot be derived automatically, a free variation selector is appended to force it | Some letter shapes cannot be predicted algorithmically, so a free variation selector has to be appended to the letter to force the right form,<sup>8</sup> get this wrong and the text shows the wrong forms, not just unstyled |
| [Unicode](unicode.md) block | Mongolian, [U+1800 to U+18AF](https://www.unicode.org/charts/PDF/U1800.pdf) (plus Mongolian Supplement) | A Latin or [Cyrillic](../language-terms/writing-systems-and-scripts/cyrillic.md) font will not render it, so confirm [font coverage](font-coverage.md) of the block, the positional forms, and the variation selectors |

### In practice

* **Confirm vertical layout before you commit a typeface or a tool:** verify the font ships the cursive joining and positional forms AND that your layout stack can set vertical, left-to-right columns, not just horizontal lines. [Noto Sans Mongolian](https://fonts.google.com/noto/specimen/Noto+Sans+Mongolian) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real vertical line, not a row of glyphs:** set a real Mongolian word in a vertical column and confirm the letters join, pick up their positional forms, and show the intended shapes (adding free variation selectors where a shape cannot be derived automatically). Tool support for [complex text layout](complex-text-layout.md) and vertical text varies, so test early.
* **Check the orthography, and which script the community uses:** Mongolian is written in the traditional script in Inner Mongolia and largely in [Cyrillic](../language-terms/writing-systems-and-scripts/cyrillic.md) in Mongolia, so do not assume one system. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Cyrillic](../language-terms/writing-systems-and-scripts/cyrillic.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Unicode Technical Note #57: Encoding and Shaping of the Mongolian Script](https://www.unicode.org/notes/tn57/)
* Design tools: [Noto Sans Mongolian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Mongolian)
* Foundations: [Unicode Mongolian code chart (U+1800)](https://www.unicode.org/charts/PDF/U1800.pdf)

### Sources

1. The Mongolian script is written vertically from top to bottom in columns running from left to right - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
2. The Mongolian script is cursive, and the letters constituting a word are normally joined together - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
3. Many letters also have distinct glyph forms depending on their position within a word; these positional forms are classified as initial, medial, final, or isolate - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
4. The Mongolian script was created around the beginning of the thirteenth century, during the reign of Genghis Khan; it derives from the Old Uyghur script - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
5. Old Uyghur itself was an adaptation of Sogdian Aramaic, a Semitic script written horizontally from right to left - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
6. The encoding model for Mongolian is somewhat different from that for any other script within Unicode, and in many respects it is the most complicated - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
7. Characters are arranged from top to bottom, and lines are arranged from right to left - Requirements for Chinese Text Layout (clreq), W3C [https://www.w3.org/TR/clreq/](https://www.w3.org/TR/clreq/)
8. When a glyph form that cannot be predicted algorithmically is required, the user needs to append an appropriate variation selector to the letter - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
</content>
