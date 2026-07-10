---
term: Alphabet
slug: alphabet
aliases: []
level: foundational
depth: core
summary: >-
  An alphabet is a type of script with separate letters for both consonants and
  vowels.
related:
  - script
  - abugida
  - abjad
  - syllabary
  - featural-alphabet
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Alphabet'
    url: https://www.unicode.org/glossary/#alphabet
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Alphabet

## Definition

An alphabet is a type of [script](script.md) with separate letters for both consonants and vowels.<sup>1</sup> The [Latin](latin-script.md), [Greek](greek-script.md), and [Cyrillic](cyrillic.md) scripts are alphabets.

For example, the Russian word мир ("world") is written м, и, р: a consonant, a vowel, and a consonant, each its own letter.

Each letter stands for roughly one sound, and consonants and vowels alike get their own letters written in sequence. That sets an alphabet apart from an [abjad](abjad.md), where vowels are usually left unwritten,<sup>2</sup> and an [abugida](abugida.md), where each consonant carries a built-in vowel that added marks change.<sup>3</sup>

While this glossary doesn't cover every script, here are some alphabets to be aware of. Select a linked term to navigate to its glossary page.

| Script                         | Languages                            | Example |
| ------------------------------ | ------------------------------------ | ------- |
| [Armenian](armenian-script.md) | Armenian                             | Բարև (Barev): "hello" |
| [Cyrillic](cyrillic.md)        | Russian, Serbian, Ukrainian          | Здравствуйте (Zdravstvujte): "hello" (Russian) |
| [Georgian](georgian-script.md) | Georgian                             | გამარჯობა (gamarjoba): "hello" |
| [Greek](greek-script.md)       | Greek                                | Γεια σου (Ya su): "hello" |
| [Latin](latin-script.md)       | English, French, Spanish, Vietnamese | Hello   |

### Why it matters in design systems

Alphabets are the structure most interface and typeface tooling assumes by default, so it is easy to wrongly define "one letter per sound, in a line" as how all scripts work. However, it is one type of script among several, and "alphabet" is technically not fixed property of a script: it describes how a script is used for the writing system of a given language.

For example, the [Arabic script](../../terms/arabic-script.md) is an [abjad](abjad.md) when it writes Arabic, with short vowels omitted, but it works as an alphabet when it writes languages such as Kashmiri or Uyghur, where every vowel is written.<sup>4</sup>

So knowing that a script is being used as an alphabet is a starting point, not the whole picture.&#x20;

It does tell you the structure: both consonants and vowels are written as full letters, so [font coverage](../../terms/font-coverage.md) has to include the vowel letters and any [diacritic](diacritic.md) marks the language adds to them.&#x20;

It does not tell you the script behaves like the Latin alphabet: whether it has uppercase and lowercase, how its letters sort, and how they are spaced are all set by the individual script's [rules](script-rules.md) and the language's [orthography](orthography.md), and several alphabets have no letter case at all.&#x20;

Check the whole [writing system](writing-system.md), not just the fact that it is an alphabet, before you commit to a typeface or a layout.

***

### Related terms and mentions

[Abjad](abjad.md) · [Abugida](abugida.md) · [Arabic script](../../terms/arabic-script.md) · [Armenian script](armenian-script.md) · [Cyrillic](cyrillic.md) · [Diacritic](diacritic.md) · [Featural script](featural-alphabet.md) · [Font coverage](../../terms/font-coverage.md) · [Georgian script](georgian-script.md) · [Greek script](greek-script.md) · [Latin script](latin-script.md) · [Letter spacing](../../terms/letter-spacing.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Syllabary](syllabary.md) · [Typeface](../../terms/typeface.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Alphabet](https://www.unicode.org/glossary/#alphabet)

### Sources

1. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
2. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
3. An abugida's base letters carry an inherent vowel changed by additional marks - Unicode Glossary: Abugida [https://www.unicode.org/glossary/#abugida](https://www.unicode.org/glossary/#abugida)
4. "When this script is used to represent the Arabic language, short vowels diacritics are omitted. In that case, the Arabic script is referred to as an 'abjad'... when this script is used to write some other languages (such as Kashmiri, Uighur, and most African languages), all vowels are represented, including short vowels. The Arabic script is then an 'alphabet'." - W3C: An Introduction to Writing Systems & Unicode [https://www.w3.org/International/questions/qa-scripts](https://www.w3.org/International/questions/qa-scripts)
