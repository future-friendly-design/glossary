---
term: Collation
slug: collation
aliases: [sort order, Unicode Collation Algorithm, UCA]
tags: [i18n-engineering]
level: intermediate
depth: core
summary: Collation is the set of rules that software follows to put text in order, for example when it sorts a list of names.
related: [locale, icu, cldr, localization]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Collator (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator
    type: code
  - title: "UTS #10: Unicode Collation Algorithm"
    url: https://www.unicode.org/reports/tr10/
    type: authority
license: CC-BY-4.0
---

# Collation

## Definition

Collation is the set of rules that software follows to put text in order, for example when it sorts a list of names.<sup>1</sup>

Alphabetical order is one kind of collation. It is the kind used by languages written with an [alphabet](../../language-terms/writing-systems-and-scripts/alphabet.md), and even those languages do not agree with each other about it.

### Why it matters in design systems

Open a contacts screen, a country picker, or a table with a column you can sort, and the entries arrive in order. In English that order is called alphabetical, and it feels like a fact about the letters instead of a decision somebody made. It is a decision, and each [language](../../language-terms/linguistics/language.md) makes it differently: languages that share the same letters do not agree on where those letters go.<sup>2</sup>

Here are the same five entries, sorted three ways:

| Sorted by | Result |
| --------- | ------ |
| Swedish rules | anna, Olle, Zorn, Äpple, Östen |
| German rules | anna, Äpple, Olle, Östen, Zorn |
| The numbers the characters are stored as, with no language rules | Olle, Zorn, anna, Äpple, Östen |

In Swedish, ä is a letter of its own and comes after z,<sup>3</sup> and so does ö.<sup>4</sup> German sorts ä with the other forms of a.<sup>5</sup> Neither list is wrong. Each one is right for the people who read that language, and wrong for the others.

The third row is the one to watch for. A computer stores every [character](../text-in-software/character.md) as a number, and sorting by those numbers is the least work for the code, so it is what happens when nobody asks for anything better. It gives an order that no language uses.<sup>6</sup> In the stored numbers `Z` is 90 and `a` is 97, which is why `Zorn` lands ahead of `anna`.

The cost of a wrong order falls on the person looking for something. Someone who reads Danish expects Søren after Sylt, because Danish puts ø after z.<sup>7</sup> Someone who expects ø to sit with o looks between Sorem and Soret, does not see the name, and decides it is missing.<sup>8</sup> Nothing was lost. The list was in an order they could not use.

Language is not the only thing that changes the order. Inside a single language, a dictionary and a phone book can sort the same words differently.<sup>9</sup>

Many [scripts](../../language-terms/writing-systems-and-scripts/script.md) are not alphabets at all, so there is no alphabetical order to fall back on. [Chinese characters](../../language-terms/writing-systems-and-scripts/han-characters.md) can be sorted by how they are pronounced or by how they are drawn.<sup>10</sup> Sorting them by sound usually needs the pronunciation to be kept with the text,<sup>11</sup> which in a product can mean one more field in the form and one more column in the data.

Search follows sorting. If a language sorts two letters as the same letter, a search in that language should treat them as the same letter too.<sup>12</sup>

The shared rulebook for all of this is the Unicode Collation Algorithm. It gives one starting order for every character, built so that it can be adjusted for each language.<sup>13</sup> It is published as Unicode Technical Standard #10, which is a specification of its own and not a part of the [Unicode Standard](../text-in-software/unicode-standard.md).<sup>14</sup> The adjustments for each language are published in [CLDR](cldr.md), a public collection of language conventions. Software chooses a set of rules from a [locale](locale.md), the setting that says which language and regional conventions to use.

Those published rules are worth reading before you trust what you remember about a language. The standard rules for Spanish move one letter: ñ goes after n.<sup>15</sup> A second, optional set of Spanish rules, called traditional, also sorts ch after c and ll after l.<sup>16</sup> Which of the two a Spanish reader expects is a question to ask, and the answer may differ between a phone book and a product catalogue.

For a design system, this turns "sort A to Z" into three questions for every sorted list: which language's order, for what purpose, and what happens to an entry in a script that has no A and no Z. Write the answers into the specification of the component. And look at the label on the control, because a sort button that says "A to Z" has already assumed the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md).

***

### Related terms and mentions

[Alphabet](../../language-terms/writing-systems-and-scripts/alphabet.md) · [Character](../text-in-software/character.md) · [CLDR](cldr.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [ICU](icu.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Localization (l10n)](localization.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Unicode](../text-in-software/unicode.md) · [Unicode Standard](../text-in-software/unicode-standard.md) · [Multi-language products](../multi-language-products/)

### Further reading

* Code & specs: [Intl.Collator (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator)
* Foundations: [UTS #10: Unicode Collation Algorithm](https://www.unicode.org/reports/tr10/)

### Sources

1. "Collation is the general term for the process and function of determining the sorting order of strings of characters" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
2. "Collation varies according to language and culture: Germans, French and Swedes sort the same characters differently" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
3. "Swedish treats ä as an individual letter, sorting it after z in the alphabet" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
4. Table 1, Example Differences: "Swedish: z < ö German: ö < z" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
5. "German, however, sorts it either like ae or like other accented forms of a" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
6. "it is not even possible to arrange the encoding for characters so that simple binary string comparison produces the desired collation order for any particular language" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1.1.1 [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
7. "a few languages, such as Norwegian and Danish, sort ø as a unique element after z" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
8. "A user will look for "Søren" between "Sorem" and "Soret", not see it in the selection, and assume the string is missing" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
9. "even within the same language, dictionaries may sort differently than phonebooks or book indices" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
10. "For non-alphabetic scripts such as East Asian ideographs, collation can be either phonetic or based on the appearance of the character" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1 Introduction [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
11. "Phonetic sorting of Han characters requires use of either a lookup dictionary of words or, more typically, special construction of programs or databases to maintain an associated phonetic spelling for the words in the text" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1.4 [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
12. "if two letters are treated as identical base letters for sorting, then those letters should also be treated as identical for searching" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1.5 [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
13. "This table is designed so that it can be tailored to meet the requirements of different languages and customizations" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, section 1.9 [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
14. "A Unicode Technical Standard (UTS) is an independent specification. Conformance to the Unicode Standard does not imply conformance to any UTS" - Unicode Technical Standard #10: Unicode Collation Algorithm, version 18.0.0, Status [https://www.unicode.org/reports/tr10/tr10-55.html](https://www.unicode.org/reports/tr10/tr10-55.html)
15. The `standard` collation for Spanish holds one rule, `&N<ñ<<<Ñ` - CLDR 48, common/collation/es.xml [https://github.com/unicode-org/cldr/blob/release-48/common/collation/es.xml](https://github.com/unicode-org/cldr/blob/release-48/common/collation/es.xml)
16. The `traditional` collation for Spanish adds two rules, `&C<ch<<<Ch<<<CH` and `&l<ll<<<Ll<<<LL` - CLDR 48, common/collation/es.xml [https://github.com/unicode-org/cldr/blob/release-48/common/collation/es.xml](https://github.com/unicode-org/cldr/blob/release-48/common/collation/es.xml)
