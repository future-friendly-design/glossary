# Internationalization & localization terms

## Internationalization and localization for multi-language support

When your design system has to support multiple languages, the internationalization and localization work makes that possible. Internationalization (i18n) is the design and development work that prepares a product to be adapted to other languages and places. Localization (l10n) is the work of adapting a product to one particular language and place, with consideration for regional differences in reading and writing.&#x20;

For example, the order a date appears in its numeric form is different between the US and the UK, even though both use English: the US puts the month first and the UK puts the day first.&#x20;

### Why it matters

Almost none of this is translation. A design system supporting several languages has to decide what a text style does when the same label arrives three times as long, what a sort order means when the alphabet is not the one the code was written for, how a person types a language whose characters outnumber the keys on their keyboard, and which of a date, a number, a name order, and a currency are allowed to be assumptions.

Those are design decisions with visible consequences, made long before a translator sees a string.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every part of building multilingual software. If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### The two halves of the multi-language job

Preparing a product to hold any language, and then adapting it to one. Plus the technique for finding out whether the first half was actually done. Internationalization is the parent of the other terms in this section, except localization, its partner. Some are tools for the work, and the rest are things it has to plan for.

[**Internationalization (i18n)**](internationalization.md)

Internationalization is the design and development work that makes a product able to be adapted to other languages and places.

[**Localization (l10n)**](localization.md)

Localization is the work of adapting a product to one particular language and place.

[**Pseudolocalization**](pseudolocalization.md)

Pseudolocalization is a testing technique that swaps a product's text for a fake translation, to show whether the product is ready for a real one.

#### Describing a language and a place

A product needs a way to say which language and which regional conventions it is using, and a source of truth for what those conventions actually are. Language tags and locales are the same kind of code doing two jobs: a language tag says what language the content is in, and a locale says what the reader expects.

[**CLDR**](cldr.md)

CLDR is a shared public collection of data that records how each language writes things such as dates, numbers and sorted lists in each place it is used, so that software can look those conventions up instead of every product working them out.

[**ICU**](icu.md)

ICU is a widely used collection of ready-made code that products reuse to handle text and local conventions in many languages, such as formatting a date or sorting a list.

[**Language tag**](language-tag.md)

A language tag is a short code that labels a piece of text or other content with the language it is in.

[**Locale**](locale.md)

A locale is a short code that names a language and a specific location, so that software can look up the conventions used there for writing things such as dates, numbers and sorted lists.

#### What changes when the language changes

Some behaviour a product treats as fixed is really a local convention, and it changes underneath you.

[**Case mapping**](case-mapping.md)

Case mapping is the process software uses to change text from one letter case to another, such as from lowercase to uppercase.

[**Collation**](collation.md)

Collation is the set of rules that software follows to put text in order, for example when it sorts a list of names.

[**Text expansion**](text-expansion.md)

Text expansion is the growth in the space a piece of text needs when it is translated into another language.

[**Truncation**](truncation.md)

Truncation is cutting text short so it fits the space it is given, usually with an ellipsis (…) to show that some of it is hidden.

#### Typing in another language

Input is the half of multilingual support that design most often forgets, because the team's own keyboards already work.

[**Input method editor (IME)**](input-method-editor.md)

An input method editor (IME) is software that turns what a person types into the characters they mean, usually by offering a list of choices to pick from.

[**Keyboard layout**](keyboard-layout.md)

A keyboard layout is the set of rules that decides which character appears when a person presses a key on a keyboard or taps one on a screen.

### Where to go next

* How the text itself is stored, counted, and compared is covered in [Text encoding & character terms](../text-in-software/).
* Whether your type can render the languages you are adding is covered in [Font terms](../../design-terms/fonts/).
* What the languages and scripts themselves require is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/) and [Language & linguistics](../../language-terms/linguistics/).
