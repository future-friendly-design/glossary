---
term: Internationalization (i18n)
slug: internationalization
aliases:
  - i18n
level: foundational
depth: deep
summary: Internationalization is the design and development work that makes a product able to be adapted to other languages and places.
related:
  - localization
  - locale
  - text-expansion
  - pseudolocalization
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: Internationalization (MDN)
    url: https://developer.mozilla.org/en-US/docs/Glossary/Internationalization
    type: code
  - title: Localization vs. Internationalization (W3C)
    url: https://www.w3.org/International/questions/qa-i18n
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Internationalization (i18n)

## Definition

Internationalization is the design and development work that makes a product able to be adapted to other languages and places.<sup>1</sup>

It is often written "i18n", because there are 18 letters between the i and the n.<sup>2</sup>

The work usually covers five things:

* **Holding any language's text.** The product stores and shows text with [Unicode](../text-in-software/unicode.md), the shared list of the world's [characters](../text-in-software/character.md).<sup>3</sup>
* **Supporting every script's rules.** Each [script](../../language-terms/writing-systems-and-scripts/script.md) has its own rules, and the product has to follow them. One of these rules is [text direction](../../language-terms/writing-systems-and-scripts/text-direction.md): a script can be read [left to right](../../language-terms/writing-systems-and-scripts/left-to-right.md), [right to left](../../language-terms/writing-systems-and-scripts/right-to-left.md), or top to bottom ([vertical text](../../terms/vertical-text.md)). A single line can also mix left-to-right and right-to-left text ([bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md)). And each piece of text carries a [language tag](language-tag.md), so software knows which language, and so which rules, it is dealing with.<sup>4</sup>
* **Following each reader's conventions.** Dates, numbers, calendars and the order of sorted lists ([collation](collation.md)) follow the reader's [locale](locale.md).<sup>5</sup> The way a word changes from small letters to capitals ([case mapping](case-mapping.md)) also differs from one language to another.<sup>6</sup> The conventions themselves come from shared data ([CLDR](cldr.md)) through ready-made code ([ICU](icu.md)).<sup>7</sup>
* **Keeping the words separate from the design.** Text lives outside the screens and components, so a translated version can be swapped in.<sup>8</sup> The design also leaves room for a translation that takes more space than the original ([text expansion](text-expansion.md)).<sup>9</sup>
* **Letting people type their language.** The product works with the [keyboard layout](keyboard-layout.md) a person has chosen, the setting that decides which character each key produces.<sup>10</sup> It also works with the [input method editor (IME)](input-method-editor.md) that some languages need, software that turns key presses into the characters a person means.<sup>11</sup>

A test called [pseudolocalization](pseudolocalization.md) checks whether this work was done, before any translator is involved.<sup>12</sup>

Internationalization is one half of a pair. The other half is [localization](localization.md), which is adapting the product to one particular language and place. Internationalization comes first: designers and developers internationalize a product so that translators and localizers can then localize it.<sup>13</sup>

### Why it matters in design systems

Look at a button that says "Search". Somebody typed that word straight into the design file, and a developer typed it straight into the code. The button is exactly as wide as those six letters. The date beside it puts the month first, and the arrow for "next" points to the right.

None of that looks like a decision, yet each part quietly assumes one language and one place. Internationalization is the work of finding those assumptions and taking them out, so the product can hold a language it was not first written in. It is not translation. Not one word has to be translated for a product to be internationalized, and the work is useful even if the product never is.<sup>14</sup>

These are assumptions that often get built in without anyone choosing them:

| What was assumed | What goes wrong in another language | What internationalization does instead |
| ---------------- | ----------------------------------- | -------------------------------------- |
| Text can be typed directly into the screens and the code | A translator cannot reach that text, so it stays in the first language | Every piece of text is kept in a list of its own, apart from the code, so a translated list can be loaded in its place<sup>15</sup> |
| A label will always be about this long | A longer translation is cut off or pushed out of its box (see text expansion) | Components let text wrap onto another line and let the box grow<sup>16</sup> |
| A sentence can be glued together from pieces, such as "You have" + "3" + "new messages" | Other languages order the words differently, or change one word to match another, so the glued sentence comes out wrong<sup>17</sup> | Each message is written as one whole sentence, with a named gap for the part that changes<sup>18</sup> |
| Dates, numbers, and money are written one way everywhere | The date 03/04/02 is read month first in the United States, day first in most of Europe, and year first in Japan<sup>19</sup> | The product keeps the value and lets software write it out the way the reader expects.<sup>20</sup> It knows what the reader expects from their locale, the name software uses for one set of language and regional preferences<sup>21</sup> |
| Text runs from left to right | [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md) and [Hebrew](../../language-terms/writing-systems-and-scripts/hebrew-script.md) are written right to left, so a line starts on the right<sup>22</sup> | Spacing and alignment are described by the start and end of the text, not by the left and right of the screen<sup>23</sup> |
| Any way of storing text will do | A name written in another script may not be saved or shown correctly | Text is stored using Unicode, a standard that covers the world's [writing systems](../../language-terms/writing-systems-and-scripts/writing-system.md)<sup>24</sup> |
| A picture means the same thing to everyone | An image or icon can be misread, or give offence, in another culture<sup>25</sup> | Icons and images are treated as content that can be swapped for each place, the same as text<sup>26</sup> |

Notice where those decisions are made. How wide a button may get, what happens when a label is too long, whether a spacing value is named "left" or "start", whether a sentence is written whole: most of this is settled in the design file and the component library, before a developer or a translator has seen anything. That is why internationalization is design work as much as it is code, and why a design system is the cheapest place to do it. A decision made once in a component is inherited by every screen that uses it.

### Common mistake

Leaving it until a second language is asked for. By then the text is fixed into the screens, the components are sized to the words of one language, and the sentences are glued from pieces, so adding a language means rebuilding the product instead of translating it. Reworking a product that was built around one language and culture is much harder and slower than designing it for many from the start.<sup>27</sup> The second language is not the moment internationalization begins. It is the moment a team finds out whether it was done.

### In practice

A design system carries this work in three places:

* **In components, decide what happens when the text is longer.** Write it into each component's specification: the label wraps onto a second line, or the box grows, or the text is cut short with an ellipsis. Cutting text short, called truncation, hides words from the reader, so make it the last choice and never the unstated default. Leave the same freedom for a label that sits beside an icon.
* **Name component children based on logical property names.** CSS, the language that styles web pages, can describe spacing and position by the start and end of a line instead of its left and right: `padding-inline-start` instead of `padding-left`.<sup>28</sup> Use the same start and end words for a component's child layers, and for its properties and [tokens](../../design-terms/design-token.md) too: an icon slot called `icon-start`, not `icon-left`. The start of a line is not always its left side,<sup>29</sup> and a name built on start and end still makes sense when the layout is mirrored for a language written right to left. Content translated into a language with a different direction then still displays as intended.<sup>30</sup>
* **In content guidelines, ask for whole sentences.** Write "You have {count} new messages" as one message with a named gap. A translator has to be able to move that gap anywhere in the sentence, because the number may belong at the beginning or the end in their language.<sup>31</sup>

Then check the work before any translator is involved. Pseudolocalization swaps a product's text for a fake translation, and it can be used from the earliest stage of a project.<sup>32</sup> Every problem it shows in a component is one that would otherwise be found later, in every language at once.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Case mapping](case-mapping.md) · [Character](../text-in-software/character.md) · [Character encoding](../text-in-software/character-encoding.md) · [CLDR](cldr.md) · [Collation](collation.md) · [Design token](../../design-terms/design-token.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [ICU](icu.md) · [Input method editor (IME)](input-method-editor.md) · [Keyboard layout](keyboard-layout.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Locale](locale.md) · [Localization (l10n)](localization.md) · [Pseudolocalization](pseudolocalization.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Text expansion](text-expansion.md) · [Unicode](../text-in-software/unicode.md) · [Vertical text](../../terms/vertical-text.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Internationalization & localization terms](../internationalization-and-localization/)

### Further reading

* Code & specs: [Internationalization (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Internationalization)
* Foundations: [Localization vs. Internationalization (W3C)](https://www.w3.org/International/questions/qa-i18n)

### Sources

1. "Internationalization is the design and development of a product, application or document content that enables easy localization for target audiences that vary in culture, region, or language" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
2. "Internationalization is sometimes abbreviated i18n because there are eighteen letters between the "I" and the "N" in the English word" - Internationalization Glossary, W3C Group Note: Internationalization [https://www.w3.org/TR/i18n-glossary/#dfn-i18n](https://www.w3.org/TR/i18n-glossary/#dfn-i18n)
3. "enabling the use of Unicode, or ensuring the proper handling of legacy character encodings where appropriate" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
4. "adding markup in your DTD to support bidirectional text, or for identifying language. Or adding to CSS support for vertical text or other non-Latin typographic features" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
5. "Examples include date and time formats, local calendars, number formats and numeral systems, sorting and presentation of lists" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
6. "Case mapping, at first, appears simple. However there are variations that need to be considered when treating the full range of Unicode in diverse languages" - Internationalization Glossary, W3C Group Note: Case mapping [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
7. "Typically this involves incorporating predefined localization data and features derived from existing libraries or user preferences" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
8. "Separating localizable elements from source code or content" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
9. "The general message is that text will normally expand" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
10. "keyboard support for most of the world's languages is either completely missing or often does not adequately support the input needs of language communities" - Unicode CLDR Project: Keyboard Working Group [https://cldr.unicode.org/index/keyboard-workgroup](https://cldr.unicode.org/index/keyboard-workgroup)
11. "Input method editors are used in many situations: To enter Chinese, Japanese, or Korean text using a Latin keyboard" - MDN Web Docs Glossary: Input method editor [https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor)
12. "With pseudolocalization, you can verify that your product is localizable without actually localizing into a real language" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
13. "Designers and developers internationalize products, so that they can be easily localized by translators and localizers" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
14. "Notice that these items do not necessarily include the localization of the content, application, or product into another language; they are design and development practices which allow such a migration to take place easily in the future but which may have significant utility even if no localization ever takes place" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
15. "such that localized alternatives can be loaded or selected based on the user's international preferences as needed" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
16. "Allow text to reflow and avoid small fixed-width containers or tight squeezes where possible" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
17. "it can be either difficult or impossible to deal with such composite messages in other languages because of differing rules for sentence structure, agreement and so on" - Working with Composite Messages, W3C Internationalization [https://www.w3.org/International/articles/composite-messages/](https://www.w3.org/International/articles/composite-messages/)
18. "A better approach would be to use a print function that allows you to specify the variables as a part of the string to print" - Working with Composite Messages, W3C Internationalization [https://www.w3.org/International/articles/composite-messages/](https://www.w3.org/International/articles/composite-messages/)
19. "The format MM/DD/YY is unique to the United States (but sometimes used in Canada, too, which can obviously create some confusion there). Most of Europe uses DD/MM/YY. Japan uses YY/MM/DD" - Date formats, W3C Internationalization [https://www.w3.org/International/questions/qa-date-format](https://www.w3.org/International/questions/qa-date-format)
20. "Enabling code to support local, regional, language, or culturally related preferences" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
21. "An identifier (such as a language tag) for a set of international preferences" - Internationalization Glossary, W3C Group Note: Locale [https://www.w3.org/TR/i18n-glossary/#dfn-locale](https://www.w3.org/TR/i18n-glossary/#dfn-locale)
22. "Hebrew and Arabic are right-to-left languages with new lines again being added below the previous ones" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
23. "The logical properties defined in this module enable defining properties relative to the content's writing direction, rather than a physical direction" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
24. "The work of the Unicode Consortium is a fundamental part of internationalization. Unicode supports not only variations among the world's writing systems but also cultural variations such as currencies and time/date formats" - Internationalization (i18n), MDN Glossary [https://developer.mozilla.org/en-US/docs/Glossary/Internationalization](https://developer.mozilla.org/en-US/docs/Glossary/Internationalization)
25. "Text and graphics containing references to objects, actions or ideas which, in a given culture, may be subject to misinterpretation or viewed as insensitive" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
26. "Content that can be adapted to meet the needs of a particular language, culture, or region. It includes both localizable text and non-text content such as icons" - Internationalization Glossary, W3C Group Note: Localizable content [https://www.w3.org/TR/i18n-glossary/#dfn-localizable-content](https://www.w3.org/TR/i18n-glossary/#dfn-localizable-content)
27. "Retrofitting a linguistically- and culturally-centered deliverable for a global market is obviously much more difficult and time-consuming than designing a deliverable with the intent of presenting it globally" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
28. "Properties that once only accepted physical values (top, bottom, left, right) now also accept flow-relative logical values (block-start, block-end, inline-start, inline-end)" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
29. "The start of a line is not always the left side of a line" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
30. "This means content translated into languages with different writing modes will be rendered as intended" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
31. "It must be possible to reorder variables in sentence-like arrangements and reposition them in any way relative to the text" - Working with Composite Messages, W3C Internationalization [https://www.w3.org/International/articles/composite-messages/](https://www.w3.org/International/articles/composite-messages/)
32. "The pseudolocalization strategy can be applied in the earliest phases of development before translation begins" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
