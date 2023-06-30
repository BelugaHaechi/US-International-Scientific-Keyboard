# US International Scientific Keyboard

__A very powerful custom keyboard for Windows, tailored for efficient and convenient output of international alphabetical languages and scientific notation in plain text.__

This keyboard is easy to install, easy to use, and easy to memorize, while having extensive capabilities covering common Latin letters, diacritics, mathematical symbols, additional punctuation, and some mathematical font letters. It is recommended for those who often work in __STEM__ fields on a __Windows__ system, and have collaborations with co-workers from __diverse language backgrounds__. It is also intended as a better alternative to the United States-International keyboard that had dead keys inconveniently bound on commonly used keys. 

> Note: This keyboard is **not a replacement for proper scientific notation** that can be formatted using rich-text programs like $\LaTeX$ or MathML, but rather a method to extend the symbols available in plain text input scenarios, e.g. texting, using Notepad, non-technical writing._

The keyboard was created using Microsoft Keyboard Layout Creator 1.4 (MSKLC 1.4). It is based on the __English (United States) QWERTY keyboard__, and some layout designs are consistent with the _United States-International keyboard_. Some ideas were inspired by and improved on the basis of [Michael Goerz's version](https://michaelgoerz.net/notes/the-us-international-scientific-keyboard-layout.html) of the "U.S. International - Scientific" keyboard layout for Mac systems. 

## Quick Start Guide
Setting up this keyboard on your computer is very simple! 
0. (_Recommended_) Be logged in to the Administrator account on your computer. Configuring the keyboard will require Administrator permission. 
1. Download the folder `KBDUSX3` in this repository to any directory on your computer.
2. Open the folder, and run the program `setup.exe` in the folder. Do not alter or delete any other files in the folder. 
3. Follow the setup instructions that will pop up. At some point, you will be asked for Administrator permission; please allow to continue.
4. Now the keyboard is installed on your computer! The last step is to enable the layout in Settings.
* Open Settings on your computer.
* Navigate to `Time & language > Language & region > Keyboards` (this may differ slightly for various Windows versions).
* Select `Add a keyboard`, and select `US-International and Scientific keyboard` in the drop-down menu.
* (_Recommended_) You can now disable the original `US keyboard (QWERTY)`, since its functions could be completely replaced by the new keyboard.
5. Congratulations! You are now all set to use the US International Scientific keyboard on your computer.

> Tip: You may wish to retain the `KBDUSX3` folder, because it could be used to repair/uninstall the keyboard layout on your computer. Don't worry if you accidentally deleted it anyways, as you could download it again from this repository anytime. 

## Update / Uninstallation Guide
Uninstallation 


## Content below is Work In Progress, please wait for the official release

## Core Design Ideas
0. __Compatibility.__ _The US QWERTY keyboard layout remains unchanged_, and all extensions are "hidden" in the `AltGr` (`Ctrl+Alt`) and `Shift+AltGr` (`Ctrl+Alt+Shift`) shift states. Therefore it will be just an ordinary layout under normal use, and fits with its positioning as a "keyboard extension".   
   Also, key mappings from the original United States-International keyboard are retained whenever appropriate, so that it aligns with Microsoft design and users switching over will find it more familiar to work with. These mappings with be denoted with a `(USX)` mark, referencing the Windows `KBDUSX.dll` file containing setup information. 
1. __Logicality.__ Every key mapping should always _make as much sense as possible_ and provide convenience for both multilingual and mathematical input. Every reason for a certain mapping should be explicitly documented, and alternatives should be discussed if any. 
  - At least one among name, shape, usage, etc. of the character allocated should be related with the key that it is mapped to. 
  - Common characters should be easy to access, while uncommon characters should be set further out of reach, and rare and awkward characters should be avoided. 
  - Characters of the same type should have similar shift states, when possible. 
2. __Usage of dead keys.__ Multiple characters that share an obvious characteristic (best shown in its Unicode naming or block) should be considered to be included in a [dead key](https://en.wikipedia.org/wiki/Dead_key). Dead keys will be highlighted with a bold notice "__Dead key.__", and the mappings should be fully provided for reference. 
  - Dead key base characters should be chosen with the same criteria as normal characters. 
  - If the common characteristic is a diacritic, the base assignment should be the combining diacritic for versatility. If it is not, it should be meaningful as a fallback, or another related character (this is the hard part!). 
  - In dead key mappings, the final base character should be a space (U+0020) that maps to: 1) if diacritic, the diacritic itself alone (modifier letter); 2) if else, the most common character among all options. 
  - The dead key should provide access to this class of characters to the maximum extent, except for those that are rarely used. 
3. __Restricted.__ Due to the restrictions imposed explicitly and implicitly, by MSKLC 1.4, Microsoft frameworks, and related bugs, the scope of design and functionality of this keyboard layout is somewhat restricted. However, under these restrictions, the design will strive to include the most functionality possible without causing compatibility issues. 
  - The range of Unicode characters included is limited. All output only include one character or code point. All output characters are within the Basic Multilingual Plane (BMP) of Unicode (U+0000..U+FFFF). All dead key base assignments are within U+0000..U+0FFF. 
  - Customization is not imposed on control keys, numpad, arrow keys, and function keys. 
  - Dead keys are not chained, and all base characters are available in the normal and `Shift` shift states. 
  - Shift states only include normal, `Shift`, `AltGr` (`Ctrl+Alt`), and `Shift+AltGr` (`Ctrl+Alt+Shift`). Excluded states include `Ctrl`, `Ctrl+Shift`, `SGCaps` (`CapsLock`), and so on.



## Key Mappings
### Numeric row (`\`1234567890-=`)
	- DeadKeys `~ are identical to USI, for grave and tilde. Except for tilde, there is an extra = congruent
	- Keys 123 are prime signs, from single to triple; there exists a quadruple prime, but not included
	- Key ! is inverted ¡
	- Keys @# are square root and cubic root, common math symbols
	- Keys 4$5 is identical to USI, currency ¤, pound £, Euro €
	- Key % is per mille
	- DeadKeys 6^ are CDMs for caron and circumflex, which are symmetries
	- Key 7 is a CDM for right arrow (vector), since the 7 looks like an right arrow (harpoon), while near Keys 6^& that are already CDMs
	- DeadKey & base non-breaking space, default to Zero Width Joiner, mapped to ae/oe/ij/nj/dz ligatures, also upside down &
	- Keys 89 are infinity and proportional to, looks like the numbers rotated by 90°
	- Key * is the dot operator, for multiplication
	- DeadKey 0 base combining top ring, default is the degrees sign, mapping Keys CFaAuU respectively to Celsius, Fahrenheit, å, Å, ů, Ů, o to ring operator, - to U+1db1 modifier latin small barred o
	- Keys () are mathematical angular brackets for quantum physics
	- Keys -_ are en dash and em dash
	- DeadKeys =+ are for subscript and superscript, referencing the Ctrl+"="/"+" hotkeys in MS Office; available Keys are 1234567890-=+() for both, and the rest of the letters are incomplete due to intentions of Unicode, default cases are plus and minus, minus and plus


### QWERTY row (`QWERTYUIOP[]\`)
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


### Bugs found in MSKLC - but it's a program that's almost older than myself!
1. For some reason, when I tried to rename the description of a custom keyboard based on United States-International, the 1st line in the .klc file changed, but the DESCRIPTION section at the bottom of the file remained "United States-International - Custom", which was unchangeable. 
2. Sometimes there is a newline between the DESCRIPTION section and the LANAGUAGE section, and sometimes not
3. [Major issue] Deadkeys that have a base of greater than U+1000 will fail to work when their .dll is created, and they seem to be defined errorenously, since when the corresponding keys are pressed, Windows system gives off an alarm noise, instead of the normal no response when a key combination that is not defined is called. When the built custom keyboard is then loaded into MSKLC, the deadkeys are blank and no codepoint designation can be seen. 
	- Tested base codepoints: mutiple codepoints greater than U+2100 (in the math symbols section), U+2000, U+1ffd, U+1800, U+1000, [U+0fda, U+0f00, U+0e01, U+0a01, U+0800, U+0308] (in brackets = success)
	- The original author seemed to be aware of this problem since 2008, but it is still not resolved. This is probably due to an internal Microsoft restriction (which has no reason at all :/)
4. [Major issue] For normal keys, there is also an upper limit restriction found at roughly U+10000, which means that only the codepoints in the BMP (U+0000 - U+ffff) can be accessed. For example, an attempt to include U+1d7d9 failed. 



- R.I.P Michael Scott Kaplan (*1970/02/27 Creve Coeur — †2015/10/21 Redmond), Microsoft developer and the very creator of MSKLC. He passed away at age 45 from multiple sclerosis, a disease he fought against for 25 years. 
	- His obiturary: https://obits.cleveland.com/us/obituaries/cleveland/name/michael-kaplan-obituary?id=20110483
	- A podcast with him: https://www.hanselminutes.com/117/sorting-out-internationalization-with-michael-kaplan
	- His blog archive (which contains many, many stories): http://archives.miloush.net/michkap/archive/
	- He was a very talented and responsible person, with good humor and writing... He had a colorful life: conflicts with Microsoft, battles with fatal diseases, affairs with prostitutes, and fun blogs that were brought to the readers by a unique Unicode character. 
	- Unicode's Memoriam includes his name, at https://www.unicode.org/consortium/memoriam.html. Mr. Kaplan, you shall be remembered.
