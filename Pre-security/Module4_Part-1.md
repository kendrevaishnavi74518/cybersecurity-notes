## Data Representation

- Bit: It can be 0 or 1.
- Group of 8 bits is referred to as a byte,(we can also use the term octet).
- Hex color - Color represented as combination of red,blue & green, we can get 16 million color combinations.
- Hexadecimal representation - Makes combining 4 bits into a single character easy. 
   - Hexadecimal digit ranges between 0 & F.
   - Digits 10,11,12,13,14,15 are replaced with single letter, A,B,C,D,E & F.
## Binary Numbers

- Binary system is limited to 2 digits(0 or 1).
- It uses the binary (base-2) system.
- Decimal numbers uses the decimal (base-10) system.
<br>

## Octal Numbers
- Octal refers to base-8 system.
- It uses base-8 and groups 3 bits.
- Ranges between 0 to 7.

<br>

## Data Encoding

**ASCII**
- It stands for American Standard Code for Information Interchange, introduced in 1963, uses numbers 0-127 to represent English letters,digits,punctuation & some control characters.
- **'A' stands for American.**
- Original ASCII was limited to 7 bits, it acts as a small bilingual dictionary between text & numeric codes.
- Digits(0-9): ASCII values from 48 to 57('0' is 48,'9' is 57).
- Uppercase(A-Z): ASCII values from 65 to 90.
- Lowercase(a-z): ASCII values from 97 to 122.
- Space character has decimal value 32.
- Control characters(0-31,127) - Used for new lines or backspaces rather than text.
<br>

## European Languages
- The ISO/IEC 8859 Series(International Standards) created standards for representing europeam languages.
   - ISO-8859-1(Latin-1) - Covers western european languages like German (ß, ü), French (é, ç), Spanish (ñ, ¿), Italian, Portuguese, Catalan, and Nordic languages (e.g., Icelandic ð/Ð). 
   - ISO-8859-2(Latin-2) - Covers central/eastern european languages like Polish (ł, ń), Czech (č, ř), Hungarian (ő, ű), Croatian (đ), Romanian (ș, ț), and Slovak.
<br>

## Unicode
- It is a universal character encoding standard, it assigns unique code points to characters from all modern & historical writing systems.
- It supports the interchange, processing & display of text in diverse languages.
- Unicode 17.0 is currently the latest version.It defines close to 157 thousand characters, almost 4,000 of them are emoji sequences.
<br>

## UTF-8,UTF-16,UTF-32

- ASCII characters (U+0000 to U+007F) use exactly 1 byte, ensuring seamless backward compatibility.
- Non-ASCII characters like Ω (U+03A9) use 2 bytes, while complex scripts or emoji like 🔥 (U+1F525) require 4 bytes.
<br>

- UTF-16 uses either 2 or 4 bytes per character, common characters, like most Latin, Cyrillic, or Chinese Hanzi, fit in 2 bytes; Rarer ones, like emoji or ancient scripts, require a pair, i.e., two 16-bit units totaling 4 bytes.
- UTF-32 is the simplest but also the most wasteful; every Unicode code point uses exactly 4 bytes. 
