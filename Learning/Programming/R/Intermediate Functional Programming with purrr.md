---
aliases: intermediate purrr
tags: R
---

# Intermediate Functional Programming with purrr

## Programming with purrr
### purrr basics
`map(.x, .f, ...)` : for each element of .x do .f(.x, ...) and return a list
`map2(.x, .y, .f, ...)` : for each element of .x and .y, do .f(.x, .y, ...) and return a list
`pmap(.l, .f, ...)` : for each **sublist** of .l, do .f(..1, ..2, ..3, \[etc], ...) and return a list

### Introduction to mappers
.f as a function
* Classic function
* Lambda function, also known as an anonymous function.

mapper: anonymous function with a one-sided formula. `map(list, ~ .x)`
`as_mapper()`: create mapper objects from a lambda function. They behave exactly like functions.

Why use mappers?
* They are more concise
* They are easier to read than functions
* They are reusable

When coding, if you have to copy and paste something more than twice, you should write a function. In purrr, if you have to use a mapper more than twice, save it with `as_mapper()`.

### Using mappers to clean up your data
##### set_names()
Sets the names of an unnamed list

##### keep()
Extract elements that satisfy a condition

##### discard()
Remove elements that satisfy a condition

`keep()` and `discard()` are complimentary. It's easier to switch from `keep()` to `discard()` than copying and pasting. By combining both functions, we only need one mapper. That means that if we want to change the threshold, we'll only need to do it once.

### Predicates
Predicates return TRUE or FALSE after testing for conditions
They exist in base R: `is.numeric()`, `%in%`,` is.character()`, etc.

Predicate functionals:
* Take an element & a predicate
* Use the predicate on the element

##### every()
Does every element satisfy a condition?

##### some()
Do some elements satisfy a condition?

##### detect_index()
Returns the index of the first or last element that satisfies the condition

##### detect()
Returns the value, not the index

##### has_element()
Tests if an object contains specific elements

## Functional programming: from theory to practice
### Computation in R
> "To understand computation in R, two slogans are helpful:
> - Everything that exists is an object.
> - Everything that happens is a function call."
> &mdash; <cite>John Chambers</cite>

An object, in the sense of a data structure, is composed of a name and a value.
This also means that a function is an object, and it can be treated and manipulated as such.
Every computation that happens in R is due to a function.

### R as a functional programming language
Functions can be:
* manipulated
* stored in a variable
* lambda
* stored in a list
* arguments of a function
* returned by a function

#### About "pure functions"
purrr was first designed to handle pure functions.

In a pure function:
* Its output only depends on its inputs: when you input a value, the output is always the same. Everything needed in a function needs to be passed as a parameter.
* It has no side-effect, that is to say, no effect outside the function. No change in the environment.

#### Impure functions are useful
A lot of functions in R are not pure, yet they are vital for a day to day use of R: when doing an analysis, you need to download files, create a plot, save results…

Impure functions:
* Depend on environment
* Have "side-effects"

### Tools for functional programming in purrr
#### High order functions
A high order function can:
* Take one or more functions as arguments
* Return a function

In other words, they are functions that manipulate functions.

Three types of high order functions
* Functionals: Take another function and return a vector. This is what map_\*() do.
* Function factories: Take a vector as input and create a function. 
* Function operators: Take one or more functions and return a function as output. They are called **adverbs** in purrr.

In tidyverse terminology, functions that take data and compute a value are called verbs.

#### Adverbs in purrr
Handling errors and warnings:
* `possibly()`
* `safely()`

One downside of iterations is that if the process fail, you won't be able to access the results and will need to restart the process. Using `safely()` allows running the iterations until the end.

safely() returns a function that will return:
* $result
* $error

If we use `safely()` inside `map()`, we can iterate over a list safely, and get the result when there is one. This is particularly useful in web scrapping as some url might not work anymore.

#### Extracting elements from `safely()` results
We can extract the results element or the error element by piping into `map("result")` or `map("error")`.

```R
safe_read <- safely(read_lines)
safe_read_discard <- function(url){
 safe_read(url) %>%
 discard(is.null)
}
res <- map(urls, safe_read_discard)
```

#### Using possibly()
`possibly()` creates a function that return either:
* the result
* the value of otherwise
	* A logical
	* A character
	* A NA
	* A number

Use `possibly()` when we are not interested in why the function failed. We just want to know which function call succeeded.

We are trying several methods to identify URLs that can't be accessed. Why are we doing that? Because the first step of web scraping is analyzing if you can access the URL or not.
```R
possible_read <- possibly(read_lines, otherwise = 404)
res <- map(urls, possible_read) %>% set_names(urls)
res_pasted <- map(res, paste, collapse = " ")
keep(res_pasted, ~.x == "404")
```
```R
url_tester <- function(url_list){
 url_list %>%
 map( possibly(read_lines, otherwise = 404) ) %>%
 set_names( url_list ) %>% 
 map(paste, collapse = " ") %>%
 keep(~.x != "404") %>%
 names() 
}
url_tester(urls)
```

#### Handling adverb results
Cleaning safely results
* Transform the result with `transpose()`and returns a list of results and a list of errors.

##### compact()
* `compact()` removes the NULL from a list. Similar to `discard(is.null)`.

`possibly() `and `compact()`
* use otherwise = NULL and pipe into `compact()`.

##### match.arg()
match.arg() matches arg against a table of candidate values as specified by choices, where NULL means to take the first one.

So far, we've tried:
-   An error extractor, by combining `safely()` and `map(.x, "error")`.
-   A "non-null" extractor, by combining `safely()` and `discard(.x, is.null)`.
-   A 404 generator, by using `possibly(.x, otherwise = 404)`, which was turned into a function.

```R
url_tester <- function(url_list, type = c("result", "error")) {
 type <- match.arg(type)
 url_list %>%
 map(safe_read) %>%
 set_names(url_list) %>%
 transpose() %>%
 pluck(type) 
}
url_tester(urls, type = "error")
```

#### httr package
##### GET()
GET a url.

```R
url_tester <- function(url_list){
 url_list %>%
 map( possibly(GET, NULL) ) %>%
 set_names( url_list ) %>%
 compact() %>%
 map("status_code")
}
url_tester(urls)
```
## Better code with purrr
### Why cleaner code?
Because with unclean codes:
* It's harder to spot typos when there is alot of repetitions.
* It's harder to interpret what's going on in each line of code.

Write code so that when in the future you'll need to change one thing, you'll just have to do it once.

#### What is clean code?
Clean code is:
* Light
* Readable
* Interpretable
* Maintainable

##### compose()
Compose multiple functions. Create a new function from two or more functions. 

When you use `compose()`, the functions are passed from **right to left** — that is to say in the same order as the one you would use in a nested call in base R: the first function to be executed is the function on the right.

##### tidy()
Turn an object into a tidy tibble.

##### partial()
Partial apply a function, filling in some arguments.
