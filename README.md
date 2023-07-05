# US International Scientific Keyboard Layout
__A very powerful custom keyboard layout for Windows, tailored for efficient and convenient input of international latin languages and scientific notation in plain text.__

![overview](/assets/keyboard-layout.png)

- [Quick Start Guide](#quick-start-guide)
- [Update / Uninstallation Guide](#update--uninstallation-guide)
- [Must-know Concepts](#must-know-concepts)
	- [Dead keys](#dead-keys)
	- [Shift states and AltGr](#shift-states-and-altgr)
- [Overview of Keyboard Mappings](#overview-of-keyboard-mappings)
- [Core Design Ideas](#core-design-ideas)
- [Key Mappings](#key-mappings)
	- [Numeric row](#numeric-row)
		- [`AltGr` shift state](#altgr-shift-state)
		- [`AltGr` + `Shift` shift state](#altgr--shift-shift-state)
		- [Notes](#notes)
	- [QWERTY row](#qwerty-row)
		- [`AltGr` shift state](#altgr-shift-state-1)
		- [`AltGr` + `Shift` shift state](#altgr--shift-shift-state-1)
	- [ASDF row](#asdf-row)
		- [`AltGr` shift state](#altgr-shift-state-2)
		- [`AltGr` + `Shift` shift state](#altgr--shift-shift-state-2)
	- [ZXCV row](#zxcv-row)
		- [`AltGr` shift state](#altgr-shift-state-3)
		- [`AltGr` + `Shift` shift state](#altgr--shift-shift-state-3)
- [Bugs found in MSKLC - but it's a program that's almost older than myself!](#bugs-found-in-msklc---but-its-a-program-thats-almost-older-than-myself)



This keyboard layout is easy to install, easy to use, and easy to memorize, while having extensive capabilities covering common Latin letters, diacritics, mathematical symbols, additional punctuation, and some mathematical font letters. It is recommended for those who often work in __STEM__ fields on a __Windows__ system, and have collaborations with co-workers from __diverse language backgrounds__. It is also intended as a better alternative to the United States-International keyboard layout that had dead keys inconveniently bound on commonly used keys. 

> **Note:** This keyboard layout is **not a replacement for proper scientific notation** that can be formatted using rich-text programs like $\LaTeX$, UnicodeMath, or MathML, but rather a method to extend the symbols available in plain text input scenarios, e.g. texting on Discord, using Notepad, non-technical writing.

This keyboard layout was created using Microsoft Keyboard Layout Creator 1.4 (MSKLC 1.4). The layout is based on the common __English (United States) QWERTY keyboard layout__, and some designs are consistent with the _United States-International keyboard layout_. Other ideas were inspired by and improved on the basis of [Michael Goerz's version](https://michaelgoerz.net/notes/the-us-international-scientific-keyboard-layout/index.html) of the "U.S. International - Scientific" keyboard layout for Mac systems. 

## Quick Start Guide
Setting up this keyboard on your computer is very simple! 

1. (_Optional_) Be logged in to an Administrator account on your computer. Configuring the keyboard will require Administrator permission. 
2. Download [the latest release](https://github.com/BelugaHaechi/US-International-Scientific-Keyboard/releases/latest) to any directory on your computer.
   > **Note:** Releases are named as `KBDUSS` + major version number + minor version letter. We will use `KBDUSS**` to represent this below. This naming system is in conformity with system files in `C:\Windows\System32\KBD*.dll`. 
3. Open the folder, and run the program `setup.exe` in the folder. Do not alter or delete any other files in the folder. 
4. Follow the setup instructions that will pop up. At some point, you will be asked for Administrator permission; please allow to continue.
5. Now the keyboard is installed on your computer! The last step is to enable the layout in Settings.
	- Open Settings on your computer.
	- Navigate to `Time & language > Language & region > Keyboards` (this may differ slightly for various Windows versions).
	- Select `Add a keyboard`, and select `US-International and Scientific keyboard` in the drop-down menu.
	- (_Optional_) You can now disable the original `US keyboard (QWERTY)`, since its functions could be completely replaced by the new keyboard.
6. Congratulations! You are now all set to use the US International Scientific keyboard on your computer.

> **Tip:** You may wish to retain the `KBDUSS**` folder, because it could be used to repair/uninstall the keyboard layout on your computer.

## Update / Uninstallation Guide
Uninstallation of the keyboard layout is also simple. You may wish to do so, if:
1. There is a new version of the keyboard available, and you will need to uninstall the previous version before installing the new one. Yes, minor improvements may be made to the layout upon request, feel free to post your ideas in Issues.
2. The keyboard layout doesn't work as intended on your device. If so, you may wish to reinstall the layout.
3. You wish to discard the layout for any reason :( Sad, but you are free to do so.

To uninstall the keyboard layout, simply revisit the `KBDUSS**` folder, and run `setup.exe` again. This time you would be prompted to repair or uninstall the keyboard layout, and select the action as you wish. Administrator permission may be required again. 

> **Known issue:** Possibly due to a Windows system bug, on uninstallation the keyboard layout will not be compeletely removed. Don't worry – this does not affect normal usage of other keyboard layouts. You may be still able to find the name of the layout in the keyboard layout list in computer settings, but if you try to add this layout to your input methods, it cannot appear in the input methods list for actual use. In other words, only a "ghost" placeholder of the layout will remain in the list. In the system files the keyboard layout's `.dll` configuration is deleted, but it is still registered somewhere as a blank case. 

## Must-know Concepts
The US International Scientific keyboard layout utilizes two important concepts to achieve its unparalleled functionality: **dead keys** and the **AltGr shift state**. These concepts, common in non-English keyboard layouts, are explained below for those unfamiliar with them. 

### Dead keys
When a normal key is pressed, a character is returned. However, [**dead keys**](https://en.wikipedia.org/wiki/Dead_key) do not return a character when initially pressed, but rather waits for the next keypress and uses this input to determine the character it should return. This essentially enables a key to be mapped to multiple characters, for example key `` ` `` (backtick) could be mapped to all characters with an acute accent: à, ù, ì, À, Ù, Ì, and so on. 

This comes at the cost of requiring two keypresses to access one character, as in the example to type `à` one would need to press `` ` `` then `a`. The character `` ` `` is called the **base character** of the dead key in this case. If the second keypress does not map to a character in the dead key's character set, the base character of the dead key is returned along with the second character. 

By convention, the set of characters mapped to a dead key should share similar features, and also with the base character. It is also conventional to always have the _space key_ mapped to the **default case** of a dead key, usually a blank version of the base character. Dead keys are used extensively in many modern keyboard layouts, such as in the Greek Polytonic layout, the US-International layout, the UK Extended layout, and so on. 

### Shift states and AltGr
**Shift state** is a term for the layers of a keyboard layout, that could be interchanged by the state of control keys (`Shift`, `Alt`, `Ctrl`). We normally use two shift states: the blank shift state, and the `Shift` shift state. In fact, there are extra shift states arising from the combinations of the 3 control keys. Among the most well known are the `Alt` + `Ctrl` and `Alt` + `Ctrl` + `Shift` shift states, commonly referred to as the **AltGr shift states** because they are accessed by holding the `AltGr` (short for Alternative Graphics) key on European keyboards. On keyboards without `AltGr`, hold the **Right `Alt` key** to access these shift states; holding down both `Alt` and `Ctrl` keys is also valid. `AltGr` expands a keyboard layout to twice the original size, enabling the addition of new functions. 

Shift states with only `Alt` or `Ctrl` are mostly unused in keyboard layouts, because these key combinations are reserved for hotkeys (keyboard shortcuts). 

In the US International Scientific keyboard layout, the key mappings in the normal shift states are identical to that in the common English (United States) QWERTY keyboard layout. Thus, without `AltGr`, it is just a normal layout; this feature is intended to make the transition to this layout extremely easy. All extra functionalities are carefully designed into the AltGr shift states, along with usage of dead keys.  
</details>

## Overview of Keyboard Mappings
Below is a figure of the US International Scientific keyboard layout, made by [this tool](http://www.keyboard-layout-editor.com/#/) (also [on Github](https://github.com/ijprest/keyboard-layout-editor)). This figure may be greatly helpful as a reference to the functionalities of this keyboard layout. 

**Legend**

⚫ _Black:_ Normal keys. When pressed, returns the character shown. 

🔴 _Red:_ Dead keys. When pressed, waits for a second keypress, then returns a character based on the second keypress. 

🟣 _Purple:_ Dead keys, but due to restraints its base character does not well represent the set of characters mapped to the dead key. The former character in this representation is the base, the latter is the default case. 

🟥 _Red keycaps:_ At least one of the key's shift states is set as a dead key. 

🟦 _Blue keycaps:_ The key is used to control the shift states relevant to this layout. 

![overview](/assets/keyboard-layout.png)

## Core Design Ideas
1. __Complete compatibility with plain keyboards.__ _The US QWERTY keyboard layout remains unchanged_, and all extensions are "hidden" in the `AltGr` (`Alt` + `Ctrl`) and `AltGr` + `Shift` (`Ctrl` + `Alt` + `Shift`) shift states. Therefore it will be just an ordinary layout under normal use, and fits with its positioning as a "keyboard extension".   
Also, key mappings from the original United States-International keyboard are retained whenever appropriate, so that it aligns with Microsoft design and users switching over will find it more familiar to work with. These mappings with be denoted with a `(USX)` mark, referencing the Windows `KBDUSX.dll` file containing setup information. 

2. __Consistent logicality of key mappings.__ Every key mapping should always _make as much sense as possible_ and provide convenience for both multilingual and mathematical input. Every reason for a certain mapping should be explicitly documented, and alternatives should be discussed if any. 
   - At least one among name, shape, usage, etc. of the character allocated should be related with the key that it is mapped to. 
   - Common characters should be easy to access, while uncommon characters should be set further out of reach, and rare and awkward characters should be avoided. 
   - Characters of the same type should have similar shift states, when possible.

3. __Compact organization by using dead keys.__ Multiple characters that share an obvious characteristic (best shown in its Unicode naming or block) should be considered to be included in a [dead key](https://en.wikipedia.org/wiki/Dead_key). Dead keys will be highlighted with a bold notice "__Dead key.__", and the mappings should be fully provided for reference. 
   - Dead key base characters should be chosen with the same criteria as normal characters. 
   - If the common characteristic is a diacritic, the base assignment should be the combining diacritic for versatility. If it is not, it should be meaningful as a fallback, or another related character (this is the hard part!). 
   - In dead key mappings, the final base character should be a space (U+0020) that maps to: 1) if diacritic, the diacritic itself alone (modifier letter); 2) if else, the most common character among all options. 
   - The dead key should provide access to this class of characters to the maximum extent, except for those that are rarely used. 

4. __Maximum flexibility under system restraints.__ Due to the restrictions imposed explicitly and implicitly, by MSKLC 1.4, Microsoft frameworks, and related bugs, the scope of design and functionality of this keyboard layout is somewhat restricted. However, under these restrictions, the design will strive to include the most functionality possible without causing compatibility issues. 
   - The range of Unicode characters included is limited. All output only include one character or code point. All output characters are within the Basic Multilingual Plane (BMP) of Unicode (U+0000..U+FFFF). All dead key base assignments are within U+0000..U+0FFF. 
   - Customization is not imposed on control keys, numpad, arrow keys, and function keys. 
   - Dead keys are not chained, and all base characters are available in the normal and `Shift` shift states. 
   - Shift states only include normal, `Shift`, `AltGr` (`Ctrl+Alt`), and `Shift+AltGr` (`Ctrl+Alt+Shift`). Excluded states include `Ctrl`, `Ctrl+Shift`, `SGCaps` (`CapsLock`), and so on.

## Key Mappings
### Numeric row
#### `AltGr` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|
|`` ` ``|`   |U+0300|COMBINING GRAVE ACCENT|**Dead key: Characters with the accent diacritic.** Shape similar to U+0060 GRAVE ACCENT (backtick). Retained from USX layout. |
|`1`|′   |U+2032|PRIME|Math: first (1) derivative. |
|`2`|″   |U+2033|DOUBLE PRIME|Math: second (2) derivative. |
|`3`|‴   |U+2034|TRIPLE PRIME|Math: third (3) derivative. |
|`4`|¤   |U+00A4|CURRENCY SIGN|Retained from USX layout. Related to the `Shift` shift state mapping mapping of U+0024 DOLLAR SIGN. |
|`5`|€   |U+20AC|EURO SIGN|Retained from USX layout. Near other currency characters. |
|`6`|ˇ   |U+030C|COMBINING CARON|**Dead key: Characters with the caron diacritic.** Mirror image of U+0302 COMBINING CIRCUMFLEX ACCENT. |
|`7`|⃗   |U+20D7|COMBINING RIGHT ARROW ABOVE|Physics: vector notation. Shape of 7 similar to right arrow. Near other combining diacritical marks. |
|`8`|∞   |U+221E|INFINITY|Math. Shape similar to a turned 8. |
|`9`|∝   |U+221D|PROPORTIONAL TO|Math. Near U+221E INFINITY. Shape similar to a turned 9, or a turned 8 with an opening. |
|`0`|°   |U+030A|COMBINING RING ABOVE|**Dead key: Characters with a ring above, expanded to related non-math symbols.** Shape similar to 0, also the key is positioned at the top of the keyboard (Thus mapping to key `0` is prioritized over `O`). |
|`-`|–   |U+2013|EN DASH|Punctuation: commonly used as the dash indicating ranges of numbers. Short than U+2014 EM DASH, so mapped to the hyphen which is shorter than the underscore. |
|`=`|ª   |U+00AA|FEMININE ORDINAL INDICATOR|**Dead key: Subscript characters.** Conventionally, the hotkey for subscripts is `Ctrl` + `=` in rich text programms such as MS Word. Also, Unicode provides a full set of subscripts for numbers, which relates to the position of this key (at the top of the keyboard). **Base character and default case** is U+00AA FEMININE ORDINAL INDICATOR in pair with U+00BA MASCULINE ORDINAL INDICATOR, because they are essentially superscripts. |

#### `AltGr` + `Shift` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|
|`~`|˜   |U+0303|COMBINING TILDE|**Dead key: Characters with the tilde diacritic, extended to similar math equality symbols.** Shape similar to U+007E TILDE. Retained from USX layout. |
|`!`|¡   |U+00A1|INVERTED EXCLAMATION MARK|Punctuation: used to begin exclamations in Spanish languages. Partially retained from USX layout, changed shift state for better accordance with U+0021 EXCLAMATION MARK. |
|`@`|√   |U+221A|SQUARE ROOT|Math: second (2) root. |
|`#`|∛   |U+221B|CUBE ROOT|Math: third (3) root. |
|`$`|£   |U+00A3|POUND SIGN|Retained from USX layout. Near other currency characters. |
|`%`|‰   |U+2030|PER MILLE SIGN|Shape and usage similar to U+0025 PERCENT SIGN on the same key. |
|`^`|ˆ   |U+0302|COMBINING CIRCUMFLEX ACCENT|**Dead key: Characters with the caron diacritic.** Shape similar to U+005E CIRCUMFLEX ACCENT on the same key. Retained from USX layout. |
|`&`|¦   |U+00A6|BROKEN BAR|**Dead key: Ligatures, extended to related punctuation symbols.** Usage of U+0026 AMPERSAND related to the fact that ligatures are joined characters. **Base character** is U+00A6 BROKEN BAR because 1) there is no valid and representative character in the set of ligatures, 2) it is an important character also covered in the USX layout, and 3) its shape suggests the idea of joining two objects. **Default case** is U+200D ZERO WIDTH JOINER, commonly used to compose composite graphemes, especially in emojis. |
|‍`*`|⋅   |U+22C5|DOT OPERATOR|Math: dot multiplication. Usage similar to the multiplication meaning of U+002A ASTERISK on this key. |
|`(`|⟨   |U+27E8|MATHEMATICAL LEFT ANGLE BRACKET|Physics: Bra-ket notation left bound. Shape and usage similar to U+0028 LEFT PARENTHESIS. |
|`)`|⟩   |U+27E9|MATHEMATICAL RIGHT ANGLE BRACKET|Physics: Bra-ket notation right bound. Shape and usage similar to U+0029 RIGHT PARENTHESIS. |
|`_`|—   |U+2013|EM DASH|Punctuation: commonly used as the dash indicating breaks in sentences. Longer than U+2014 EM DASH, so mapped to the underscore which is longer than the hyphen. |
|`+`|º   |U+00BA|MASCULINE ORDINAL INDICATOR|**Dead key: Superscript characters.** Conventionally, the hotkey for subscripts is `Ctrl` + `+` in rich text programms such as MS Word. Also, Unicode provides a full set of subscripts for numbers, which relates to the position of this key (at the top of the keyboard). **Base character and default case** is U+00BA MASCULINE ORDINAL INDICATOR in pair with U+00AA FEMININE ORDINAL INDICATOR, because they are essentially superscripts. |

#### Notes
1. There exists U+2057 QUADRUPLE PRIME and U+221C FOURTH ROOT as candidates for key `4`, but they were not chosen because 1) these characters are rarely used (we live in a 3-dimensional world), and 2) there exists reasonable USX layout options to retain (which were used in this layout).
2. The superscripts and subscripts provided are limited intentionally by Unicode, in a way that not every letter in the alphabet has one. Most of these mini letters were coded in the first place for IPA phonetics! It is suggested to always use rich text to achieve such styles for normal text, and this keyboard layout provides these choices only to aid in plain text communication. 
3. For keys `=` and `+`, for the pair of characters U+00BA MASCULINE ORDINAL INDICATOR and U+00AA FEMININE ORDINAL INDICATOR, the decision to map the former to the shifted shift state was based on the fact that masculinity is usually associated with outgoing character. Here no bias on gender and sex is intended; this was solely based on general social observation, which is subject to change as society progresses. It is thoroughly acknowledged that females could express masculinity and vice versa, and there are other gender identities apart from the binary system.  


### QWERTY row
#### `AltGr` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|
|`q`|÷   |U+00F7|DIVISION SIGN|Math. The result of division, quotient, starts with the letter "q". Has same shift state as U+00D7 MULTIPLICATION SIGN (mapped to key `x`), another common math operator. |
|`w`|ϵ   |U+03F5|GREEK LUNATE EPSILON SYMBOL|Shape similar to a turned "w". Key `e` is reserved for "element of"-related (set membership) symbols. |
|`e`|϶   |U+03F6|GREEK REVERSED LUNATE EPSILON SYMBOL|**Dead key: set membership math symbols.** **Base character** has a shape similar to a reversed "e", and is near its mirror image U+03F5 GREEK LUNATE EPSILON SYMBOL. **Default case** is U+2208 ELEMENT OF, which starts with the letter "e". |
|`r`|®   |U+00AE|REGISTERED SIGN|Retained from USX layout. Shape of symbol includes the letter "R". |
|`t`|†   |U+2020|DAGGER|Often used for marking footnotes, also used in math/physics for the conjugate (Hermitian) transpose. Shape similar to letter "t". |
|`y`|±   |U+00B1|PLUS-MINUS SIGN|**Dead key: math symbols comprised of horizontal and vertical lines, such as logical operators.** Shapes similar to the crossed shape of the letter "y", which also notes that the characters in this set could comprise of lines towards all directions. **Base character and default case** is U+00B1 PLUS-MINUS SIGN because it is most commonly used, and is the only character in this set which has a code point that is valid for a dead key. |
|`u`|∪   |U+222A|UNION|Math: set notation. Shape similar to letter "U". |
|`i`|ı   |U+0131|LATIN SMALL LETTER DOTLESS I|Math: imaginary unit in some fields, eg. engineering. Also used in some languages, eg. Azerbaijani, Turkish. Shape similar to letter "i". |
|`o`|ϕ   |U+03D5|GREEK PHI SYMBOL|**Dead key: circle-related math symbols.** Shapes include a circle, similar to shape of letter "o". **Base character and default case** is U+03D5 GREEK PHI SYMBOL, a common Greek variable name in math. Note for Greek language, U+03C6 GREEK SMALL LETTER PHI (φ) is used. |
|`p`|∐   |U+2210|N-ARY COPRODUCT|Math: collection operator in abstract algebra. Mirror image of U+220F N-ARY PRODUCT. |
|`[`|‹   |U+2039|SINGLE LEFT-POINTING ANGLE QUOTATION MARK|Punctuation: left single quotation mark in some European languages. Used in pairs, similar to brackets. Shift state in accordance with single/double quotation marks. 
|`]`|›   |U+203A|SINGLE RIGHT-POINTING ANGLE QUOTATION MARK|Punctuation: right single quotation mark in some European languages. Justification similar to U+2039 SINGLE LEFT-POINTING ANGLE QUOTATION MARK. |
|`\`|↓   |U+2193|DOWNWARDS ARROW|Meaning related to U+005C REVERSE SOLIDUS (backslash) that indicates a falling notion. Mirror image of U+2191 UPWARDS ARROW. |


#### `AltGr` + `Shift` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|
|`Q`|≡   |U+2261|IDENTICAL TO|Math: congruency, equivalence. Related to "equality", which has the letter `q`. This symbol has a stronger mathematical meaning than U+00F7 DIVISION SIGN, and thus is mapped to the shifted shift state. |
|`W`|∑   |U+2211|N-ARY SUMMATION|Math: sigma summation notation. Shape similar to a turned "W". Key `E` is reserved for U+2203 THERE EXISTS, which resembles the letter "E" more. |
|`E`|∃   |U+2203|THERE EXISTS|Math: existential quantifier. Shape similar to a reversed letter "E". |
|`R`|™   |U+2122|TRADE MARK SIGN|Usage highly related to U+00AE REGISTERED SIGN mapped to the same key. |
|`T`|‡   |U+2021|DOUBLE DAGGER|Often used for marking footnotes, also used in chemistry to denote a transition state. Shape similar to letter "t" and U+2020 DAGGER mapped to the same key. |
|`Y`|¥   |U+00A5|YEN SIGN|Shape similar to letter "Y". Near other currency signs. |
|`U`|∩   |U+2229|INTERSECTION|Math: set notation. Mirror image of U+222A UNION mapped to the same key. |
|`I`|ʃ   |U+0283|LATIN SMALL LETTER ESH|**Dead key: integral math symbols.** The name "integral" begins with the letter "i". Also integrals are large math operators, so they are mapped to capital key "I". **Base character and default case** is U+0283 LATIN SMALL LETTER ESH becuase it is a useful latin letter that resembles an integral, while all integral characters in this set have code points that are invalid for a dead key. |
|`O`|∅   |U+2205|EMPTY SET|Math: set notation. Shape similar to letter "O" and U+03D5 GREEK PHI SYMBOL mapped to the same key. |
|`P`|∏   |U+220F|N-ARY PRODUCT|Math: pi multiplication notation. Resembles Greek capital letter pi, which starts with the letter "p". Mirror image of U+2210 N-ARY COPRODUCT. |
|`{`|«   |U+00AB|LEFT-POINTING DOUBLE ANGLE QUOTATION MARK|Punctuation: left double quotation mark in some European languages (eg. French guillemets). Used in pairs, similar to braces. Shift state in accordance with single/double quotation marks. |
|`}`|»   |U+00BB|RIGHT-POINTING DOUBLE ANGLE QUOTATION MARK|Punctuation: right double quotation mark in some European languages (eg. French guillemets). Justification similar to U+00AB LEFT-POINTING DOUBLE ANGLE QUOTATION MARK. |
|`\|`|↑   |U+2191|UPWARDS ARROW|Shape similar to U+007C VERTICAL BAR mapped to this key. Indicates upward motion, which is related to the `Shift` key icon. Mirror image of U+2193 DOWNWARDS ARROW. |

### ASDF row
#### `AltGr` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|
|`a`|ɐ   |U+0250|LATIN SMALL LETTER TURNED A|**Dead key: set inclusion math symbols.** Mainly mapped to this key in accordance with key mappings of set membership symbols and U+2203 THERE EXISTS to key `E`. U+2220 ANGLE is also included for its similar shape with these symbols and its name starting with letter "a". **Base character** has a shape similar to a turned "a". **Default case** is U+2282 SUBSET OF, which is representative. |
|`s`|ß   |U+00DF|LATIN SMALL LETTER SHARP S|Common letter in German language. Shape and usage similar to letter "s". Retained from USX layout. |
|`d`|∂   |U+2202|PARTIAL DIFFERENTIAL|Math: calculus. Shape is essentially a variant of letter "d". |
|`f`|ϝ   |U+03DD|GREEK SMALL LETTER DIGAMMA|Math: variable name. Shape similar to letter "f". Required to be included in UTR25. |
|`g`|γ   |U+03B3|GREEK SMALL LETTER GAMMA|**Dead key: Greek letters, expanded to other math variable letters.** The name "Greek" starts with the letter "g". |



#### `AltGr` + `Shift` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|

### ZXCV row
#### `AltGr` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|


#### `AltGr` + `Shift` shift state
|Key|Char|Unicode|Character|Description|
|:-:|:--:|:-----:|---------|-----------|


	- Keys qQ are assigned to division sign (quotient), identical to (congruency)
	- Keys wW are assigned to varepsilon and n-ary summation (similar to Keys pP); the look like the letters rotated by 90°
	- Keys eE are assigned to element of (DeadKey?) and there exists (similar to Keys aA)
	- Keys rR are assigned to registered sign (from USI) and trade mark sign (related)
	- Keys tT are assigned to dagger and double dagger
	- DeadKey y is for tacks and relations (default up tack, for the more common perpendicular), since y looks like 3 lines extending randomly from a center, showing the vesatile nature of this key; has udrl mapped to up, down, left, right tacks, and amtfATF mapped to assertion, models, true, forces, and their negations excpet for models
	- Key Y is assigned to yen sign
	- Keys uU are assigned to cup (union) and cap (intersection)
	- Keys iI are assigned to mathematical double struck number 1; and integration, 1-4 for multiples, 5-7 for 1-3D contours, 8 for clockwise, 90 for (anti)clockwise contour (since they are under the parentheses symbols)
	- Keys oO are assigned to deadkey for circle operations (default ring operator), +-x/.o*=_ mapped to U+2295..U+229D; and empty set
	- Keys pP are assigned to varphi and n-ary product (similar to Keys wW), since the spelling of the Greek letters begin with p
	- Keys []{} are assigned to single/double French guillemets, usage similar to single/double quotation marks 
	- Keys \| are assigned to double bar and broken bar (latter identical to USI)

- Allocations for ASDFGHJKL;'
	- Keys aA are assigned to deadkey for subset of (default), /|\[]{} mapped to not sub, super, not super, sub or equal, super or equal, neither sub nor equal, neither super nor equal; and for all (similar to Keys eE)
	- Keys sS are assigned to German ss and section sign (identical to USI, alliteration lol)
	- Keys dD are assigned to partial differential and increment delta
	- Keys fF are assigned to digammas, ϝ (U+03DD) and Ϝ (U+03DC)
	- Keys gG are assigned to Greek letters deadkey (default gamma), since Greek starts with g; and nabla ∇ (U+2207), since it is next to ∆ (U+2206), and also means "gradient"
	- Keys hH are assigned to reduced Planck constant and Hilbert space
	- Keys jJkKlL are assigned to left/both/right single/double arrows, commonly used in math; design from the JKL hotkeys in Youtube that toggles playback
	- Keys ;: are assigned to therefore and because, used in math proofs, since they have many dots
	- DeadKeys '" are identical to USI, except that cC maps to the acute versions and not çÇ anymore, this is re-implemented in DeadKey /


- Allocations for ZXCVBNM,./
	- Keys zZ are assigned to ? and deadkey for double-struck font (integer set)
	- Keys xX are assigned to almost equal to and times multiplication; note that this way all multiplication symbols require Shift, while equals, identical to, almost equal to, and unequal to do not
	- Keys cC are assigned to copyright sign and cent sign, identical to USI
	- Keys vV are assigned to vee (logical or) and wedge (logical and)
	- Keys bB are assigned to (deadkey for bold font)
	- Keys nN are assigned to unequal to and not sign, since the not sign is more versatile in meaning NOT
	- Keys mM are assigned to micro sign (compatibility, same as USI), and 
	- Keys ,. are assigned to pilcrow sign, indicating a paragraph sign, like a brief stop in the passage; and deadkey for ellipses, -/|\_. mapped to midline, up right, vertical, down right, normal (default), and middle dot
	- DeadKeys <> are assigned to further less than/greater than inequalities (default ~ or equal to); mapping </+>=~ (example given for less than) to much ~ , not ~, neither ~ nor equal to, neither ~ nor ~, ~ over equal to, ~ or equivalent to
	- Keys /? are assigned to deadkey for stroked letters (default combining long soldius overlay), including nonstandard behaviour of mapping cC to çÇ; and inverted question mark ¿


ÇçĢģĶķĻļŅņŖŗŞşŢţḐḑḨḩ



- Mathematical Greek letters are fully supported as in https://www.unicode.org/reports/tr25/
	- uppercase Greek letters Α - Ω (U+0391..U+03A9), plus the nabla ∇ (U+2207), digamma Ϝ (U+03DC), and the variant of theta Θ given by U+03F4 (ϴ)
	- lowercase Greek letters α - ω (U+03B1..U+03C9), plus the partial differential sign ∂ (U+2202), digamma ϝ (U+03DD), and the six glyph variants of ε, θ, κ, φ, ρ, and π, given by U+03F5 (ϵ), U+03D1 (ϑ), U+03F0 (ϰ), U+03D5 (ϕ), U+03F1 (ϱ), and U+03D6 (ϖ).
	- the normal Greek letters are accessed via DeadKey g, layout identical to the Greek keyboard; the diacritics are removed, while Key w is retained as the final small sigma. Exceptions are Keys QqW, respectively U+03F4 (ϴ), U+03D1 (ϑ), and U+03D6 (ϖ), due to the similar shapes
	- Keys dD are ∂ (U+2202) and ∆ (U+2206)
	- Key G is ∇ (U+2207), since it is next to ∆ (U+2206), and also means "gradient"
	- Keys fF are the two digammas
	- Keys wp are U+03F5 (ϵ) and U+03D5 (ϕ)
	- Keys 1234 are the first four capital Herbrew letters, used in math
	- Keys 56 are for U+03F0 (ϰ) and U+03F1 (ϱ), they are put here since they seem less common and less related than to the others, but coincidently have consecutive Unicode datapoints :)


## Bugs found in MSKLC - but it's a program that's almost older than myself!
1. For some reason, when I tried to rename the description of a custom keyboard based on United States-International, the 1st line in the .klc file changed, but the DESCRIPTION section at the bottom of the file remained "United States-International - Custom", which was unchangeable. 
2. Sometimes there is a newline between the DESCRIPTION section and the LANAGUAGE section, and sometimes not
3. [Major issue] Deadkeys that have a base of greater than U+1000 will fail to work when their .dll is created, and they seem to be defined errorenously, since when the corresponding keys are pressed, Windows system gives off an alarm noise, instead of the normal no response when a key combination that is not defined is called. When the built custom keyboard is then loaded into MSKLC, the deadkeys are blank and no codepoint designation can be seen. 
	- Tested base codepoints: mutiple codepoints greater than U+2100 (in the math symbols section), U+2000, U+1ffd, U+1800, U+1000, [U+0fda, U+0f00, U+0e01, U+0a01, U+0800, U+0308] (in brackets = success)
	- The original author seemed to be aware of this problem since 2008, but it is still not resolved. This is probably due to an internal Microsoft restriction (which has no reason at all :/)
4. [Major issue] For normal keys, there is also an upper limit restriction found at roughly U+10000, which means that only the codepoints in the BMP (U+0000 - U+ffff) can be accessed. For example, an attempt to include U+1d7d9 failed. 



- R.I.P Michael Scott Kaplan (*1970/02/27 Creve Coeur — †2015/10/21 Redmond), Microsoft developer and the very creator of MSKLC. He passed away at age 45 from multiple sclerosis, a disease he fought against for 25 years. 
	- [His obiturary](https://obits.cleveland.com/us/obituaries/cleveland/name/michael-kaplan-obituary?id=20110483)
	- [A podcast with him](https://www.hanselminutes.com/117/sorting-out-internationalization-with-michael-kaplan)
	- [His blog archive](http://archives.miloush.net/michkap/archive/) (which contains many, many stories):
	- He was a very talented and responsible person, with good humor and writing… He had a colorful life: conflicts with Microsoft, battles with fatal diseases, affairs with prostitutes, and fun blogs that were brought to the readers by a unique Unicode character. 
	- [Unicode's Memoriam Page](https://www.unicode.org/consortium/memoriam.html) includes his name. Mr. Kaplan, you shall be remembered.
