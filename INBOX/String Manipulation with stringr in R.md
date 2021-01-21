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

#### library(rebus)
Build regular expressions in a human readable way.

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


## Pattern matching with regular expressions

## More advanced matching and manipulation