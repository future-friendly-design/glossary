---
term: Pseudolocalization
slug: pseudolocalization
aliases:
  - pseudo-localization
  - pseudo-loc
level: intermediate
depth: core
summary: Pseudolocalization is a testing technique that swaps a product's text for a fake translation, to show whether the product is ready for a real one.
related:
  - internationalization
  - localization
  - text-expansion
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Test your app with pseudolocales (Android Developers)
    url: https://developer.android.com/guide/topics/resources/pseudolocales
    type: code
  - title: Pseudolocalization (Microsoft Learn)
    url: https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Pseudolocalization

## Definition

Pseudolocalization is a testing technique that swaps a product's text for a fake translation, to show whether the product is ready for a real one.<sup>1</sup>

The fake translation is made by software, not by a translator. It changes the letters and makes the text longer, but the result can still be read, so a team can keep using the product while they test it.<sup>2</sup> For example, the English label `Settings` might be shown as `[Šéţţîñĝš one two]`: accents on the letters, extra words to add length, and a bracket at each end.<sup>3</sup>

The name borrows from [localization](localization.md), which is adapting a product to one particular language and place, with "pseudo" meaning fake. What it actually tests is [internationalization](internationalization.md), the earlier design and development work that makes a product able to be adapted at all.

### Why it matters in design systems

A product built in one language looks finished in that language. Every label fits its button and every sentence reads well, and nothing on the screen shows what will happen when the words change. Waiting for a real translation to find out means finding out late. Pseudolocalization needs no translator, so it can start with the first screens of a project and carry on all the way through it.<sup>4</sup>

The fake text is built up in steps, and each step is there to expose a different problem:

| Step | Before | After | What it is for |
| ---- | ------ | ----- | -------------- |
| Swap letters for accented ones | `Settings` | `Šéţţîñĝš` | Text that was never passed through the swap stays plain, so it stands out<sup>5</sup> |
| Make the text longer | `Šéţţîñĝš` | `Šéţţîñĝš one two` | Shows where a longer translation would not fit<sup>6</sup> |
| Put a marker at each end | `Šéţţîñĝš one two` | `[Šéţţîñĝš one two]` | If a marker is missing, the text was cut off<sup>7</sup> |

With that in place, a pseudolocalized screen can be read like a checklist:

| What you see | What it tells you |
| ------------ | ----------------- |
| A label still in plain, unaccented text | The text was typed directly into the code, which is called hard-coding. A translator will never be sent it<sup>8</sup> |
| An opening bracket with no closing bracket | The text was cut off, which is called truncation. The component did not have room for it |
| One sentence shown as two or more bracketed pieces | The sentence was glued together from separate pieces, which is called concatenation.<sup>9</sup> A translator cannot change the order of the pieces, and many languages need a different order<sup>10</sup> |
| Text overlapping its neighbours or pushed out of its box | The layout has no room for [text expansion](text-expansion.md), the growth in space that translated text often needs<sup>11</sup> |

How much longer should the fake text be? A common rule, when the original text is English, is to add 40 percent. That figure is a rule of thumb for testing, not a measurement of any language, and a real translation of a short label can turn out 200 or even 400 percent longer.<sup>12</sup>

Pseudolocalization shows whether a product can be translated. It does not replace testing the real translated product,<sup>13</sup> and it leaves these things unchecked:

* **Real scripts.** Accented Latin letters are still letters of the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md). Some tools also mix in characters from other [scripts](../../language-terms/writing-systems-and-scripts/script.md) to help reveal [font](font.md) problems,<sup>14</sup> but scattered characters are not words. Only real text shows whether a script is displayed correctly.
* **Right-to-left layout**, unless a mirrored version is used. Some platforms offer a second fake translation that turns the text [right to left](../../language-terms/writing-systems-and-scripts/right-to-left.md), so a team can check a mirrored layout without reading a right-to-left language.<sup>15</sup> It works by reversing the original characters, so it is still not Arabic or Hebrew.<sup>16</sup>
* **Shorter and taller text.** A translation can be shorter than the original, which is hard to imitate and so is left out.<sup>17</sup> Nothing in the fake text is taller than the original either.
* **Translation quality.** No real language is involved, so there is no translation to judge. Whether the words are right, natural, and respectful can only be checked by someone who knows the language.

For a design system, this makes pseudolocalization a cheap habit to add to component review. Look at every component with the fake text switched on, and check it against the table above before it is released. A component that passes has not been proven in every language. A component that fails has a problem worth fixing while it is still one component, and not yet forty screens in six languages.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [Internationalization](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Localization](localization.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Text expansion](text-expansion.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Test your app with pseudolocales (Android Developers)](https://developer.android.com/guide/topics/resources/pseudolocales)
* Foundations: [Pseudolocalization (Microsoft Learn)](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)

### Sources

1. "With pseudolocalization, you can verify that your product is localizable without actually localizing into a real language" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
2. "Pseudotranslation is an automated transformation of source text. It simulates common effects of translation that commonly cause issues with a product. The transformation is readable enough that the product can still be used and tested without knowing a foreign language" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
3. "adds Latin accents to the base English UI text, expands the original text by adding non-accented text, and brackets each message unit to expose potential issues from expanded text" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
4. "The pseudolocalization strategy can be applied in the earliest phases of development before translation begins. The strategy is sustained throughout the development cycle for continual testing and validation" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
5. "Resources that haven't been exposed to localization are readily apparent because they won't be pseudo-translated" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
6. "Expand the string to simulate the longer strings that can result from translation. Expanded strings reveal layout and truncation issues" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
7. "Wrapping a string instantly reveals truncations in the product user interface because the delimiter is missing" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
8. "Hardcoded strings, which can't be sent to translation, display as unaccented text in the pseudolocale to make them noticeable" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
9. "String concatenation, which displays as one message split across two or more brackets" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
10. "String concatenation can also make correct translation impossible, because different languages might require a different order of parts or a completely different sentence structure" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
11. "UI layout issues caused by text expansion, showing where the UI can break due to text length" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
12. "When the source language is English, a good heuristic is to lengthen the text by 40%. In practice, there can be extreme cases where a string may be 200% or even 400% longer when translated into a real language" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
13. "While pseudotranslation can help discover many potential issues with localization, it isn't a complete replacement for validating the translated application" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
14. "Pad text to the expansion length using characters from other scripts, such as Greek, Cyrillic, Asian, and Indic scripts. Adding text from other scripts helps reveal clipping and font-handling issues" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
15. "Pseudolocales can help you make an RTL version of your app, even if you don't write or speak any RTL languages" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
16. "sets the text direction of the original left-to-right messages to the right-to-left direction, which reverses the order of the characters in the original message" - Test your app with pseudolocales, Android Developers [https://developer.android.com/guide/topics/resources/pseudolocales](https://developer.android.com/guide/topics/resources/pseudolocales)
17. "Translations can also be shorter than the source text. Shrinkage generally causes fewer issues than growth and is challenging to simulate, so isn't used with pseudo" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
