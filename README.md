# US International Scientific Keyboard Layout
__A very powerful keyboard layout for Windows, tailored for efficient and convenient input of international Latin languages and scientific notation in plain text.__

![overview](/assets/keyboard-layout.png)

- [Quick Start Guide](#quick-start-guide)
- [Update / Uninstallation Guide](#update--uninstallation-guide)
- [Must-know Concepts](#must-know-concepts)
	- [Dead keys](#dead-keys)
	- [Shift states and AltGr](#shift-states-and-altgr)
- [Overview of Key Mappings](#overview-of-key-mappings)
- [Core Design Ideas](#core-design-ideas)
- [Key Mappings](#key-mappings)
	- [Numeric row](#numeric-row)
	- [QWERTY row](#qwerty-row)
	- [ASDF row](#asdf-row)
	- [ZXCV row](#zxcv-row)
	- [Space bar](#space-bar)
- [Dead Key Secondary Mappings](#dead-key-secondary-mappings)
	- [Modified Latin letters](#modified-latin-letters)
	- [Mathematical alphanumeric symbols](#mathematical-alphanumeric-symbols)
	- [Mathematical operators](#mathematical-operators)
- [Comparison to Other Layouts](#comparison-to-other-layouts)
- [Notes on MSKLC 1.4](#notes-on-msklc-14)



This keyboard layout is easy to install, easy to use, and easy to memorize, while having extensive capabilities covering common Latin letters, diacritics, mathematical symbols, additional punctuation, and some mathematical font letters. It is recommended for those who often work in __STEM__ fields on a __Windows__ system, and have collaborations with co-workers from __diverse language backgrounds__. It is also intended as a better alternative to the United States-International keyboard layout that had dead keys inconveniently bound on commonly used keys. 

> **Note:** This keyboard layout is **not a replacement for proper scientific notation** that can be formatted using rich-text programs like $\LaTeX$, UnicodeMath, or MathML, but rather a method to extend the symbols available in plain text input scenarios, e.g. texting on Discord, using Notepad, or non-technical writing.

This keyboard layout was created using [Microsoft Keyboard Layout Creator 1.4](https://www.microsoft.com/en-us/download/details.aspx?id=102134) (MSKLC 1.4). The layout is based on the common __English (United States) QWERTY keyboard layout__, and some designs are consistent with the __United States-International keyboard layout__. Other ideas were inspired by and improved on the basis of [Michael Goerz's version](https://michaelgoerz.net/notes/the-us-international-scientific-keyboard-layout/index.html) of the "U.S. International - Scientific" keyboard layout for Mac systems. 

A detailed comparison chart of this keyboard layout with other layouts can be found in [this section](#comparison-to-other-layouts). A previous version of this layout (v1.5.1) could also be found on the [Keyboard Layout Info website](https://kbdlayout.info/KBDUSS5a/). Special thanks to Mr. Jan Kučera from the Czech Republic for creating the dedicated page and the entire highly useful website! 

## Quick Start Guide
Setting up this keyboard on your computer is very simple! 
> **Note:** Be logged in to an Administrator account on your computer. Configuring the keyboard will require Administrator permission. 
1. Download [the latest release](https://github.com/BelugaHaechi/US-International-Scientific-Keyboard/releases/latest) to any directory on your computer.
	> **Note:** Releases are named as `KBDUSS` + major version number + minor version letter. We will use `KBDUSS**` to represent this below. This naming system is in conformity with system files in `C:\Windows\System32\KBD*.dll`. From version 1.6.0, you can also view the current version of the installed layout conveniently, just by checking the layout name on the taskbar.
2. Open the folder, and run the program `setup.exe` in the folder. Do not alter or delete any other files in the folder. 
3. Follow the setup instructions that will pop up. At some point, you will be asked for Administrator permission; please allow to continue.
	>**Note:** Security warnings from Windows Defender should appear, because the executable for this program does not have digital certification yet. The author promises that it is **safe** to continue execution for this project (the option will appear when "More Info" is clicked), but in general *do not easily trust uncertified executables* as they could be potentially very harmful. Please make sure the executable you have obtained is from this repository. 
4. Now the keyboard is installed on your computer! The last step is to enable the layout in Settings.
	- Open Settings on your computer.
	- Navigate to `Time & language > Language & region > Keyboards` (this may differ slightly for various Windows versions).
	- Select `Add a keyboard`, and select `US-International and Scientific keyboard` in the drop-down menu.
	- (_Optional_) You can now disable the original `US keyboard (QWERTY)`, since its functions could be completely replaced by the new keyboard.
	- Restart your computer. This often helps to finalize the installation (#25).
5. Congratulations! You are now all set to use the US International Scientific keyboard on your computer.

> **Tip:** You may wish to retain the `KBDUSS**` folder, because it could be used to repair/uninstall the keyboard layout on your computer.

## Update / Uninstallation Guide
Uninstallation of the keyboard layout is also simple. You may wish to do so, if:
1. There is a new version of the keyboard available, and you will need to uninstall the previous version before installing the new one. Yes, minor improvements may be made to the layout upon request, feel free to post your ideas in Issues!
2. The keyboard layout doesn't work as intended on your device. If so, you may wish to reinstall the layout.
3. You wish to discard the layout for any reason :(

To uninstall the keyboard layout, simply revisit the `KBDUSS**` folder, and run `setup.exe` again. This time you would be prompted to repair or uninstall the keyboard layout, and select the action as you wish. Administrator permission may be required again. You may need to restart your computer for changes to take effect. 

> **Known issue:** Possibly due to a Windows system bug, sometimes on uninstallation the keyboard layout will not be compeletely removed, where the name of the layout is still retained in the keyboard layout list in computer settings. If you try to add this layout to your input methods, it cannot appear in the input methods list for actual use. 
> 
> In other words, only a "ghost" placeholder of the layout will remain in the list. In the system files the keyboard layout's `.dll` configuration is deleted, but it is still present in the registry. 
> 
> To solve this issue, navigate in the Registry Editor to `Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layouts`, and manually delete the registry folder for this layout (usually called `a0000409`). Always backup the registry before making changes, in case of causing serious errors!   

## Must-know Concepts
The US International Scientific keyboard layout utilizes two important concepts to achieve its unparalleled functionality: **dead keys** and the **AltGr shift state**. These concepts, common in Europeah keyboard layouts, are explained below for those unfamiliar with them. 

### Dead keys
When a normal key is pressed, a character is returned. However, [**dead keys**](https://en.wikipedia.org/wiki/Dead_key) do not return a character when initially pressed, but rather waits for the next keystroke and uses this input to determine the character it should return. This essentially enables a key to be mapped to multiple characters, for example key <kbd>\`</kbd> (backtick) could be mapped to all characters with an acute accent: à, ù, ì, À, Ù, Ì, and so on. To type letter "à", one would need to press <kbd>\`</kbd> then <kbd>a</kbd>. 

The character corresponding to the first keystroke (also the dead key itself) is called the **root character**, the character for the second keystroke is called the **base character**, and the returned character is called the **composite character**. If the root character does not map to a composite character in the dead key's character set, the root character of the dead key is returned, followed by the base character. 

By convention, the set of characters mapped to a dead key should share similar features, and also with the root character. It is also conventional to always have the <kbd>Space</kbd> key mapped to the **default character** of a dead key, usually the root character in isolation. 

Dead keys are used extensively in many modern keyboard layouts, such as in the Greek Polytonic layout, the US-International layout, the UK Extended layout, and so on. 

### Shift states and AltGr
**Shift state** is a term for the layers of a keyboard layout, that could be interchanged by the state of control keys (<kbd>Shift</kbd>, <kbd>Alt</kbd>, <kbd>Ctrl</kbd>). We normally use two shift states: the blank shift state, and the Shift shift state. In fact, there are extra shift states arising from the combinations of the 3 control keys. Among the most well known are the Alt + Ctrl and Alt + Ctrl + Shift shift states, commonly referred to as the **AltGr shift states** because they are accessed by holding the <kbd>AltGr</kbd> (short for Alternative Graphics) key on European keyboards. On keyboards without <kbd>AltGr</kbd>, hold the **Right <kbd>Alt</kbd> key** to access these shift states; holding down both <kbd>Alt</kbd> and <kbd>Ctrl</kbd> keys is also valid. <kbd>AltGr</kbd> expands a keyboard layout to twice the original size, enabling the addition of new functions. 

Shift states with only <kbd>Alt</kbd> or <kbd>Ctrl</kbd> are mostly unused in keyboard layouts, because these key combinations are reserved for hotkeys (keyboard shortcuts). 

In the US International Scientific keyboard layout, the key mappings in the normal shift states are identical to that in the common English (United States) QWERTY keyboard layout. Thus, without <kbd>AltGr</kbd>, it is just a normal layout; this feature is intended to make the transition to this layout extremely easy. All extra functionalities are carefully designed into the AltGr shift states, along with usage of dead keys.  

## Overview of Key Mappings
Below is a figure of the US International Scientific keyboard layout, made by [this tool](http://www.keyboard-layout-editor.com/#/) (also [on Github](https://github.com/ijprest/keyboard-layout-editor)). This figure may be greatly helpful as a reference to the functionalities of this keyboard layout. 

**Legend**

⚫ _Black:_ Normal keys. When pressed, returns the character shown. 

🔴 _Red:_ Dead keys. When pressed, waits for a second keystroke, then returns a character based on the second keystroke. 

🟣 _Purple:_ Dead keys, but due to restraints its root character does not well represent the set of characters mapped to the dead key. The former character in this representation is the root character, the latter is the default character. 

🟥 _Red keycaps:_ At least one of the key's shift states is set as a dead key. 

🟦 _Blue keycaps:_ The key is used to control the shift states relevant to this layout. 

![overview](/assets/keyboard-layout.png)

For details on the meaning and justification of each key-character mapping, please see [this section](#key-mappings). 

For details on the secondary mappings of dead keys, please jump to [this section](#dead-key-secondary-mappings). 

## Core Design Ideas
1. __Complete compatibility with plain keyboards.__ _The US QWERTY keyboard layout remains unchanged_, and all extensions are "hidden" in the AltGr (<kbd>Alt</kbd> + <kbd>Ctrl</kbd>) and AltGr + Shift (<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd>) shift states. Therefore it will be just an ordinary layout under normal use, and fits with its positioning as a "keyboard extension".   
Also, key mappings from the original United States-International keyboard are retained whenever appropriate (denoted as `USX` in this documentation), so that it aligns with Microsoft design and users switching over will find it more familiar to work with. 

1. __Consistent logicality of key mappings.__ Every key mapping should always _make as much sense as possible_ and provide convenience for both multilingual and mathematical input. Every reason for a certain mapping should be explicitly documented, and alternatives should be discussed if any. 
   - At least one among name, shape, usage, etc. of the character allocated should be related with the key that it is mapped to. 
   - Common characters should be easy to access, while uncommon characters should be set further out of reach, and rare and awkward characters should be avoided. 
   - Characters of the same type should have similar shift states, when possible.

2. __Compact organization by using dead keys.__ Multiple characters that share an obvious characteristic (best shown in its Unicode naming or block) should be considered to be included in a [dead key](https://en.wikipedia.org/wiki/Dead_key). Dead keys will be highlighted with a bold notice, and the mappings should be fully provided for reference. 
   - Dead key root characters should be chosen with the same criteria as normal characters. 
   - If the common characteristic is a diacritic, the root character should be the combining diacritic for versatility. If it is not, it should be meaningful as a fallback, or another related character (this is the hard part!). 
   - In dead key mappings, the final base character should be a space (U+0020) that maps to: 1) if diacritic, the diacritic itself alone (modifier letter); 2) if else, the most common character among all options. This is the default character. 
   - The dead key should provide access to this class of characters to the maximum extent, except for those that are rarely used. 

3. __Maximum flexibility under system restraints.__ Due to the restrictions imposed explicitly and implicitly, by MSKLC 1.4, Microsoft frameworks, and related bugs, the scope of design and functionality of this keyboard layout is somewhat restricted. However, under these restrictions, the design will strive to include the most functionality possible without causing compatibility issues. 
   - Mathematical Greek letters are fully supported as in §2.2 of [Unicode® Technical Report #25: Unicode Support For Mathematics](https://www.unicode.org/reports/tr25/).
   - **The range of Unicode characters included is limited. All output only include one character or code point. All output characters are within the Basic Multilingual Plane (BMP) of Unicode (U+0000–U+FFFF). All dead key root characters are within U+0000–U+0FFF.** Currently most characters are within U+0000–U+2FFF. 
   - Customization is not imposed on control keys, numpad, arrow keys, and function keys. 
   - Dead keys are not chained, and all base characters are available in the normal and Shift shift states. 
   - Shift states only include normal, Shift, AltGr, and Shift+AltGr. Excluded states include Ctrl, Ctrl+Shift, SGCaps (<kbd>CapsLock</kbd>), and so on.

## Key Mappings
Below is a detailed documentation on the complete set of key mappings for the US International Scientific keyboard layout, including specific descriptions of the characters selected and the corresponding justifications. 
### Numeric row
#### AltGr shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>\`</kbd>|`   |U+0300|COMBINING GRAVE ACCENT|**Dead key: characters with the grave accent diacritic.** Shape similar to U+0060 GRAVE ACCENT (backtick). Retained from USX layout. |
|<kbd>1</kbd>|′   |U+2032|PRIME|Math: first (1) derivative. |
|<kbd>2</kbd>|″   |U+2033|DOUBLE PRIME|Math: second (2) derivative. |
|<kbd>3</kbd>|‴   |U+2034|TRIPLE PRIME|Math: third (3) derivative. |
|<kbd>4</kbd>|¤   |U+00A4|CURRENCY SIGN|Retained from USX layout. Related to the Shift shift state mapping of U+0024 DOLLAR SIGN. |
|<kbd>5</kbd>|€   |U+20AC|EURO SIGN|Retained from USX layout. Near other currency characters. |
|<kbd>6</kbd>|ˇ   |U+030C|COMBINING CARON|**Dead key: characters with the caron diacritic.** Mirror image of U+0302 COMBINING CIRCUMFLEX ACCENT. |
|<kbd>7</kbd>|⃗   |U+20D7|COMBINING RIGHT ARROW ABOVE|Physics: vector notation. Shape of 7 similar to right arrow. Near other combining diacritical marks. |
|<kbd>8</kbd>|∞   |U+221E|INFINITY|Math. Shape similar to a turned 8. |
|<kbd>9</kbd>|∝   |U+221D|PROPORTIONAL TO|Math. Near U+221E INFINITY. Shape similar to a turned 9, or a turned 8 with an opening. |
|<kbd>0</kbd>|°   |U+030A|COMBINING RING ABOVE|**Dead key: characters with a ring above, expanded to related non-math symbols.** Shape similar to 0, also the key is positioned at the top of the keyboard (Thus mapping to key <kbd>0</kbd> is prioritized over <kbd>O</kbd>). |
|<kbd>-</kbd>|–   |U+2013|EN DASH|Punctuation: commonly used as the dash indicating ranges of numbers. Shorter than U+2014 EM DASH, so mapped to the hyphen which is shorter than the underscore. |
|<kbd>=</kbd>|ª   |U+00AA|FEMININE ORDINAL INDICATOR|**Dead key: subscript characters.** Conventionally, the hotkey for subscripts is <kbd>Ctrl</kbd> + <kbd>=</kbd> in rich text programms such as MS Word. Also, Unicode provides a full set of subscripts for numbers, which relates to the position of this key (at the top of the keyboard). **Root character and default character** is U+00AA FEMININE ORDINAL INDICATOR in pair with U+00BA MASCULINE ORDINAL INDICATOR, because they are essentially superscripts. |

#### AltGr + Shift shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>~</kbd>|˜   |U+0303|COMBINING TILDE|**Dead key: characters with the tilde diacritic, extended to similar math equality symbols.** Shape similar to U+007E TILDE. Retained from USX layout. |
|<kbd>!</kbd>|¡   |U+00A1|INVERTED EXCLAMATION MARK|Punctuation: used to begin exclamations in Spanish languages. Partially retained from USX layout, changed shift state for better accordance with U+0021 EXCLAMATION MARK. |
|<kbd>@</kbd>|√   |U+221A|SQUARE ROOT|Math: second (2) root. |
|<kbd>#</kbd>|∛   |U+221B|CUBE ROOT|Math: third (3) root. |
|<kbd>$</kbd>|£   |U+00A3|POUND SIGN|Retained from USX layout. Near other currency characters. |
|<kbd>%</kbd>|‰   |U+2030|PER MILLE SIGN|Shape and usage similar to U+0025 PERCENT SIGN on the same key. |
|<kbd>^</kbd>|ˆ   |U+0302|COMBINING CIRCUMFLEX ACCENT|**Dead key: characters with the circumflex diacritic.** Shape similar to U+005E CIRCUMFLEX ACCENT on the same key. Retained from USX layout. |
|<kbd>&</kbd>|¦   |U+00A6|BROKEN BAR|**Dead key: ligatures, extended to miscellaenous North European letters.** Usage of U+0026 AMPERSAND related to the fact that ligatures are joined characters. **Root character** is U+00A6 BROKEN BAR because 1) there is no valid and representative character in the set of ligatures, 2) it is an important character also covered in the USX layout, and 3) its shape suggests the idea of joining two objects. **Default character** is U+200D ZERO WIDTH JOINER, commonly used to compose composite graphemes, especially in emojis. |
|‍<kbd>*</kbd>|̇   |U+0307|COMBINING DOT ABOVE OPERATOR|**Dead key: characters with the overdot diacritic.** Shape indicates a dot-like mark raised above. |
|<kbd>(</kbd>|⟨   |U+27E8|MATHEMATICAL LEFT ANGLE BRACKET|Physics: Bra-ket notation left bound. Shape and usage similar to U+0028 LEFT PARENTHESIS. |
|<kbd>)</kbd>|⟩   |U+27E9|MATHEMATICAL RIGHT ANGLE BRACKET|Physics: Bra-ket notation right bound. Shape and usage similar to U+0029 RIGHT PARENTHESIS. |
|<kbd>_</kbd>|—   |U+2013|EM DASH|Punctuation: commonly used as the dash indicating breaks in sentences. Longer than U+2014 EM DASH, so mapped to the underscore which is longer than the hyphen. |
|<kbd>+</kbd>|º   |U+00BA|MASCULINE ORDINAL INDICATOR|**Dead key: superscript characters.** Conventionally, the hotkey for subscripts is <kbd>Ctrl</kbd> + <kbd>+</kbd> in rich text programms such as MS Word. Also, Unicode provides a full set of subscripts for numbers, which relates to the position of this key (at the top of the keyboard). **Root character and default character** is U+00BA MASCULINE ORDINAL INDICATOR in pair with U+00AA FEMININE ORDINAL INDICATOR, because they are essentially superscripts. |

#### Notes
1. There exists U+2057 QUADRUPLE PRIME and U+221C FOURTH ROOT as candidates for key <kbd>4</kbd>, but they were not chosen because 1) these characters are rarely used (we live in a 3-dimensional world), and 2) there exists reasonable USX layout options to retain (which were used in this layout).
2. The superscripts and subscripts provided are limited intentionally by Unicode, in a way that not every letter in the alphabet has one. Most of these mini letters were coded in the first place for IPA phonetics! It is suggested to always use rich text to achieve such styles for normal text, and this keyboard layout provides these choices only to aid in plain text communication. 
3. For keys <kbd>=</kbd> and <kbd>+</kbd>, for the pair of characters U+00BA MASCULINE ORDINAL INDICATOR and U+00AA FEMININE ORDINAL INDICATOR, the decision to map the former to the shifted shift state was based on the fact that masculinity is usually associated with outgoing character. Here no bias on gender or sex is intended; it is thoroughly acknowledged that females could express masculinity and vice versa, and there are other gender identities apart from the binary system.  


### QWERTY row
#### AltGr shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>q</kbd>|÷   |U+00F7|DIVISION SIGN|Math. The result of division, quotient, starts with the letter "q". Has same shift state as U+00D7 MULTIPLICATION SIGN (mapped to key <kbd>x</kbd>), another common math operator. |
|<kbd>w</kbd>|ϵ   |U+03F5|GREEK LUNATE EPSILON SYMBOL|Shape similar to a turned "w". Key <kbd>e</kbd> is reserved for "element of"-related (set membership) symbols. |
|<kbd>e</kbd>|϶   |U+03F6|GREEK REVERSED LUNATE EPSILON SYMBOL|**Dead key: set membership math symbols.** **Root character** has a shape similar to a reversed "e", and is near its mirror image U+03F5 GREEK LUNATE EPSILON SYMBOL. **Default character** is U+2208 ELEMENT OF, which starts with the letter "e". |
|<kbd>r</kbd>|®   |U+00AE|REGISTERED SIGN|Retained from USX layout. Shape includes letter "R". Shift state same as ℗ and ©. |
|<kbd>t</kbd>|†   |U+2020|DAGGER|Often used for marking footnotes, also used in math/physics for the conjugate (Hermitian) transpose. Shape similar to letter "t". |
|<kbd>y</kbd>|±   |U+00B1|PLUS-MINUS SIGN|**Dead key: math symbols comprised of horizontal and vertical lines, such as relational operators.** Shapes similar to the crossed shape of the letter "y", which also notes that the characters in this set could comprise of lines towards all directions. **Root character and default character** is U+00B1 PLUS-MINUS SIGN because it is most commonly used, and is the only character in this set which has a code point that is valid for a dead key. |
|<kbd>u</kbd>|∪   |U+222A|UNION|Math: set notation. Shape similar to letter "U". |
|<kbd>i</kbd>|ı   |U+0131|LATIN SMALL LETTER DOTLESS I|Math: imaginary unit in some fields, eg. engineering. Also used in some languages, eg. Azerbaijani, Turkish. Shape similar to letter "i". |
|<kbd>o</kbd>|ϕ   |U+03D5|GREEK PHI SYMBOL|**Dead key: circle-related math symbols.** Shapes include a circle, similar to shape of letter "o". **Root character and default character** is U+03D5 GREEK PHI SYMBOL, a common Greek variable name in math. Note for Greek language, U+03C6 GREEK SMALL LETTER PHI (φ) is used. |
|<kbd>p</kbd>|℗   |U+2117|SOUND RECORDING COPYRIGHT|Also known as published phonorecord sign. Shape includes letter "P". Shift state same as ® and ©. |
|<kbd>[</kbd>|‹   |U+2039|SINGLE LEFT-POINTING ANGLE QUOTATION MARK|Punctuation: left single quotation mark in some European languages. Used in pairs, similar to brackets. Shift state in accordance with single/double quotation marks. |
|<kbd>]</kbd>|›   |U+203A|SINGLE RIGHT-POINTING ANGLE QUOTATION MARK|Punctuation: right single quotation mark in some European languages. Justification similar to U+2039 SINGLE LEFT-POINTING ANGLE QUOTATION MARK. |
|<kbd>\\</kbd>|↓   |U+2193|DOWNWARDS ARROW|Meaning related to U+005C REVERSE SOLIDUS (backslash) that indicates a falling notion. Mirror image of U+2191 UPWARDS ARROW. |


#### AltGr + Shift shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>Q</kbd>|≡   |U+2261|IDENTICAL TO|Math: congruency, equivalence. Related to "equality", which has the letter "q". This symbol has a stronger mathematical meaning than U+00F7 DIVISION SIGN, and thus is mapped to the shifted shift state. |
|<kbd>W</kbd>|Ʃ   |U+01A9|LATIN CAPITAL LETTER ESH|**Dead key: n-ary math operators.** Large math operators, such as summation, multiplication, and coproduct. **Root character and default character** is used in the African Alphabet, shape similar to capital letter sigma and turned letter "W". This pairs with key <kbd>I</kbd> mapped to U+0283 LATIN SMALL LETTER ESH. Key <kbd>E</kbd> is reserved for U+2203 THERE EXISTS, which resembles the letter "E" more. |
|<kbd>E</kbd>|∃   |U+2203|THERE EXISTS|Math: existential quantifier. Shape similar to a reversed letter "E". |
|<kbd>R</kbd>|™   |U+2122|TRADE MARK SIGN|Usage highly related to U+00AE REGISTERED SIGN mapped to the same key. |
|<kbd>T</kbd>|‡   |U+2021|DOUBLE DAGGER|Often used for marking footnotes, also used in chemistry to denote a transition state. Shape similar to letter "t" and U+2020 DAGGER mapped to the same key. |
|<kbd>Y</kbd>|¥   |U+00A5|YEN SIGN|Shape similar to letter "Y". Near other currency signs. |
|<kbd>U</kbd>|∩   |U+2229|INTERSECTION|Math: set notation. Mirror image of U+222A UNION mapped to the same key. |
|<kbd>I</kbd>|ʃ   |U+0283|LATIN SMALL LETTER ESH|**Dead key: integral math symbols.** The name "integral" begins with the letter "i". Also integrals are large math operators, so they are mapped to capital key "I". **Root character and default character** is U+0283 LATIN SMALL LETTER ESH becuase it is a useful latin letter that resembles an integral, while all integral characters in this set have code points that are invalid for a dead key. |
|<kbd>O</kbd>|∅   |U+2205|EMPTY SET|Math: set notation. Shape similar to letter "O" and U+03D5 GREEK PHI SYMBOL mapped to the same key. |
|<kbd>P</kbd>|¶   |U+00B6|PILCROW SIGN|Typography: denotes a paragraph. Name starts with letter "p". Shape similar to reversed letter "P". Has same shift state as U+00A7 SECTION SIGN. |
|<kbd>{</kbd>|«   |U+00AB|LEFT-POINTING DOUBLE ANGLE QUOTATION MARK|Punctuation: left double quotation mark in some European languages (eg. French guillemets). Used in pairs, similar to braces. Shift state in accordance with single/double quotation marks. |
|<kbd>}</kbd>|»   |U+00BB|RIGHT-POINTING DOUBLE ANGLE QUOTATION MARK|Punctuation: right double quotation mark in some European languages (eg. French guillemets). Justification similar to U+00AB LEFT-POINTING DOUBLE ANGLE QUOTATION MARK. |
|<kbd>\|</kbd>|↑   |U+2191|UPWARDS ARROW|Shape similar to U+007C VERTICAL BAR mapped to this key. Indicates upward motion, which is related to the <kbd>Shift</kbd> key icon. Mirror image of U+2193 DOWNWARDS ARROW. |

### ASDF row
#### AltGr shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>a</kbd>|ɐ   |U+0250|LATIN SMALL LETTER TURNED A|**Dead key: set inclusion math symbols.** Mainly mapped to this key in accordance with key mappings of set membership symbols and U+2203 THERE EXISTS to key <kbd>E</kbd>. U+2220 ANGLE is also included for its similar shape with these symbols and its name starting with letter "a". **Root character** has a shape similar to a turned "a". **Default character** is U+2282 SUBSET OF, which is representative. |
|<kbd>s</kbd>|ß   |U+00DF|LATIN SMALL LETTER SHARP S|Common letter in German language. Shape and usage similar to letter "s". Retained from USX layout. |
|<kbd>d</kbd>|∂   |U+2202|PARTIAL DIFFERENTIAL|Math: calculus. Shape is essentially a variant of letter "d". |
|<kbd>f</kbd>|ϝ   |U+03DD|GREEK SMALL LETTER DIGAMMA|Math: variable name. Shape similar to letter "f". Required to be included in UTR25. |
|<kbd>g</kbd>|γ   |U+03B3|GREEK SMALL LETTER GAMMA|**Dead key: Greek letters, expanded to other math variable letters.** The name "Greek" starts with the letter "g". The base character mappings for this dead key is based on the Greek QWERTY keyboard layout. **Root character and default character** is U+03B3 GREEK SMALL LETTER GAMMA because it is the Greek version of letter "g", and also mapped so in the Greek QWERTY keyboard layout. |
|<kbd>h</kbd>|ℏ   |U+210F|PLANCK CONSTANT OVER TWO PI|Physics: reduced Plank's constant. Shape similar to letter "h". |
|<kbd>j</kbd>|←   |U+2190|LEFTWARDS ARROW|Shape of letter "J" points to the left, similar to a mirror image of letter "L". Conventionally, many video websites (eg. Youtube) map rewind/pause/foward shortcuts to keys <kbd>J</kbd>, <kbd>K</kbd>, and <kbd>L</kbd>. |
|<kbd>k</kbd>|↔   |U+2194|LEFT RIGHT ARROW|Letter "K" positioned between letters "J" and "L" mapped to the left and right arrows. Shape of letter "K" also points to two directions. |
|<kbd>l</kbd>|→   |U+2192|RIGHTWARDS ARROW|Shape of letter "L" points to the left, similar to a mirror image of letter "J". Justification similar to U+2190 LEFTWARDS ARROW. |
|<kbd>;</kbd>|∴   |U+2234|THEREFORE|Math: indicates logical consequence in proofs, especially for geometry. Shape has multiple dots, similar to the colon and semicolon. In pair with U+2235 BECAUSE, but normally used after it, thus mapped to the non-shifted shift state. |
|<kbd>'</kbd>|´   |U+0301|COMBINING ACUTE ACCENT|**Dead key: characters with the acute accent diacritic.** Shape of apostrophe similar to acute accent. Retained from USX layout. |


#### AltGr + Shift shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>A</kbd>|∀   |U+2200|FOR ALL|Math: universal quantifier. Shape similar to a turned letter "A". |
|<kbd>S</kbd>|§   |U+00A7|SECTION SIGN|Typography: denotes a section. Shape includes two letter "S"s. Retained from USX layout. Has same shift state as U+00B6 PILCROW SIGN. |
|<kbd>D</kbd>|∆   |U+2206|INCREMENT|Math: indicates the difference of the value of a variable resulting from change. Shape similar to Greek capital letter delta. Related to U+2202 PARTIAL DIFFERENTIAL mapped to the same key. |
|<kbd>F</kbd>|Ϝ   |U+03DC|GREEK LETTER DIGAMMA|Math: variable name. Shape similar to letter "F". Required to be included in UTR25. |
|<kbd>G</kbd>|∇   |U+2207|NABLA|Physics: differential operator. Describes gradient, which starts with letter "g". Similar to an inverted Greek capital delta, that also shares the same shift state with this character. Near other Greek letters. |
|<kbd>H</kbd>|Ħ   |U+0126|LATIN CAPITAL LETTER H WITH STROKE|**Dead key: letters with the mathematical Fraktur (Black-letter or Gothic) font.** Due to Windows limitations, only a few such letters are available. **Root character** is U+0126 LATIN CAPITAL LETTER H WITH STROKE only as a representation of the special font, while all Fraktur letters are not valid as dead key root characters; this character is by intent not mapped to a Base characterstroke because it is only a placeholder and not a Fraktur letter. **Default character** is U+210C BLACK-LETTER CAPITAL H (ℌ), which is commonly used in physics for Hilbert space. |
|<kbd>J</kbd>|⇐   |U+21D0|LEFTWARDS DOUBLE ARROW|Justification similar to U+2190 LEFTWARDS ARROW. Mapped to shifted state because it is double-stroke, a variant of the single arrow. |
|<kbd>K</kbd>|⇔   |U+21D4|LEFT RIGHT DOUBLE ARROW|Justification similar to U+2194 LEFT RIGHT ARROW. Mapped to shifted state because it is double-stroke, a variant of the single arrow. |
|<kbd>L</kbd>|⇒   |U+21D2|RIGHTWARDS DOUBLE ARROW|Justification similar to U+2192 RIGHTWARDS ARROW. Mapped to shifted state because it is double-stroke, a variant of the single arrow. |
|<kbd>:</kbd>|∵   |U+2235|BECAUSE|Math: indicates logical conditions in proofs, especially for geometry. Shape has multiple dots, similar to the colon and semicolon. In pair with U+2234 THEREFORE, but normally used first, thus mapped to the shifted shift state. |
|<kbd>"</kbd>|¨   |U+0308|COMBINING DIAERESIS|**Dead key: characters with the diaeresis diacritic, extended to diacritics with one or multiple dots.** Shape of quotation mark similar to diaeresis accent. Retained from USX layout. |

### ZXCV row
#### AltGr shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>z</kbd>|≠   |U+2260|NOT EQUAL TO|Math. Shape similar to letter "z". Has the same shift state as the equals sign ("="). |
|<kbd>x</kbd>|×   |U+00D7|MULTIPLICATION SIGN|Math. Shape similar to letter "x". Has same shift state as U+00F7 DIVISION SIGN (mapped to key <kbd>x</kbd>), another common math operator. |
|<kbd>c</kbd>|©   |U+00A9|COPYRIGHT SIGN|Shape includes letter "c". Retained from USX layout. Shift state same as ® and ℗. |
|<kbd>v</kbd>|∨   |U+2228|LOGICAL OR|Math: logical operator. Shape similar to letter "v". |
|<kbd>b</kbd>|ˉ   |U+0304|COMBINING MACRON|**Dead keys: characters with the macron diacritic, extended to overline diacritics.** The shapes of these diacritics are usually called "bars" (especially in physics), which starts with letter "b". This key was originally intended for only U+0305 COMBINING OVERLINE for use in math and physics (denoting averages), then extended. |
|<kbd>n</kbd>|¬   |U+00AC|NOT SIGN|Math: logical operator. The name "not" starts with letter "n". |
|<kbd>m</kbd>|↦   |U+21A6|RIGHTWARDS ARROW FROM BAR|Math: function notation. Commonly called the maplet, which starts with letter "m". |
|<kbd>,</kbd>|¸   |U+0327|COMBINING CEDILLA|**Dead key: characters with the cedilla or ogonek diacritic.** Shape of cedilla similar to the comma, while shape of ogonek similar to a reversed comma. The two diacritics are mutually exclusive on a letter, thus they are mapped to the same key. |
|<kbd>.</kbd>|̣   |U+0323|COMBINING DOT BELOW|**Dead key: characters with the underdot diacritic, extended to punctuation with multiple dots.** Shape similar to the period. In accordance with $\LaTeX$, includes the family of matrix abbreviators `\cdot`, `\cdots`, `\vdots`, etc. **Default character** is the punctuation U+00B7 MIDDLE DOT (·), as there is no modifier letter for the below dot diacritic. Not to be confused with U+22C5 DOT OPERATOR (⋅), which should be used exclusively for dot multiplication in math. |
|<kbd>/</kbd>|̸   |U+0338|COMBINING LONG SOLIDUS OVERLAY|**Dead key: characters with a stroke.** Shape similar to the solidus. Standard combining character for "crossing out" other characters in Unicode. **Default character** is U+2044 FRACTION SLASH, which has a similar shape with the solidus, and also represents the usage of the solidus as the division operator. |


#### AltGr + Shift shift state
|Key|Char|Unicode|Character&nbsp;name|Description|
|:-:|:--:|:-----:|--------------|-----------|
|<kbd>Z</kbd>|Ƶ   |U+01B5|LATIN CAPITAL LETTER Z WITH STROKE|**Dead key: letters with the mathematical double-struck font.** Due to Windows limitations, only a few such letters are available. **Root character** is U+01B5 LATIN CAPITAL LETTER Z WITH STROKE only as a representation of the special font, while all double-struck letters are not valid as dead key root characters; this character is by intent not mapped to a Base characterstroke because it is only a placeholder and not a double-struck letter. **Default character** is U+2124 DOUBLE-STRUCK CAPITAL Z (ℤ), which is commonly used in math for the set of integers. |
|<kbd>X</kbd>|≈   |U+2248|ALMOST EQUAL TO|Math. Denotes approximation, which has the sound of letter "x". Has the same shift state as U+2261 IDENTICAL TO, both equality-related symbols. |
|<kbd>C</kbd>|¢   |U+00A2|CENT SIGN|Shape similar to letter "c". Similarly in a shifted shift state as the dollar sign. Retained from USX layout. |
|<kbd>V</kbd>|∧   |U+2227|LOGICAL AND|Math: logical operator, conjunction. Mirror image of U+2228 LOGICAL OR. |
|<kbd>B</kbd>|˘   |U+0306|COMBINING BREVE|**Dead key: characters with the breve diacritic.** The name "breve" starts with the letter "b". |
|<kbd>N</kbd>|⊻   |U+22BB|XOR|Math: logical operator, exclusive disjunction. Expresses an alternative version of OR, so mapped to the same key as U+00AC NOT SIGN; but this does not mean that this is a negated version of OR (XOR is not NOR). Near other logical operators. |
|<kbd>M</kbd>|µ   |U+00B5|MICRO SIGN|**Dead key: letters with the mathematical script font.** Due to Windows limitations, only a few such letters are available. **Root character** is U+00B5 MICRO SIGN, whose name starts with letter "m". Itself is a deprecated symbol identical to Greek small letter mu (μ), and the latter should always be used. Here it is a placeholder, while all script letters are not valid as dead key root characters; this character is by intent not mapped to a Base characterstroke because it is only a placeholder and not a script letter. **Default character** is U+2133 SCRIPT CAPITAL M (ℳ), which is the symbol for the M-matrix in physics, and the pre-WWII German Mark. |
|<kbd><</kbd>|<   |U+003C|LESS-THAN SIGN|**Dead key: variants of the less-than sign in math.** **Root character** is the plain less-than sign because all of its variants are not valid as dead key root characters. **Default character** is U+2264 LESS-THAN OR EQUAL TO as the most common and simple variant. |
|<kbd>></kbd>|>   |U+003E|GREATER-THAN SIGN|**Dead key: variants of the greater-than sign in math.** **Root character** is the plain greater-than sign because all of its variants are not valid as dead key root characters. **Default character** is U+2265 GREATER-THAN OR EQUAL TO as the most common and simple variant. |
|<kbd>?</kbd>|¿   |U+00BF|INVERTED QUESTION MARK|Punctuation: used to begin interrogations in Spanish languages. Partially retained from USX layout, changed shift state for better accordance with U+003F QUESTION MARK. |

### Space bar
- **AltGr shift state:** U+00A0 NO-BREAK SPACE. Special whitespace in typesetting that prevents an automatic line break at its position. 
- **AltGr + Shift shift state:** U+200B ZERO WIDTH SPACE. Special whitespace that has no width, which could serve as implicit word boundaries in typesetting. Not to be confused with U+200D ZERO WIDTH JOINER available at key <kbd>&</kbd>, that is for joining and composing graphemes. 

## Dead Key Secondary Mappings
For convenience and ease of memory, the 26 dead keys in the US International Scientific keyboard layout are listed below in groups sharing similar design logic, instead of original order. 

### Modified Latin letters
|Category|Grave accents|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>\`</kbd>|
|Root|U+0300 COMBINING GRAVE ACCENT (◌̀)|
|Bases|`aeiouynw AEIOUYNW`|
|Composites|àèìòùỳǹẁ ÀÈÌÒÙỲǸẀ|
|Default|U+0060 GRAVE ACCENT (`)|

|Category|Tilde diacritic + math equality symbols|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>~</kbd>|
|Root|U+0303 COMBINING TILDE (◌̃)|
|Bases|`aeiouynv AEIOUYNV -=`|
|Composites|ãẽĩõũỹñṽ ÃẼĨÕŨỸÑṼ ≃≅|
|Default|U+00DC SMALL TILDE (˜)|
|Notes|Two common mathematical equality operators with related shapes are included, respectively U+2243 ASYMPTOTICALLY EQUAL TO, U+2245 APPROXIMATELY EQUAL TO. 

|Category|Caron diacritic|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>6</kbd>|
|Root|U+030C COMBINING CARON (◌̌)|
|Bases|`aeiou cdghjklnrstz AEIOU CDGHKLNRSTZ`|
|Composites|ǎěǐǒǔ čďǧȟǐǰǩľňřšťž ǍĚǏǑǓ ČĎǦȞǏǨĽŇŘŠŤŽ|
|Default|U+02C7 CARON (ˇ)|
|Notes|For unknown reasons, Unicode does not include capital letter "J" with caron, although its lowercase form is encoded. Certain letters may have a different display for the caron, such as an apostrophe at the upper right corner. |

|Category|Circumflex accents|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>^</kbd>|
|Root|U+0302 COMBINING CIRCUMFLEX ACCENT (◌̂)|
|Bases|`aeiouy cghjswz AEIOUY CGHJSWZ`|
|Composites|âêîôûŷ ĉĝĥĵŝŵẑ ÂÊÎÔÛŶ ĈĜĤĴŜŴẐ|
|Default|U+02C6 MODIFIER LETTER CIRCUMFLEX ACCENT (ˆ)|

|Category|Dot above diacritic
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>*</kbd>|
|Root|U+0307 COMBINING DOT ABOVE (◌̇)|
|Bases|`aeoy bcdfghlmnprstwxz AEIOY BCDFGHLMNPRSTWXZ`|
|Composites|ȧėȯẏ ḃċḋḟġḣŀṁṅṗṙṡṫẇẋż ȦĖİȮẎ ḂĊḊḞĠḢĿṀṄṖṘṠṪẆẊŻ|
|Default|U+02D9 DOT ABOVE (˙)|

|Category|Ring above diacritic + circle symbols|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>0</kbd>|
|Root|U+030A COMBINING RING ABOVE (◌̊)|
|Bases|`auwy AU CF oObB.\| -x`|
|Composites|åůẘẙ ÅŮ ℃℉ ○◯●⬤◌◍ ⦵⦻|
|Default|U+00B0 DEGREE SIGN (°)|
|Notes|Includes related symbols: degree Celsius/Fahrenheit, various circles, and the Plimsoll symbol (U+29B5 CIRCLE WITH HORIZONTAL BAR) for chemical standard state (however it is not a superscript; for raw-text editing, by IUPAC the degrees sign is also accepted), along with U+29BB	CIRCLE WITH SUPERIMPOSED X. |

|Category|Acute accent + typographical single quotes|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>'</kbd>|
|Root|U+0301 COMBINING ACUTE ACCENT (◌́)|
|Bases|`aeiouy cgklmnprswz AEIOUY CGKLMNPRSWZ []{}`|
|Composites|áéíóúý ćǵḱĺḿńṕŕśẃź ÁÉÍÓÚÝ ĆǴḰĹḾŃṔŔŚẂŹ ‘’‚‛|
|Default|U+00B4 ACUTE ACCENT (´)|
|Notes|Typographical single quotes are included, which have direction. An alternate pair is available for languages such as German. |

|Category|Diaeresis diacritic + dot diacritics|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>"</kbd>|
|Root|U+0308 COMBINING DIAERESIS (◌̈)|
|Bases|`` aeiouy htwx AEIOUY HWX 1234 '"` []{}``|
|Composites|äëïöüÿ ḧẗẅẍ ÄËÏÖÜ ḦẄẌ ◌̇◌̈ ⃛ ⃜ ◌̋˝̏
|Default|U+00A8 DIAERESIS (¨)|
|Notes|For unknown reasons, Unicode does not include capital letter "T" with diaeresis, although its lowercase form is encoded. Combining diacritical marks with 1–4 dots above are included, which are commonly used to indicate time derivatives in physics. Also includes combining double acute and grave accents, and the modifier letter for the former mapped to `"` (there is no modifier letter for the latter in Unicode). Typographical single quotes are featured, with alternate pair available for languages such as German. |

|Category|Macron diacritic + bar diacritics|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>b</kbd>|
|Root|U+0304 COMBINING MACRON (◌̄)|
|Bases|`aeiouyg AEIOUYG -=_`|
|Composites|āēīōūȳḡ ĀĒĪŌŪ∨YḠ ◌̅◌̿¯|
|Default|U+02C9 MODIFIER LETTER MACRON (ˉ)|
|Notes|Includes related combining diacritical marks: U+0305 COMBINING OVERLINE (denotes averages in math), U+033F COMBINING DOUBLE OVERLINE. Includes U+00AF MACRON, a longer variant of the modifier letter from legacy.|

|Category|Breve diacritic|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>B</kbd>|
|Root|U+0306 COMBINING BREVE (◌̆)|
|Bases|`aeioug AEIOUG ^`|
|Composites|ăĕĭŏŭğ ĂĔĬŎŬĞ ◌̑|
|Default|U+02D8 BREVE (˘)|
|Notes|Includes combining inverted breve mapped to the circumflex due to similar shape, but there is no modifier letter for this in Unicode.|

|Category|Cedilla and ogonek diacritics|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>,</kbd>|
|Root|U+0327 COMBINING CEDILLA (◌̧)|
|Bases|`aeiou cdghklnrst AEIOU CDGHKLNRST \\|`|
|Composites|ąęįǫų çḑģḩķļņŗşţ ĄĘĮǪŲ ÇḐĢḨĶĻŅRŞŢ ◌̨ ˛|
|Default|U+00B8 CEDILLA (¸)|
|Notes|Since only consonants can have a cedilla while only vowels can have an ogonek, being mutually exclusive, the two diacritics are included in the same key (With the exception of letters `E` and `e` with cedilla (Ȩȩ), since they are rare and the more common version with ogonek is already included). Certain letters may have a different display for the cedilla, such as having the shape of an apostrophe. Includes the combining diacritical mark and modifier letter for the ogonek, respectively mapped to <kbd>\\</kbd> and <kbd>\|</kbd> since the ogonek and cedilla are approximately mirror images.|

|Category|Underdot diacritic + dot-related symbols|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>.</kbd>|
|Root|U+0323 COMBINING DOT BELOW (◌̣)|
|Bases|`abdehiklmnorstuvwyz ABDEHIKLMNORSTUVWYZ -/\|\ ." *`|
|Composites|ạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓ ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒ ⋯⋰⋮⋱ …◌̤ ⋅|
|Default|U+00B7 MIDDLE DOT (·)|
|Notes|Ellipsis is mapped to key <kbd>.</kbd> representing the extra dots. This is more convenient than key <kbd>_</kbd> which requires shift. U+00B7 MIDDLE DOT (·) is not for dot multiplication, the preferred character is U+22C5 DOT OPERATOR mapped to `*`. Also includes U+0324 COMBINING DIAERESIS BELOW for two dots below. |

|Category|Stroked letters + vulgar fractions|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>\\</kbd>|
|Root|U+0338 COMBINING LONG SOLIDUS OVERLAY (◌̸)|
|Bases|`abcdefghijkloprtuyz`<br>`ABCDEFGHIJKLOPRTUYZ`<br>`1234567 890 !@#$% ^&() *`|
|Composites|ⱥƀȼđɇꞙǥħɨɉꝁłøᵽɍŧꞹɏƶ<br>ȺɃȻĐɆꞘǤĦƗɈꝀŁØⱣɌŦꞸɎƵ<br>⅛¼⅜½⅝¾⅞ ⅔⅓↉ ⅕⅖⅗⅘ ⅚⅙⅐⅑⅒ ⅟|
|Default|U+2044 FRACTION SLASH (⁄)|
|Notes|Includes all vulgar fractions provided in Unicode, perfectly mapped to the number row keys. Third fractions are in reverse order, considering fraction ↉ as 0, and to accommodate the remaining two, 8 is two thirds by having two circles in its shape, and 9 is one third by having one circle only. Other fractions are mapped by their value. U+215F FRACTION NUMERATOR ONE (⅟ ) is mapped to `*` representing the blank denominator. Custom vulgar fractions can be composed by superscript numbers, the fraction slash (provided as default case of this dead key), and subscript numbers (e.g. ¹¹³⁄₃₅₅).  This combining diacritical mark (U+0338) is also the standard combining character for "crossing out" other characters in Unicode, for example negating math operators: U+003D (=) + U+0338 ⇔ U+2260 (≠). |

|Category|Ligatures + North European letters|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>&</kbd>|
|Root|U+00A6 BROKEN BAR (¦)|
|Bases|`ao ilnd AO ILND 1234567 s tT eE 8* 9( 0) &\|`|
|Composites|æœ ĳǉǌǳ ÆŒ ĲǇǊǱ ﬀﬁﬂﬃﬄﬅﬆ ‍ſ þÞ ðÐ ȣȢ ƣƢ ŋŊ ⅋¦|
|Default|U+200D ZERO WIDTH JOINER (‍)|
|Notes|The default character U+200D ZERO WIDTH JOINER is a special invisible whitespace (thus mapped to the space bar) that is the standard combining character for composing multiple graphemes, such as adding skin color in emojis. Also includes all typographical ligatures mapped to number keys in sequence; North European letters long s, thorn, eth, ou, gha, and eng (last 3 are mapped to numbers by similar shape); and loosely-related characters U+214B TURNED AMPERSAND (⅋, used in linear logic) and U+00A6 BROKEN BAR (¦, for [legacy](https://en.wikipedia.org/wiki/Vertical_bar#Solid_vertical_bar_vs_broken_bar)). |

### Mathematical alphanumeric symbols
|Category|Subscripts|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>=</kbd>|
|Root|U+00AA FEMININE ORDINAL INDICATOR (ª)|
|Bases|`0123456789+-=() aehijklmnoprstuvx`|
|Composites|₀₁₂₃₄₅₆₇₈₉₊₋₌₍₎ ₐₑₕᵢⱼₖₗₘₙₒₚᵣₛₜᵤᵥₓ|
|Default|U+00AA FEMININE ORDINAL INDICATOR (ª)|
|Notes|Not all subscript lowercase letters are available in Unicode. |

|Category|Superscripts|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>+</kbd>|
|Root|U+00BA MASCULINE ORDINAL INDICATOR (º)|
|Bases|`0123456789+-=()`<br>`abcdefghijklmnoprstuvwxyz`<br>`ABCDEFGHIJKLMNOPQRTUVW`|
|Composites|⁰¹²³⁴⁵⁶⁷⁸⁹⁺⁻⁼⁽⁾<br>ᵃᵇᶜᵈᵉᶠᵍʰⁱʲᵏˡᵐⁿᵒᵖʳˢᵗᵘᵛʷˣʸᶻ<br>ᴬᴮꟲᴰᴱꟳᴳᴴᴵᴶᴷᴸᴹᴺᴼᴾꟴᴿᵀᵁⱽᵂ|
|Default|U+00BA MASCULINE ORDINAL INDICATOR (º)|
|Notes|All superscript lowercase letters except "q" (U+107A5, non-BMP characters are not supported) are available on this keyboard. For superscript capital letters, "S", "X", "Y", and "Z" are missing. |

|Category|Greek letters with variants + first 4 Hebrew letters|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>g</kbd>|
|Root|U+03B3 GREEK SMALL LETTER GAMMA (γ)|
|Bases|`qwertyuiop`<br>`asdfghjkl`<br>`zxcvbnm`<br>`QWERTYUIOP`<br>`ASDFGHJKL`<br>`ZXCVBNM`<br>`123456`|
|Composites|ϑςερτυθιοπ<br>ασδφγηξκλ<br>ζχψωβνμ<br>ϴϖΕΡΤΥΘΙΟΠ<br>ΑΣΔΦΓΗΞΚΛ<br>ΖΧΨΩΒΝΜ<br>ℵℶℷℸϰϱ|
|Default|U+03B3 GREEK SMALL LETTER GAMMA (γ)|
|Notes|These letters are included in the Basic Set of Alphanumeric Characters for mathematical notation (see §2.2 of [UTR25](http://www.unicode.org/reports/tr25/)). For convenience and consistency, the mappings are mostly identical to the standard Greek keyboard layout. Greek diacritics were removed. Key <kbd>w</kbd> is retained as the lowercase final sigma. Keys `QqW` are mapped respectively to U+03F4 (ϴ ↔ Θ), U+03D1 (ϑ ↔ θ), and U+03D6 (ϖ ↔ π), based on their similar shapes. Keys `1234` are the first 4 capital Herbrew letters Alef, Bet, Gimel, and Dalet. Keys `56` are mapped respectively to U+03F0 (ϰ ↔ κ) and U+03F1 (ϱ ↔ ρ) due to the lack of space, yet coincidently the shapes are relatable (ϰ looks like a distorted turned 5, ϱ looks like a flipped 6), and their Unicode datapoints are consecutive! |

|Category|Black-letter (Fraktur) font letters|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>H</kbd>|
|Root|U+0126 LATIN CAPITAL LETTER H WITH STROKE (Ħ)|
|Bases|`CHIRZ`|
|Composites|ℭℌℑℜℨ|
|Default|U+210C BLACK-LETTER CAPITAL H (ℌ)|
|Notes|Black-letter capital H is representative for this font family as the symbol for Hilbert space. | 

|Category|Double-struck font letters + italics|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>Z</kbd>|
|Root|U+01B5 LATIN CAPITAL LETTER Z WITH STROKE (Ƶ)|
|Bases|`CDHNPQRZ Ddeij`|
|Composites|ℂℍℕℙℚℝℤ ⅅⅆⅇⅈⅉ|
|Default|U+2124 DOUBLE-STRUCK CAPITAL Z (ℤ)|
|Notes|Includes 5 extra double-struck italic letters defined in Unicode. Double-struck capital Z is representative for this font family as the symbol for the set of integers. |

|Category|Script font letters|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>M</kbd>|
|Root|U+00B5 MICRO SIGN (µ)|
|Bases|`eglo BEFHILMPR`|
|Composites|ℯℊℓℴ ℬℰℱℋℐℒℳ℘ℛ|
|Default|U+2133 SCRIPT CAPITAL M (ℳ)|
|Notes|Script capital M is representative for this font family as the symbol for the M-matrix in physics. The root character U+00B5 MICRO SIGN (µ) is supported in many legacy environments, but U+03BC μ is the preferred Unicode character. |

### Mathematical operators
|Category|Set membership operators + nonexistential quantifier|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>e</kbd>|
|Root|U+03F6 GREEK REVERSED LUNATE EPSILON SYMBOL (϶)|
|Bases|`/\|\ eE`|
|Composites|∉∋∌ ϶∄|
|Default|U+2208 ELEMENT OF (∈)|
|Notes|Since ∈ and ∋ are mirror images, the latter is mapped to key </kbd>\|` indicating the plane of symmetry; other mappings follow this logic. Includes U+2204 THERE DOES NOT EXIST (∄) since key <kbd>E</kbd> is mapped to U+2203 THERE EXISTS (∃). 

|Category|Set inclusion operators + angle symbol|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>a</kbd>|
|Root|U+0250 LATIN SMALL LETTER TURNED A (ɐ)|
|Bases|`/[{\|}]\ CaA`|
|Composites|⊄⊆⊈⊃⊉⊇⊅ ∁ɐ∠|
|Default|U+2282 SUBSET OF (⊂)|
|Notes|Logic similar to set membership operators. Includes notation for complimentary sets and angles (since the key is <kbd>a</kbd>). |

|Category|Relational operators + tack-like symbols|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>y</kbd>|
|Root|U+00B1 PLUS-MINUS SIGN (±)|
|Bases|`amtfATF udrl p +-`|
|Composites|⊦⊧⊨⊩⊬⊭⊮ ⊥⊤⊢⊣ ⟂ ±∓|
|Default|U+00B1 PLUS-MINUS SIGN (±)|
|Notes|The mappings are based on the initial letter of each character's name: assertion, models, true, forces; up, down, right, left; perpendicular. Negations are mapped to capital letters (shifted state). Includes plus-minus and minus-plus signs. |

|Category|N-ary operators|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>W</kbd>|
|Root|U+01A9 LATIN CAPITAL LETTER ESH (Ʃ)|
|Bases|`sSpPuUvV .+x`|
|Composites|∑⅀∏∐⋃⋂⋁⋀ ⨀⨁⨂|
|Default|U+01A9 LATIN CAPITAL LETTER ESH (Ʃ)|
|Notes|S stands for "sum" and "sigma", P stands for "product" and "pi". Capital letter mappings represent variants. Default character is a resembling letter, only use if other symbols do not display. |

|Category|Integral operators|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>I</kbd>|
|Root|U+0283 LATIN SMALL LETTER ESH (ʃ)|
|Bases|`1234567890`|
|Composites|∫∬∭⨌∮∯∰∱∲∳|
|Default|U+0283 LATIN SMALL LETTER ESH (ʃ)|
|Notes|Mapping based on integral dimensions. Default character is a resembling letter, only use if other symbols do not display.|

|Category|Circle-related operators + QED|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>o</kbd>|
|Root|U+03D5 GREEK PHI SYMBOL (ϕ)|
|Bases|`+-x/\|\\.oO*=_<> q`|
|Composites|⊕⊖⊗⊘⦶⦸⊙∘⊚⊛⊜⊝⧀⧁ ∎|
|Default|U+03D5 GREEK PHI SYMBOL (ϕ)|
|Notes|Includes the QED (end-of-proof) symbol mapped to key <kbd>q</kbd>. |

|Category|Less-than operator variants + left ceiling/floor|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd><</kbd>|
|Root|U+003C LESS-THAN SIGN (<)|
|Bases|`/-+~=<> [{`|
|Composites|≮≤≰≲≦≪≶ ⌊⌈|
|Default|U+2264 LESS-THAN OR EQUAL TO (≤)|
|Notes|Includes left ceiling/floor brackets. |

|Category|Greater-than operator variants + right ceiling/floor|
|:------:|---|
|Dead key|<kbd>AltGr</kbd> + <kbd>></kbd>|
|Root|U+003E GREATER-THAN SIGN (>)|
|Bases|`/-+~=>< ]}`|
|Composites|≯≥≱≳≧≫≷ ⌋⌉|
|Default|U+2265 GREATER-THAN OR EQUAL TO (≥)|
|Notes|Includes right ceiling/floor brackets. |

## Comparison to Other Layouts
|Aspect|<i>US Intl. Sci.</i>|US|US Intl|Other projects|
|------|-|-|-|-|
|Basic Latin and ASCII|![√](assets/check.svg)|![√](assets/check.svg)|![√](assets/check.svg)|![√](assets/check.svg)|
|Latin-1 Supplement letters (àéçôïñðœßøþ...)|![√](assets/check.svg)|![-](assets/minus.svg)|![√](assets/check.svg)|![!](assets/limited.svg)Most|
|Latin-1 punctuation and symbols (¡¢£¤§...)|![!](assets/limited.svg)28/29|![-](assets/minus.svg)|![!](assets/limited.svg)22/29|![!](assets/limited.svg)Most|
|Multiplication and division operators (×÷)|![√](assets/check.svg)|![-](assets/minus.svg)|![√](assets/check.svg)|![!](assets/limited.svg)Some|
|Vulgar fractions (¼½¾)|![√](assets/check.svg)Any|![-](assets/minus.svg)|![!](assets/limited.svg)|![-](assets/minus.svg)|
|French special letters (éàç...)|![√](assets/check.svg)|![-](assets/minus.svg)|![√](assets/check.svg)|![√](assets/check.svg)|
|German special letters (ßöü)|![√](assets/check.svg)|![-](assets/minus.svg)|![√](assets/check.svg)|![√](assets/check.svg)|
|Spanish/Portugese special letters (ñãõ)|![√](assets/check.svg)|![-](assets/minus.svg)|![√](assets/check.svg)|![√](assets/check.svg)|
|East European special letters (ščžşçąų...)|![√](assets/check.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|![!](assets/limited.svg)|
|North European special letters (åþð)|![√](assets/check.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|![-](assets/minus.svg)|
|Ligatures|![√](assets/check.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|![!](assets/limited.svg)|
|Greek letters|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Greek letter variants in math|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Hebrew letters in math|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Equality operators (≤≥≈≡)|![√](assets/check.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|![!](assets/limited.svg)|
|Integrals|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Derivatives / Change (′″‴∂∆∇)|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Set notation operators|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Circled operators|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Relational operators|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Subscripts and superscripts|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Letters in mathematical font|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Arrows|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Special whitespaces|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Support for physics|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Support for chemistry|![√](assets/check.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![!](assets/limited.svg)|
|Controls|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Cyrillic letters|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Arabics|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Logosyllabics|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|
|Other non-alphabetical languages|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|![-](assets/minus.svg)|

## Notes on MSKLC 1.4
This project is made possible by the software [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=102134). Sadly, several bugs or limitations exist in this software that had prevented this project from being more powerful and extensive. 

1. Errors when renaming layouts. In certain cases (details unclear), editing the layout description text on a custom version of an imported layout will not take effect. Sometimes there is a newline between the DESCRIPTION section and the LANGUAGE section, and sometimes not, which may affect the behavior of descriptions. 
2. Dead key base limit at U+0FFF. Dead keys that have a base of greater than U+1000 will not work when the `.dll` is created. When triggered, the Windows system gives off an alarm noise, instead of no response for an undefined key combination. When the built custom keyboard layout is then loaded into MSKLC, the deadkeys are blank and no codepoint designation can be seen. 
	- Tested base codepoints: mutiple codepoints greater than U+2100 (in the math symbols section), U+2000, U+1ffd, U+1800, U+1000, [U+0fda, U+0f00, U+0e01, U+0a01, U+0800, U+0308] (in brackets = success)
	- The original author seemed to be aware of this problem since 2008, but it is still not resolved. This is probably due to an internal Microsoft restriction :/
3. Character limit at U+FFFF. For normal keys, there is also an upper limit restriction found at roughly U+10000, which means that only the codepoints in the BMP (U+0000..U+FFFF) can be accessed. The behavior of this issue is the same for dead keys. 
   - For example, an attempt to include U+1D7D9 failed. 
   - This prevents inclusion of most letters with mathematical fonts. 

However, these issues have no hope of being fixed in the short term, since the software is not completely open-source, and its original creator has passed away…

R.I.P Michael Scott Kaplan (*1970/02/27 Creve Coeur — †2015/10/21 Redmond), Microsoft developer and the very creator of MSKLC. He passed away at age 45 from multiple sclerosis, a disease he fought against for 25 years. He was a very talented and responsible person, with good humor and writing… He had a colorful life: conflicts with Microsoft, battles with fatal diseases, affairs with prostitutes, and fun blogs that were brought to the readers by a unique Unicode character. 
- [His blog archive](http://archives.miloush.net/michkap/archive/) (which contains many, many stories);
- [His obiturary](https://obits.cleveland.com/us/obituaries/cleveland/name/michael-kaplan-obituary?id=20110483);
- [A podcast with him](https://www.hanselminutes.com/117/sorting-out-internationalization-with-michael-kaplan);
- [Unicode's Memoriam Page](https://www.unicode.org/consortium/memoriam.html) includes his name. 

*In memoriam of Mr. Michael S. Kaplan.*
