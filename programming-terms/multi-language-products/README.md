# Multi-language products

## Building for more than one language

There are two halves to this job, and mixing them up is the most expensive mistake in the area.

Internationalization is the up-front work that makes a product capable of holding another language at all: text pulled out of the code, layouts that survive a longer word, formats that are not hard-coded to one country's habits.
Localization is adapting that prepared product to one particular language and place.

The order is not negotiable.
You cannot cleanly localize a product whose text is baked into its screens, and no amount of translation budget fixes a layout that assumed every label would be short.

### Why it matters

Almost none of this is translation.
A design system supporting several languages has to decide what a text style does when the same sentence arrives 40 percent longer, what a sort order means when the alphabet is not the one the code was written for, how a person types a language whose characters outnumber the keys on their keyboard, and which of a date, a number, a name order, and a currency are allowed to be assumptions.

Those are design decisions with visible consequences, made long before a translator sees a string.

***

### Terms by topic

{% hint style="info" %}
This glossary does not cover every part of building multilingual software; its coverage follows the questions that came up in the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching. Select a linked term to navigate to its glossary page to learn more.

If there is a term you would like to see added, head to the [contributing page](../../CONTRIBUTING.md).
{% endhint %}

#### The two halves of the job

Preparing a product to hold any language, and then adapting it to one. Plus the technique for finding out whether the first half was actually done.

* [Internationalization](../text-for-digital-products-and-the-web/internationalization.md)
* [Localization](../text-for-digital-products-and-the-web/localization.md)
* [Pseudolocalization](../text-for-digital-products-and-the-web/pseudolocalization.md)

#### Describing a language and a place

A product needs a way to say which language and which regional conventions it is using, and a source of truth for what those conventions actually are.

* [CLDR](../text-for-digital-products-and-the-web/cldr.md)
* [ICU](../text-for-digital-products-and-the-web/icu.md)
* [Locale](../text-for-digital-products-and-the-web/locale.md)

#### What changes when the language changes

Some behaviour a product treats as fixed is really a local convention, and it changes underneath you.

* [Collation](../text-for-digital-products-and-the-web/collation.md)
* [Text expansion](../text-for-digital-products-and-the-web/text-expansion.md)

#### Typing in another language

Input is the half of multilingual support that design most often forgets, because the team's own keyboards already work.

* [Input method editor (IME)](../text-for-digital-products-and-the-web/input-method-editor.md)
* [Keyboard layout](../text-for-digital-products-and-the-web/keyboard-layout.md)

### Where to go next

* How the text itself is stored, counted, and compared is covered in [Text in software](../text-in-software/).
* Whether your type can render the languages you are adding is covered in [Fonts](../../design-terms/fonts/).
* What the languages and scripts themselves require is covered in [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/) and [Language & linguistics](../../language-terms/linguistics/).
