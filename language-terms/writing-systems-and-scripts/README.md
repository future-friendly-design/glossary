# Writing systems & scripts

## What is a writing system

When a language evolves from spoken/signed to being written, its community develops a writing system for the language over time.

From a zoomed-out perspective, a writing system consists of:

* at least one script - the visual symbols used to write a language
* an orthography - the language-specific rules on how to use a script to write the language.

### Why it matters

When a written language is represented digitally, we can zoom in to the various parts of its writing system to understand how each part connects to typography.

The goal is to look at a part of a writing system, identify which typography properties it maps to, and make user-friendly decisions when working with text in a design system.

#### Example

For example, both French and Vietnamese languages use the Latin script in their writing systems. However, the orthography of each calls for differences in the marks used to modify the Latin symbols, which map to the line-height typographic property.

* French - one mark per letter
* Vietnamese - stacks multiple marks per letter

Stacked marks take up more vertical space on a letter. That extra height needs room between lines, which is what line height controls. That would mean a larger value for the line-height when working with the Vietnamese language compared to French.

***

### Script terms by topic

{% hint style="info" %}
This glossary does not support every script. Its coverage is limited to the examples and related terms that came up during the [SILCON](https://silicon.stanford.edu/) UX incubator that Sam, the founder of Future Friendly Designs, was teaching.&#x20;

If you've got a script or related term you'd like see added, head to the [contributing page](../../CONTRIBUTING.md) to learn more!
{% endhint %}



#### Anatomy of a writing system

A script is a part of a language-specific writing system. The orthography defines the rules on how to use that script to write a language.&#x20;

The same script can be used to write more than one language, and single language may have more than one script!

{% content-ref url="language.md" %}
[language.md](language.md)
{% endcontent-ref %}

{% content-ref url="orthography.md" %}
[orthography.md](orthography.md)
{% endcontent-ref %}

{% content-ref url="script.md" %}
[script.md](script.md)
{% endcontent-ref %}

{% content-ref url="writing-system.md" %}
[writing-system.md](writing-system.md)
{% endcontent-ref %}



#### Anatomy of a script

A script consists of the visual symbols and marks used to write a language and the rules on how to use the script.&#x20;

{% content-ref url="script.md" %}
[script.md](script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/symbol.md" %}
[symbol.md](../../terms/symbol.md)
{% endcontent-ref %}

{% content-ref url="../../terms/script-rules.md" %}
[script-rules.md](../../terms/script-rules.md)
{% endcontent-ref %}

{% content-ref url="mark.md" %}
[mark.md](mark.md)
{% endcontent-ref %}





#### Symbol terms

Symbol refers to the individual visual elements that make up a script. Scripts have different names for their symbols. For example, in a script classified as an alphabet, the symbols that represent vowels and consonants are called letters.&#x20;

{% content-ref url="../../terms/grapheme.md" %}
[grapheme.md](../../terms/grapheme.md)
{% endcontent-ref %}

{% content-ref url="../../terms/grapheme-cluster.md" %}
[grapheme-cluster.md](../../terms/grapheme-cluster.md)
{% endcontent-ref %}

{% content-ref url="../../terms/symbol.md" %}
[symbol.md](../../terms/symbol.md)
{% endcontent-ref %}



#### Mark terms

A mark is a symbol that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions.

These mark terms span across many scripts. Script specific marks are not listed here, see the script examples.&#x20;

{% content-ref url="../../terms/diacritic.md" %}
[diacritic.md](../../terms/diacritic.md)
{% endcontent-ref %}

{% content-ref url="../../terms/punctuation-mark.md" %}
[punctuation-mark.md](../../terms/punctuation-mark.md)
{% endcontent-ref %}

{% content-ref url="../../terms/tone-mark.md" %}
[tone-mark.md](../../terms/tone-mark.md)
{% endcontent-ref %}





#### Script rule terms

Script rules are the behaviors a script imposes on its own symbols and that applies to any language using the script in its writing system. For example, the latin script has a text direction rule of left-to-right. <br>

{% content-ref url="../../terms/bidirectional-text.md" %}
[bidirectional-text.md](../../terms/bidirectional-text.md)
{% endcontent-ref %}

{% content-ref url="../../terms/joining.md" %}
[joining.md](../../terms/joining.md)
{% endcontent-ref %}

{% content-ref url="../../terms/reph.md" %}
[reph.md](../../terms/reph.md)
{% endcontent-ref %}

{% content-ref url="../../terms/script-rules.md" %}
[script-rules.md](../../terms/script-rules.md)
{% endcontent-ref %}

{% content-ref url="../../terms/stacking-script.md" %}
[stacking-script.md](../../terms/stacking-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/tategaki.md" %}
[tategaki.md](../../terms/tategaki.md)
{% endcontent-ref %}

{% content-ref url="../../terms/text-direction.md" %}
[text-direction.md](../../terms/text-direction.md)
{% endcontent-ref %}



#### Script classification terms&#x20;

Scripts are classified by what their symbols represent. For example, if a script is to be classified as an alphabet, it must have separate symbols (called letters) representing consonants and vowels.&#x20;

{% content-ref url="../../terms/abjad.md" %}
[abjad.md](../../terms/abjad.md)
{% endcontent-ref %}

{% content-ref url="../../terms/abugida.md" %}
[abugida.md](../../terms/abugida.md)
{% endcontent-ref %}

{% content-ref url="../../terms/alphabet.md" %}
[alphabet.md](../../terms/alphabet.md)
{% endcontent-ref %}

{% content-ref url="../../terms/alphasyllabary.md" %}
[alphasyllabary.md](../../terms/alphasyllabary.md)
{% endcontent-ref %}

{% content-ref url="../../terms/brahmic-scripts.md" %}
[brahmic-scripts.md](../../terms/brahmic-scripts.md)
{% endcontent-ref %}

{% content-ref url="../../terms/cjk.md" %}
[cjk.md](../../terms/cjk.md)
{% endcontent-ref %}

{% content-ref url="../../terms/featural-alphabet.md" %}
[featural-alphabet.md](../../terms/featural-alphabet.md)
{% endcontent-ref %}

{% content-ref url="../../terms/ideographic.md" %}
[ideographic.md](../../terms/ideographic.md)
{% endcontent-ref %}

{% content-ref url="../../terms/logographic.md" %}
[logographic.md](../../terms/logographic.md)
{% endcontent-ref %}

{% content-ref url="../../terms/logosyllabary.md" %}
[logosyllabary.md](../../terms/logosyllabary.md)
{% endcontent-ref %}

{% content-ref url="../../terms/pictographic.md" %}
[pictographic.md](../../terms/pictographic.md)
{% endcontent-ref %}

{% content-ref url="../../terms/syllabary.md" %}
[syllabary.md](../../terms/syllabary.md)
{% endcontent-ref %}



### Scripts to explore

Now that you understand what scripts are and how they work, you can explore these scripts to learn more about its symbols, marks and rules:

Abjad scripts:

{% content-ref url="../../terms/arabic-script.md" %}
[arabic-script.md](../../terms/arabic-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/hebrew-script.md" %}
[hebrew-script.md](../../terms/hebrew-script.md)
{% endcontent-ref %}

Abugida scripts:

{% content-ref url="../../terms/bengali-assamese.md" %}
[bengali-assamese.md](../../terms/bengali-assamese.md)
{% endcontent-ref %}

{% content-ref url="../../terms/canadian-aboriginal-syllabics.md" %}
[canadian-aboriginal-syllabics.md](../../terms/canadian-aboriginal-syllabics.md)
{% endcontent-ref %}

{% content-ref url="../../terms/devanagari.md" %}
[devanagari.md](../../terms/devanagari.md)
{% endcontent-ref %}

{% content-ref url="../../terms/ethiopic-script.md" %}
[ethiopic-script.md](../../terms/ethiopic-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/syloti-nagri.md" %}
[syloti-nagri.md](../../terms/syloti-nagri.md)
{% endcontent-ref %}

{% content-ref url="../../terms/tamil-script.md" %}
[tamil-script.md](../../terms/tamil-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/thai-script.md" %}
[thai-script.md](../../terms/thai-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/tibetan-script.md" %}
[tibetan-script.md](../../terms/tibetan-script.md)
{% endcontent-ref %}

Alphabet scripts:

{% content-ref url="../../terms/armenian-script.md" %}
[armenian-script.md](../../terms/armenian-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/cyrillic.md" %}
[cyrillic.md](../../terms/cyrillic.md)
{% endcontent-ref %}

{% content-ref url="../../terms/georgian-script.md" %}
[georgian-script.md](../../terms/georgian-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/greek-script.md" %}
[greek-script.md](../../terms/greek-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/latin-script.md" %}
[latin-script.md](../../terms/latin-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/mongolian-script.md" %}
[mongolian-script.md](../../terms/mongolian-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/ol-chiki.md" %}
[ol-chiki.md](../../terms/ol-chiki.md)
{% endcontent-ref %}

{% content-ref url="../../terms/wancho-script.md" %}
[wancho-script.md](../../terms/wancho-script.md)
{% endcontent-ref %}

{% content-ref url="../../terms/warang-citi.md" %}
[warang-citi.md](../../terms/warang-citi.md)
{% endcontent-ref %}

Featural scripts:

{% content-ref url="../../terms/hangul.md" %}
[hangul.md](../../terms/hangul.md)
{% endcontent-ref %}

Logographic scripts:

{% content-ref url="../../terms/han-characters.md" %}
[han-characters.md](../../terms/han-characters.md)
{% endcontent-ref %}

Syllabary scripts:

{% content-ref url="../../terms/hiragana.md" %}
[hiragana.md](../../terms/hiragana.md)
{% endcontent-ref %}

{% content-ref url="../../terms/katakana.md" %}
[katakana.md](../../terms/katakana.md)
{% endcontent-ref %}
