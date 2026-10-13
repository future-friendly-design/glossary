---
term: Text expansion
slug: text-expansion
aliases:
  - string expansion
level: foundational
depth: deep
summary: Text expansion is the growth in the space a piece of text needs when it is translated into another language.
related:
  - localization
  - internationalization
  - pseudolocalization
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Text size in translation (W3C)
    url: https://www.w3.org/International/articles/article-text-size
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Text expansion

## Definition

Text expansion is the growth in the space a piece of text needs when it is translated into another language.<sup>1</sup>

The name describes the most common case, not the only one. A translation can also be shorter than the original, or taller, and each of those changes the space a design has to provide. For example, the English word "views" is "visualizzazioni" in Italian, which is three times as long,<sup>2</sup> and 조회 in Korean, which takes up less room than the English.<sup>3</sup>

### Why it matters in design systems

A button that says "Save" tends to be drawn just wide enough for the word "Save". So is a tab, a menu item, the heading of a column. Each one is a small bet that the text will always be about that long, and the bet is placed in whichever language the product was first written in.

Here is one short label from a real product, the word "views" shown under a photo, in seven languages:

| Language | The word | Length compared with English<sup>4</sup> |
| -------- | -------- | ---------------------------- |
| Korean | 조회 | 0.8 |
| English | views | 1 |
| Chinese | 次檢視 | 1.2 |
| Portuguese | visualizações | 2.6 |
| French | consultations | 2.6 |
| German | -mal angesehen | 2.8 |
| Italian | visualizzazioni | 3 |

Each Chinese and Korean character is counted as two English letters in this table, because each one is wider.<sup>5</sup>

A word that triples in length looks like an extreme case. For a label this short it is ordinary. These are published averages for text translated from English into European languages, where 200% means twice the length of the original:

<!-- The W3C table also has a row for 51 to 70 characters that reads "151-170%", which breaks the downward pattern. It is left out here. The misprint starts in the IBM original (archived 2011-02-25 at https://web.archive.org/web/20110225183535/http://www-01.ibm.com/software/globalization/guidelines/a3.html), whose table gives ADDITIONAL space (100% to 200%, 80% to 100%, 60% to 80%, 40% to 60%, then 30% for over 70) and repeats the row label "51 to 70" in the value cell. W3C added 100 to every figure, which is why this page reads the percentages as total length, and which turned the misprint into "151-170%". NEEDS EXPERT REVIEW: the true 51-70 figure is in neither page; do not add the row without a source that states it. -->

| Number of characters in the English text | Average length of the translation<sup>6</sup> |
| ---------------------------------------- | ------------------------------------- |
| Up to 10 | 200 to 300% |
| 11 to 20 | 180 to 200% |
| 21 to 30 | 160 to 180% |
| 31 to 50 | 140 to 160% |
| Over 70 | 130% |

The published table also has a row for text of 51 to 70 characters. Its figure is a misprint, so that row is left out here.

The shorter the original text, the more it tends to grow.<sup>7</sup> That is hard on an interface, because the shortest text is exactly the text that gets squeezed into the smallest places: beside a form field, inside a graphic, across a row of tabs.<sup>8</sup> A paragraph has room to absorb its extra third. A four-letter button does not have room to become twelve letters.

Notice also what the table is measured by. It is the length of the original text, not the language it is translated into, and it describes English going into European languages only.

Width is not the only thing that changes, and text does not always get bigger:

| What changes | An example | What it does to a layout |
| ------------ | ---------- | ------------------------ |
| The text gets shorter | "views" becomes 조회 in Korean | A component stretched to fit the longest language is left with empty space, which can be as much of a problem as too little<sup>9</sup> |
| Each character is wider | English "desktop" becomes デスクトップ in Japanese. That is one character fewer, and it is much wider<sup>10</sup> | A box sized by counting characters is too narrow |
| The text becomes one long word | English "Input processing features" becomes "Eingabeverarbeitungsfunktionen" in German | The three English words can wrap onto a second line. The single German word may not wrap at all<sup>11</sup> |
| The text gets taller | Arabic, Chinese, Devanagari, Japanese, Korean, and Tibetan text all need more height than Latin text.<sup>12</sup> Tibetan, a [stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md), places consonants above and below one another, as in rgyud (རྒྱུད), "string"<sup>13</sup> | A row with a fixed height, or a [line height](../../design-terms/typography/line-height.md) tuned for Latin letters, cuts off the top or bottom of the text |
| The text runs the other way | Arabic is written [right to left](../../language-terms/writing-systems-and-scripts/right-to-left.md), as in marhaba (مرحبا), "hello"<sup>14</sup> | The line starts on the right,<sup>15</sup> so the room a design left after a label is now on the wrong side |

So leaving more room is only part of the answer. Width, height, wrapping, and direction can all change in the same translation, and a component has to be able to change with them.

### Common mistake

Adding one fixed percentage to every component, usually a figure someone remembers as how much longer one language is than another. The published averages are tied to the length of the original text, not to a language, and they are averages. The same product that turns "views" into a word three times as long leaves "FAQ" as "FAQ" in German and French, and turns it into "Perguntas freqüentes" in Portuguese.<sup>16</sup> A figure of 40 percent does appear in testing guidance, as a rule of thumb for how much to lengthen fake test text when the original is English.<sup>17</sup> It is not a measurement of any language. A single percentage gives a short button far too little room, and gives a paragraph more than it needs.

### In practice

* **Let the component change size, and write down how.** For every component that holds text, say what happens when the text is longer: it wraps onto another line, or the box grows, or as a last choice the text is cut short. Avoid small fixed widths and tight fits.<sup>18</sup> Do not rescue a tight layout by abbreviating the words, because another language may not be able to shorten them the same way.<sup>19</sup>
* **Keep type sizes and line heights where they can differ by script.** When font size and line height are held apart from the content, as design tokens are, they can be adjusted for a translation.<sup>20</sup> One line height shared by every script will be too tight for some of them, so plan for the value to vary.
* **Keep words out of pictures, and give icons with labels room to grow.** Text fitted snugly into a graphic has nowhere to go when it is translated.<sup>21</sup> The same is true of a label pinned at a fixed width beside an icon.

Test all of this before real translations arrive. [Pseudolocalization](pseudolocalization.md), a technique that swaps in fake text made longer on purpose, shows which components break.<sup>22</sup> Then test again with real text in each script the product supports, because fake text built from Latin letters cannot show how much height another script needs.

***

### Related terms and mentions

[Agglutinative language](../../language-terms/linguistics/agglutinative-language.md) · [Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Full-width](../text-in-software/full-width.md) · [Internationalization](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Line height](../../design-terms/typography/line-height.md) · [Localization](localization.md) · [Pseudolocalization](pseudolocalization.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Tibetan script](../../language-terms/writing-systems-and-scripts/tibetan-script.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Foundations: [Text size in translation (W3C)](https://www.w3.org/International/articles/article-text-size)

### Sources

1. "The general message is that text will normally expand" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
2. "The 300% expansion from English to Italian is not at all surprising for a small string such as this" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
3. Table row "Korean 조회 0.8", beside "English views 1" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
4. "The following table shows comparative lengths of the word Flickr used for 'views' as a ratio" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
5. "Because of the width of the glyphs involved, each Chinese and Korean character is counted as two English characters in width" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
6. "The following are average expected expansion rates for text translated from English into European languages, as published by IBM" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
7. "note carefully how the smaller the source message, the higher the likely translation length" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
8. "the smaller the English text, the more likely it is to be squeezed into a small space, such as alongside a form entry field, or inside a graphic, or a set of width restricted tabs" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
9. "smaller translations can be as problematic as bigger ones if they leave too much white space on the page" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
10. "The Japanese has one less character, but will typically take up much more horizontal space" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
11. "Whereas the English text can easily be wrapped on two lines where there is restricted width available, such as alongside a form entry field, or in a series of tabs or buttons, or in narrow columns, the German may not wrap automatically" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
12. "There are numerous scripts which require much more height than Latin text, including Arabic (especially in Nastaliq fonts), Chinese, Devanagari (used for Hindi), Japanese, Korean, Tibetan, etc." - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
13. "The base consonant can be written singly or it can have other consonants added above or below it to make a vertically “stacked” letter" - The Unicode Standard, Version 18.0, Chapter 13: South and Central Asia-II, Tibetan [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-13/)
14. "Hebrew and Arabic are right-to-left languages with new lines again being added below the previous ones" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
15. "The start of a line is not always the left side of a line" - CSS logical properties and values, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
16. "Of course, this is not true for every string or message, but when it is you must have some way of dealing with it. For example, Flickr translates "FAQ" as "FAQ" in German and French, but as "Perguntas freqüentes" in Portuguese" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
17. "When the source language is English, a good heuristic is to lengthen the text by 40%" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
18. "Allow text to reflow and avoid small fixed-width containers or tight squeezes where possible" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
19. "Other languages may not be able to replicate such an abbreviation, and the text may need to be bigger in translation" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
20. "Separate presentation and content, so that font sizes, line heights, etc. can be easily adapted for translated text" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
21. "Be especially careful about fitting text snugly into graphic designs" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
22. "Expand the string to simulate the longer strings that can result from translation. Expanded strings reveal layout and truncation issues" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
