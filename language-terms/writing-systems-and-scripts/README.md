# Writing systems & script terms

## What is a writing system

When a language evolves from spoken/signed to being written, its community develops a writing system for the language over time.

From a zoomed-out perspective, a writing system consists of:

* at least one script - the visual symbols used to write a language
* an orthography - the language-specific rules on how to use a script to write the language.

When a written language is represented digitally, we can zoom in to the various parts of its writing system to understand how each part connects to typography.

### Why it matters

The goal is to look at a part of a writing system, identify which typography properties it maps to, and make user-friendly decisions when working with text in a design system.

#### Example

For example, both French and Vietnamese languages use the Latin script in their writing systems. However, the orthography of each calls for differences in the marks used to modify the Latin symbols, which map to the line-height typographic property.

* French - one mark per letter
* Vietnamese - stacks multiple marks per letter

Stacked marks take up more vertical space on a letter. That extra height needs room between lines, which is what line height controls. That would mean a larger value for the line-height when working with the Vietnamese language compared to French.

***

### Script terms by topic

{% hint style="info" %}
This glossary does not support every script. Its coverage is limited to the examples and related terms that came up during the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching.

If you've got a script or related term you'd like see added, head to the [contributing page](../../CONTRIBUTING.md) to learn more!
{% endhint %}

#### Anatomy of a writing system

A script is a part of a language-specific writing system. The orthography defines the rules on how to use that script to write a language.

The same script can be used to write more than one language, and a single language may have more than one script.

* [Language](../linguistics/language.md)
* [Orthography](orthography.md)
* [Script](script.md)
* [Writing system](writing-system.md)

#### Anatomy of a script

A script consists of the visual symbols and marks used to write a language, plus the rules on how to use them.

* [Mark](mark.md)
* [Script](script.md)
* [Script rules](script-rules.md)
* [Symbol](symbol.md)

#### Symbol terms

A symbol is an individual visual element that makes up a script. Scripts have different names for their symbols. For example, in a script classified as an alphabet, the symbols that represent vowels and consonants are called letters.

* [Grapheme](../../programming-terms/text-for-digital-products-and-the-web/grapheme.md)
* [Grapheme cluster](../../programming-terms/text-for-digital-products-and-the-web/grapheme-cluster.md)
* [Symbol](symbol.md)

#### Mark terms

A mark is a kind of [symbol](symbol.md) that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions. Some marks are general across scripts, like the [diacritic](diacritic.md) and the [tone mark](tone-mark.md). Others recur across a whole script family: the [matra](matra.md), [virama](virama.md), and [nukta](nukta.md) belong to the Brahmic scripts, and the [harakat](harakat.md) to the Arabic script. A mark used by only a single script is found on that script's page rather than listed here.

* [Diacritic](diacritic.md)
* [Harakat](harakat.md)
* [Matra](matra.md)
* [Nukta](nukta.md)
* [Punctuation mark](punctuation-mark.md)
* [Tone mark](tone-mark.md)
* [Virama](virama.md)

One of these shares the word but not the sense. A [punctuation mark](punctuation-mark.md) stands alone instead of modifying another symbol, so [Unicode](../../programming-terms/text-for-digital-products-and-the-web/unicode.md) files it under punctuation, not marks. It is listed here because it carries the word "mark", not because it works like one.

#### Script rules and features

Script rules define how a script's symbols behave: how they combine, connect, stack, or run. Some are general, like which [direction](text-direction.md) the script runs or whether its letters [join](joining.md). Others are features of particular scripts or families: the Brahmic [conjunct](conjunct.md), [reph](reph.md), and headline [shirorekha](shirorekha.md), or the Tibetan syllable-marking [tsheg](tsheg.md). For example, the Latin script runs [left to right](left-to-right.md), while Devanagari hangs its letters from a [shirorekha](shirorekha.md) and reorders some of its vowel marks.

* [Bidirectional text](bidirectional-text.md)
* [Conjunct](conjunct.md)
* [Hanging baseline](hanging-baseline.md)
* [Joining](joining.md)
* [Left-to-right (LTR)](left-to-right.md)
* [Reph](reph.md)
* [Right-to-left (RTL)](right-to-left.md)
* [Script rules](script-rules.md)
* [Shirorekha](shirorekha.md)
* [Stacking script](stacking-script.md)
* [Tategaki](tategaki.md)
* [Text direction](text-direction.md)
* [Tsheg](tsheg.md)
* [Vertical text](../../terms/vertical-text.md)

#### Script classifications

Scripts are classified by what their symbols represent. Most sit on a spectrum of how much of a syllable each symbol carries: an [alphabet](alphabet.md) gives consonants and vowels their own separate symbols; an [abjad](abjad.md) writes the consonants and leaves most vowels for the reader to supply; an [abugida](abugida.md) gives every consonant a built-in vowel that added marks change; and a [syllabary](syllabary.md) uses one symbol for a whole syllable. Cutting across that spectrum, a [featural](featural-alphabet.md) script shapes its symbols to mirror the sounds they make, so a script can be featural and also, say, a syllabary. A separate branch classifies by meaning rather than sound: a [logographic](logographic.md) script's symbols stand for words or morphemes, with [ideographic](ideographic.md) and [pictographic](pictographic.md) as symbol-level categories and [logosyllabary](logosyllabary.md) the more precise label for Han. [Alphasyllabary](alphasyllabary.md) is another name for an abugida.

* [Abjad](abjad.md)
* [Abugida](abugida.md)
* [Alphabet](alphabet.md)
* [Alphasyllabary](alphasyllabary.md)
* [Featural script](featural-alphabet.md)
* [Ideographic](ideographic.md)
* [Logographic](logographic.md)
* [Logosyllabary](logosyllabary.md)
* [Pictographic](pictographic.md)
* [Syllabary](syllabary.md)

#### Script families and groupings

Some scripts are grouped not by how their symbols work but by shared ancestry or regional use. A grouping tells you what infrastructure transfers between its members, but the members still differ, so verify per script, not by family.

* [Brahmic scripts](brahmic-scripts.md): a large family of related [abugidas](abugida.md) descended from the ancient Brahmi script, spanning South and Southeast Asia.
* [CJK](cjk.md): a regional and typographic grouping of the Chinese, Japanese, and Korean writing systems, which share Han characters and are set together in software.

### Scripts to explore

Now that you understand what scripts are and how they work, you can explore these scripts, organized by classification, to learn more about their symbols, marks, and rules.

#### Abjad scripts

* [Arabic script](arabic-script.md)
* [Hebrew script](hebrew-script.md)

#### Abugida scripts

* [Bengali-Assamese script](bengali-assamese.md)
* [Devanagari script](devanagari.md)
* [Ethiopic script](ethiopic-script.md)
* [Syloti Nagri script](syloti-nagri.md)
* [Tamil script](tamil-script.md)
* [Thai script](thai-script.md)
* [Tibetan script](tibetan-script.md)

#### Alphabet scripts

* [Armenian script](armenian-script.md)
* [Cyrillic script](cyrillic.md)
* [Georgian script](georgian-script.md)
* [Greek script](greek-script.md)
* [Latin script](latin-script.md)
* [Mongolian script (traditional)](mongolian-script.md)
* [Ol Chiki script](ol-chiki.md)
* [Wancho script](wancho-script.md)
* [Warang Citi script](warang-citi.md)

#### Featural scripts

* [Hangul script](hangul.md)

#### Logographic scripts

* [Han characters script](han-characters.md)

#### Syllabary scripts

* [Canadian Aboriginal Syllabics script](canadian-aboriginal-syllabics.md)
* [Hiragana script](hiragana.md)
* [Katakana script](katakana.md)
