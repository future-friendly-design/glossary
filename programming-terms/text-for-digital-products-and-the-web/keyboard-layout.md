---
term: Keyboard layout
slug: keyboard-layout
aliases: []
tags: [i18n-engineering]
level: foundational
depth: core
summary: A keyboard layout is the set of rules that decides which character appears when a person presses a key on a keyboard or taps one on a screen.
related: [input-method-editor, internationalization, locale]
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors: [sam-gordashko]
further_reading:
  - title: "KeyboardEvent: code property (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code
    type: code
  - title: "CLDR Keyboard Working Group (Unicode)"
    url: https://cldr.unicode.org/index/keyboard-workgroup
    type: authority
license: CC-BY-4.0
---

# Keyboard layout

## Definition

A keyboard layout is the set of rules that decides which character appears when a person presses a key on a keyboard or taps one on a screen.<sup>1</sup>

Keyboard layouts are one of the things [internationalization (i18n)](internationalization.md) has to plan for. Internationalization is the design and development work that makes a product able to be adapted to other languages and places.<sup>2</sup>

The layout is a setting in the software, and it is separate from the keyboard as an object. The keys can stay exactly where they are while the layout changes what they produce.<sup>3</sup>

### Why it matters in design systems

Look down at a keyboard and every key has a character printed on it, so it is natural to think that the key is that character. It is not. Pressing a key only tells the computer which key went down, and the layout chosen in the settings turns that into a character. The printed label is a hint about one layout, and it can be wrong.<sup>4</sup>

Here is one key, the one labelled `2` on a keyboard sold in the United States, under three layouts:

| Layout | Pressing the key | Pressing it with Shift held down |
| ------ | ---------------- | -------------------------------- |
| United States | `2` | `@` |
| United Kingdom | `2` | `"` |
| French | `é` | `2` |

Same key, same finger, three results.<sup>5</sup>

The keyboard on a phone screen is a layout too, and it has moves that a physical keyboard does not. Holding a key down can open a small set of related characters, such as the accented forms of a letter.<sup>6</sup> Physical keyboards have their own move for accents, called a dead key: a key that types no character of its own and changes the next key instead, so that `^` followed by `e` gives `ê`.<sup>7</sup>

One language does not mean one layout. Several layouts are often in use for the same language,<sup>8</sup> so knowing which language a person writes does not tell you where their keys are.

In a product, this shows up first in keyboard shortcuts. A shortcut can be tied to the character a key types or to the position of the key, and software can ask for either one.<sup>9</sup> The two come apart as soon as the layout changes. On the French layout in the table, a shortcut on `2` needs Shift, and a shortcut described in the help text as "the key next to 1" points at a different character. So decide what each shortcut means. A shortcut that stands for a word, such as S for save, belongs to the character. A shortcut that depends on where the fingers rest belongs to the position.

A keyboard layout is also not the only way text gets in. Some languages are typed through an [input method editor](input-method-editor.md), software that offers a list of possible characters and lets the person choose. The two are separate things. A layout follows fixed rules, so the same keys always give the same character, while an input method editor asks a question. The shared format for describing layouts, published in [CLDR](cldr.md), a public collection of language conventions, covers layouts and, for now, leaves input method editors out.<sup>10</sup>

The larger problem is whether a layout exists at all. For most of the world's languages, keyboard support is either missing or does not meet the needs of the people who write them.<sup>11</sup> Being able to type often arrives many years after a [script](../../language-terms/writing-systems-and-scripts/script.md) is added to [Unicode](../text-in-software/unicode.md), the shared list of characters that software uses.<sup>12</sup> So a product can hold the right font, show a language correctly on every screen, and still be unusable in that language, because nobody can type in it. When a design system adds a language, ask the people who write it how they enter text today, and test every text field that way.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [CLDR](cldr.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Input method editor (IME)](input-method-editor.md) · [Internationalization (i18n)](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Locale](locale.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Unicode](../text-in-software/unicode.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [KeyboardEvent: code property (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code)
* Foundations: [CLDR Keyboard Working Group (Unicode)](https://cldr.unicode.org/index/keyboard-workgroup)

### Sources

1. Key map: "The basic mapping between hardware or on-screen positions and the output characters for each set of modifier combinations associated with a particular layout" - Unicode Technical Standard #35, version 48.2, Unicode Locale Data Markup Language (LDML) Part 7: Keyboards, Definitions [https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html](https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html)
2. "Designing and developing in a way that removes barriers to localization or international deployment" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
3. "While the arrangement of keys on a keyboard may be fixed, the mapping of those keys may vary" - Unicode Technical Standard #35, version 48.2, Unicode Locale Data Markup Language (LDML) Part 7: Keyboards, Definitions [https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html](https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html)
4. "the visual appearance of the key has no bearing on its digital representation, and in many configurations may be completely inaccurate" - UI Events, W3C Working Draft, section 4.1.1 Key Legends [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
5. Table "Handling the "2" Key (with and without Shift pressed) on various keyboard layouts", whose rows give `2` and `@` for US, `2` and a double quotation mark for UK, and `é` and `2` for French - UI Events, W3C Working Draft, section 4.2.3 code Examples [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
6. Long-press key: "Secondary keys typically provide access to variants of the top level key, such as accented variants" - Unicode Technical Standard #35, version 48.2, Unicode Locale Data Markup Language (LDML) Part 7: Keyboards, Definitions [https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html](https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html)
7. "in many Latin keyboards hitting the ^ dead-key followed by the e key produces ê" - Unicode Technical Standard #35, version 48.2, Unicode Locale Data Markup Language (LDML) Part 7: Keyboards, Definitions [https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html](https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html)
8. "The layout attribute describes the layout pattern, such as QWERTY, DVORAK, INSCRIPT, etc. typically used to distinguish various layouts for the same language" - Unicode Technical Standard #35, version 48.2, Unicode Locale Data Markup Language (LDML) Part 7: Keyboards, Element: info [https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html](https://www.unicode.org/reports/tr35/tr35-78/tr35-keyboards.html)
9. "code holds a string that identifies the physical key being pressed. The value is not affected by the current keyboard layout or modifier state, so a particular key will always return the same value" - UI Events, W3C Working Draft, section 3.5.1 Interface KeyboardEvent [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
10. "Input Method Editors (IME) or other input methods are not currently in scope for this format" - CLDR Keyboard Working Group, Unicode CLDR [https://cldr.unicode.org/index/keyboard-workgroup](https://cldr.unicode.org/index/keyboard-workgroup)
11. "keyboard support for most of the world’s languages is either completely missing or often does not adequately support the input needs of language communities" - CLDR Keyboard Working Group, Unicode CLDR [https://cldr.unicode.org/index/keyboard-workgroup](https://cldr.unicode.org/index/keyboard-workgroup)
12. "input support often lags many years behind when a script is added to Unicode" - CLDR Keyboard Working Group, Unicode CLDR [https://cldr.unicode.org/index/keyboard-workgroup](https://cldr.unicode.org/index/keyboard-workgroup)
