---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=vgYS-F8opgE)

# Debugging Methods in the R Ecosystem
Infamous error message: Object of type ‘closure’ is not subsettable

## General strategies for coping with confusing and frustrating situations

Turn it off and on again
Make a reprex
Dig into the error
Plan for the unexpected

### What's your main debugging method?
A. I don't have a method.
B. I ask in an online forum or consult my local expert.
C. I Google it.
D. Print debugging.
E. I use R's debugging tools, like browser()

Debugging usually tend to be reactive. We don't spend time learning proactive debugging skills.

### Reset
This should be your first strategy.
Restart R. Especially when things get weird.
A common reason why it works is because we update and install packages while we work and things might get funky.
Ctrl + Shift + F10.
Don't save your workspace when you quit R and don't load it when you restart.
`R --n-save --no-restore-data`
Superior to `rm(list = ls())`

#### What persist after rm(list = ls())?
A. library(dplyr)
B. summary <- head
C. options(stringAsFactors = FALSE)
D. Sys.setenv(LANGUAGE  = "fr")
E. x <- 1:5
F. attach(iris)

A, C, D, F persist.

#### A Fresh Start
Cleans workspace
Resets options and env vars
Clears search path

This works well with some other habits such as saving your sources. Otherwise, killing your workspace might be costly.

### Reprex
reprex package.
Reprex mindset. Working on a small concrete example that reveals, confirms, or eliminates something

#### Reprex: Minimum Reproducible Example.
Making reprex is a science and an art.
The reproducible part is the science.
The art aspect is to make it minimal.

Reproducible: no reliance on hidden state.

Also important, there's the problem of what you think or say you are doing and what you are actually doing.

Try to make the code as small and as simple as possible.

Minimal
* Inputs are small and simple
* No extraneous packages
* No unnecessary function calls

Why make a reprex?
Help them help you but more importantly, you tend to solve your own problem.

### Debug
Order of what you can try and order of how much control you have.

traceback(): Gve some spare facts about the error
options(error = recover) : Inspect the error call stacks.
browser() : Interrupt before the error.

rlang::last_trace() give an alternative view to traceback().
New takes at how to present the call stack.
Designed with readibility in mind.

options(error = recover) pause execution and allows to look at frames, the environment corresponding to the different function calls.
ls.str() to see objects that exists.

Insert a call to browser() before the error inside the body of the function.
In RStudio, you can put IDE breakpoints
Browse by line with n.
Unlike other debugging mode, you can redefine variables.

debug() and undebug()
debugonce()

### Deter
If you fix something, make sure it stays fixed.
Add a test.
Add an assertion.
Automate your checks.
R CMD check for packages
testthat::test_check()
Run your checks on their machine
Leave access panels
Write error messages for humans