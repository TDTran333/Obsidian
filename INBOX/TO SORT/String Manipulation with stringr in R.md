---
tags: R
---

# String Manipulation with stringr in R

## String basics
### When to use \" vs \'
* No quotes in the string, use double quotes
* Doubles quotes in the string, use single quotes
* Doubles and single quotes in the string, use double quotes
* Note: You can escape quotes inside strings using a backslash.

### Entering strings
##### writelines()
Write text lines to a connection. By default, show one string per line.

The function `cat()` is very similar to `writeLines()`, but by default separates elements with a space, and will attempt to convert non-character objects to a string.

A sequence in a string that starts with a `\` is called an _escape sequence_ and allows us to include special characters in our strings. http://www.unicode.org/charts/

When R comes across a `\` it assumes you are starting an escape, so if you actually need a backslash in your string you'll need the sequence `\\`.

### Turning numbers into strings
Fixed and scientific formats
* Fixed: decimal point between ones and tenths
* Scientific: decimal point after first digit
* The advantage of scientific notation is that very large and very small numbers can be written quite concisely.

##### format()
Encode in a Common Format. scientific = TRUE / FALSE

When the representation is scientific, the `digits` argument is the number of digits before the exponent. When the representation is fixed, `digits` controls the significant digits used for the smallest (in magnitude) number. Each other number will be formatted to match the number of decimal places in the smallest number. This means the number of decimal places you get in your output depends on **all** the values you are formatting!

By default `format()` will pad the start of the strings with spaces so that the decimal points line up, which is really useful if you are presenting the numbers in a vertical column. However, if you are putting the number in the middle of a sentence, you might not want these extra spaces. You can set `trim = TRUE` to remove them.

###### arguments: big.interval and big.mark

##### prettynum()
`prettyNum()` is used for “prettifying” (possibly formatted) numbers

##### formatC()
Formatting Using C-style Formats. format = "f" / "e" / "g"
-   `"f"` for fixed,
-   `"e"` for scientific, and
-   `"g"` for fixed unless scientific saves space

When using fixed format, `digits` is the number of digits after the decimal point.

###### flag argument
The `flag` argument allows you to provide some modifiers that, for example, force the display of the sign (`flag = "+"`), left align numbers (`flag = "-"`) and pad numbers with leading zeros (`flag = "0"`).

### Putting strings together
##### paste()  / paste0()
Concatenate Strings.

-   The vectors you pass to [`paste()`](https://www.rdocumentation.org/packages/base/topics/paste) are pasted together element by element, using the `sep` argument to combine them.
-   If the vectors passed to [`paste()`](https://www.rdocumentation.org/packages/base/topics/paste) aren't the same length, the shorter vectors are recycled up to the length of the longest one.
-   Only use `collapse` if you want a single string as output. `collapse` specifies the string to place between different elements.

## Introduction to stringr
#### library(stringr)
* Powerful but easy to learn
* Built on stringi
* Concise and consistent
* All functions start with str_
* All functions take a vector of strings as the first argument

##### str_c()
Join multiple strings into a single string.

There are two key ways `str_c()` differs from `paste()`. 
* First, the default separator is an empty string, `sep = ""`, as opposed to a space, so it's more like `paste0()`.
* The second way `str_c()` differs to `paste()` is in its handling of missing values. `paste()` turns missing values into the string `"NA"`, whereas `str_c()` propagates missing values. That means combining any strings with a missing value will result in another missing value. This behavior is nice because you learn quickly when you might have missing values, rather than discovering later weird `"NA"`s inside your strings.

##### str_length()
The length of a string.

##### str_sub()
Extract and replace substrings from a character vector.

The arguments `start` and `end` specify the boundaries of the piece to extract in characters. Both `start` and `end` can be negative integers, in which case, they count from the end of the string.

`substr()`, a base R function, is similar to `str_sub()`. The big advantage of `str_sub()` is the ability to use negative indexes to count from the end of a string.

### Matching pattern
##### str_detect()
Detect the presence or absence of a pattern in a string.

##### fixed()
Compare literal bytes in the string.

##### str_subset()
Keep strings matching a pattern, or find positions.

##### str_count()
Count the number of matches in a string.

### Splitting strings
##### str_split()
Split up a string into pieces. Return a list.

###### argument: simplify = TRUE to return a matrix.

### Replacing matches in strings
##### str_replace() and str_replace_all()
Replace matched patterns in a string.

`str_replace()` takes three arguments, `string` a vector of strings to do the replacements in, `pattern` that identifies the parts of strings to replace and `replacement` the thing to use as a replacement.

`replacement` can be a vector, the same length as `string`, each element specifies the replacement to be used in each string.

## Pattern matching with regular expressions
### Regular expressions
*  A language for describing patterns

#### library(rebus)
Build regular expressions in a human readable way.

`rebus` provides `START` and `END` shortcuts to specify regular expressions that match the start and end of the string. These are also known as _anchors_.

`rebus` also provides the function `exactly(x)` which is a shortcut for `START %R% x %R% END` that matches only if the string is exactly `x`.

In a regular expression you can use a wildcard to match a single character, no matter what the character is. In `rebus` it is specified with `ANY_CHAR`.

`ANY_CHAR` will only ever match one character.

_Regular expressions are lazy and will take the first match they find._

##### str_view() and str_view_all()
View HTML rendering of regular expression match.

##### str_extract() and str_extract_all
Extract matching patterns from a string.

| Pattern                    | Regular Expression | rebus              |
| -------------------------- | ------------------ | ------------------ |
| Start of string            | ^                  | START              |
| End of string              | $                  | END                |
| Any single character       | .                  | ANY_CHAR           |
| Literal dot, carat, dollar | \., \^, \$         | DOT, CARAT, DOLLAR |

### Alternation
The `rebus` function `or()` allows us to specify a set of alternatives, which may be single characters or character strings, to be matched.

### Character classes
In regular expressions a _character class_ is a way of specifying "match one (and only one) of the following characters". In `rebus` you can specify the set of allowable characters using the function `char_class()`.

A negated character class matches "any single character that isn't one of the following", and in `rebus` is specified with `negated_char_class()`.

Unlike in other places in a regular expression you don't need to escape characters that might otherwise have a special meaning inside character classes. If you want to match `.` you can include `.` directly, e.g. `char_class(".")`. Matching a `-` is a bit trickier. If you need to do it, just make sure it comes first in the character class.

### Repetition
| Pattern               | Regular Expression | rebus          |
| --------------------- | ------------------ | -------------- |
| Optional              | ?                  | optional()     |
| Zero or more          | *                  | zero_or_more() |
| One or more           | +                  | one_or_more()  |
| Between m and n times | {m,n}              | repeated()     | 

### Shortcuts
Specify a range with a dash inside a character class.
`DGT`
`WRD`
`SPC`
`DOT`
`LOWER`
`OPEN_PAREN`
`CLOSE_PAREN`
`ASCII_UPPER`
`dgt(1, 2)` to match one or two digits

##### ls.str()
List Objects and their Structure

##### str_remove()
Remove matched patterns in a string.

## More advanced matching and manipulation

### Capturing
In `rebus`, to denote a part of a regular expression you want to capture, you surround it with the function `capture()`.

##### str_match()
Extract matched groups from a string.

### Backreferences
Backreferences can be useful in matching because they allow you to find repeated patterns or words. Using a backreference requires two things: you need to `capture()`the part of the pattern you want to reference, and then you refer to it with `REF1`.

If you capture more than one thing you can refer to them with `REF2`, `REF3` etc. up to `REF9`, counting the captures from the left of the pattern.

The `replacement` argument to `str_replace()` can also include backreferences. This works just like specifying patterns with backreferences, except the capture happens in the `pattern` argument, and the backreference is used in the `replacement` argument.

### Unicode and pattern matching
Unicode
* Associates each character with a code point

Unicode in R
* \u followed by 4 digits code
* \U followed by up to 8 digits code

Hexadecimal code
* as.hexmode(utf9ToInt("symbol"))

Matching Unicode groups
* Regular expression
	* Use \p followed by {name}
* rebus
	* str_view_all(x, greek and coptic()) 

The `stringi` package that `stringr` is built on contains functions for converting between the two forms. `stri_trans_nfc()` composes characters with combining accents into a single character. `stri_trans_nfd()` decomposes character with accents into separate letter and accent characters.

In Unicode, an accent is known as a _diacritic Unicode Property_, and you can match it using the `rebus` value `UP_DIACRITIC`.

`ANY_CHAR` will only match a character represented by a single code point.

The Unicode standard has a concept of a _grapheme_ that represents a display character, but may be composed of many code points. To match any _grapheme_ you can use `GRAPHEME`.

### Case study

##### readLines()
Read Text Lines from a Connection.

##### stri_read_lines()
Reads a text file in its entirety, re-encodes it, and splits it into text lines.

##### stri_isempty()
Determine if a String is of Length Zero.

##### or1()
It specifies alternatives but rather than each alternative being an argument like in `or()`, you can pass in a vector of alternatives.

### regex are case sensitive
#### Changing case to ease matching
* A simple solution to working with strings in mixed case, is to simply transform them into all lower or all upper case.

##### whole_word()
`whole_word()` will only match if it occurs as a word on its own.

#### Ignoring case when matching

##### regex()
The default. Uses ICU regular expressions.

we wrap our pattern in `regex()` and specify the argument `ignore_case = TRUE`

#### Transform string to common case
You can use `str_to_upper()` and `str_to_lower()`, but there is also `str_to_title()` which transforms to title case, in which every word starts with a capital letter.

##### stri_trans_totitle()
Allows a specification of the `type` which, by default, is `"word"`, resulting in title case, but can also be `"sentence"` to give sentence case: only the first word in each sentence is capitalized.
