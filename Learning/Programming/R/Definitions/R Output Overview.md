---
aliases:
tags: R
---
Link: [Discussion](https://stackoverflow.com/questions/36699272/why-is-message-a-better-choice-than-print-in-r-for-writing-a-package)

### TL;DR
You should use `cat()` when making the `print.*()` functions for S3 objects. For everything else, you should use `message()` unless the state of the program is problematic. e.g. bad error that is recoverable gives `warning()` vs. show stopping error uses `stop()`.

# R Output Overview
The traditional output functions are:

1.  [`print()`](https://stat.ethz.ch/R-manual/R-patched/library/base/html/print.html)
2.  [`cat()`](https://stat.ethz.ch/R-manual/R-patched/library/base/html/cat.html)
3.  [`message()`](https://stat.ethz.ch/R-manual/R-patched/library/base/html/message.html)
4.  [`warning()`](https://stat.ethz.ch/R-manual/R-patched/library/base/html/warning.html)
5.  [`stop()`](https://stat.ethz.ch/R-manual/R-patched/library/base/html/stop.html)

Now, the first two functions (`print()` and `cat()`) send their output to stdout or standard output. The last three functions (`message()`, `warning()`, and `stop()`) send their output to stderr or the standard error. That is, the result output from a command like `lm()` is sent to one file and the error output - if it exists - is sent to a completely separate file. This is particularly important for the user experience as diagnostics then are not cluttering the output of the results in log files and errors are then available to search through quickly. 

### print()
This function has some severe limitations. One of them being the lack of embedded concatenation of terms. The second, and probably more severe, is the fact that each output is preceded by [x] followed by quotations around the actual content. The x in this case refers to the element number being printed. This is helpful for debugging purposes, but outside of that it doesn't serve any purpose.

For concatenation, we rely upon the `paste()` function working in sync with print():

Alternatively, one can use the `paste0(...)` function in place of paste(...) to avoid the default use of a space between elements governed by `paste()`'s `sep = " "` parameter. (a.k.a concatenation without spaces)

### cat()
On the flip side, `cat()` addresses all of these critiques. Most notably, the sep=" " parameter of the paste() functionality is built in allowing one to skip writing paste() within cat(). However, the cat() function's only downside is you have to force new lines via `\n` appended at the end or fill = TRUE (uses default print width). 

### message()
The `message()` function is one step better than even `cat()`! The reason why is the output is distinct from traditional plain text as it is directed to stderr instead of stdout. E.g. They changed the color from standard black output to red output to catch the users eye. Furthermore, you have the built in` paste0()` functionality. Moreover, message() provides an error state that can be used with `tryCatch()`.

### warning()
The `warning()` function is not something to use casually. The warning function is differentiated from the message function primarily by having a line prefixed to it ("Warning message:") and its state is consider to be problematic. Misc: Casual use in a function may inadvertently trigger heartbreak while trying to upload the package to CRAN due to the example checks and warnings normally being treated as "errors".

### stop()
Last but not least, we have `stop()`. This takes warnings to the next level by completely killing the task at hand and returning control back to the user. Furthermore, it has the most serious prefix with the term "Error:" being added.