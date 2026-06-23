# Writing systems & scripts

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

The same script can be used to write more than one language, and single language may have more than one script!

* [Language](../linguistics/language.md)
* [Orthography](orthography.md)
* [Script](script.md)
* [Writing system](writing-system.md)

#### Anatomy of a script

A script consists of the visual symbols and marks used to write a language and the rules on how to use the script.

* [Script](script.md)
* [Symbol](../../terms/symbol.md)
* [Script rules](../../terms/script-rules.md)
* [Mark](mark.md)

#### Symbol terms

Symbol refers to the individual visual elements that make up a script. Scripts have different names for their symbols. For example, in a script classified as an alphabet, the symbols that represent vowels and consonants are called letters.

* [Grapheme](../../terms/grapheme.md)
* [Grapheme cluster](../../terms/grapheme-cluster.md)
* [Symbol](../../terms/symbol.md)

#### Mark terms

A mark is a symbol that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions.

These mark terms span across many scripts. Script specific marks are not listed here, see the script examples.

* [Diacritic](../../terms/diacritic.md)
* [Punctuation mark](../../terms/punctuation-mark.md)
* [Tone mark](../../terms/tone-mark.md)

#### Script rule terms

Script rules are the behaviors a script imposes on its own symbols and that applies to any language using the script in its writing system. For example, the latin script has a text direction rule of left-to-right.<br>

* [Bidirectional text](../../terms/bidirectional-text.md)
* [Joining](../../terms/joining.md)
* [Reph](../../terms/reph.md)
* [Script rules](../../terms/script-rules.md)
* [Stacking script](../../terms/stacking-script.md)
* [Tategaki](../../terms/tategaki.md)
* [Text direction](../../terms/text-direction.md)

#### Script classification terms

Scripts are classified by what their symbols represent. For example, if a script is to be classified as an alphabet, it must have separate symbols (called letters) representing consonants and vowels.

* [Abjad](../../terms/abjad.md)
* [Abugida](../../terms/abugida.md)
* [Alphabet](../../terms/alphabet.md)
* [Alphasyllabary](../../terms/alphasyllabary.md)
* [Brahmic scripts](../../terms/brahmic-scripts.md)
* [CJK](../../terms/cjk.md)
* [Featural alphabet](../../terms/featural-alphabet.md)
* [Ideographic](../../terms/ideographic.md)
* [Logographic](../../terms/logographic.md)
* [Logosyllabary](../../terms/logosyllabary.md)
* [Pictographic](../../terms/pictographic.md)
* [Syllabary](../../terms/syllabary.md)

### Scripts to explore

Now that you understand what scripts are and how they work, you can explore these scripts to learn more about its symbols, marks and rules:

#### Abjad scripts:

* [Arabic script](../../terms/arabic-script.md)
* [Hebrew script](../../terms/hebrew-script.md)

#### Abugida scripts:

* [Bengali-Assamese](../../terms/bengali-assamese.md)
* [Canadian Aboriginal Syllabics](../../terms/canadian-aboriginal-syllabics.md)
* [Devanagari](../../terms/devanagari.md)
* [Ethiopic script](../../terms/ethiopic-script.md)
* [Syloti Nagri](../../terms/syloti-nagri.md)
* [Tamil script](../../terms/tamil-script.md)
* [Thai script](../../terms/thai-script.md)
* [Tibetan script](../../terms/tibetan-script.md)

#### Alphabet scripts:

* [Armenian script](../../terms/armenian-script.md)
* [Cyrillic](../../terms/cyrillic.md)
* [Georgian script](../../terms/georgian-script.md)
* [Greek script](../../terms/greek-script.md)
* [Latin script](../../terms/latin-script.md)
* [Mongolian script (traditional)](../../terms/mongolian-script.md)
* [Ol Chiki](../../terms/ol-chiki.md)
* [Wancho script](../../terms/wancho-script.md)
* [Warang Citi](../../terms/warang-citi.md)

#### Featural scripts:

* [Hangul](../../terms/hangul.md)

#### Logographic scripts:

* [Han characters](../../terms/han-characters.md)

#### Syllabary scripts:

* [Hiragana](../../terms/hiragana.md)
* [Katakana](../../terms/katakana.md)
