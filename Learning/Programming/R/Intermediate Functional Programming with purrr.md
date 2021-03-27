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

#### Building functions with compose() and negate()
There is no limits to how many function there is in `compose()`.
We can use `negate()` on mapper so that we can reduce the number of code we need to adjust if we want to change something.

##### negate()
Negate a predicate function.

#### HTTP Status Codes
| Code | Description        | Code | Description           |
| ---- | ------------------ | ---- | --------------------- |
| 200  | OK                 | 400  | Bad Request           |
| 201  | Created            | 401  | Unauthorized          |
| 202  | Accepted           | 403  | Forbidden             |
| 301  | Moved permanently  | 404  | Not Found             |
| 303  | See Other          | 410  | Gone                  |
| 304  | Not Modified       | 500  | Internal Server Error |
| 307  | Temporary Redirect | 503  | Server Unavailable    |

##### %in% operator
%in% is a more intuitive interface as a binary operator, which returns a logical vector indicating if there is a match or not for its left operand.

```R
`%not_in%` <- negate(`%in%`)
extract_status <- compose(status_code, GET)
strict_code <- function(url) {
  code <- extract_status(url)
  if (code %not_in% 200:203) {
    return(NA)
  }
  code
}
```

#### Prefilling functions
##### partial()
Partial apply a function, filling in some arguments.

#### Using partial() and compose()
Reminder on [[Web Scraping in R|rvest]] package.

```R
get_h2 <- partial(html_nodes, css = "h2")
get_content <- compose(html_text, get_h2, read_html)
res <- map(urls, get_content) %>% set_names(urls)
res

get_a <- partial(html_nodes, css = "a")
href <- partial(html_attr, name = "href")
get_links <- compose(href, get_a, read_html)
res <- map(urls, get_links) %>% set_names(urls)
res
```

### List columns
#### What is a list column?
A list column, also known as a nested dataframe, can have anything in one cell of a dataframe, instead of a scalar value. This behavior is specific to the tibble class, which is the tidyverse implementation of dataframes.

#### Why list columns?
You can write cleaner code with list-columns as everything stays in the same dataframe and we can combine the power of dplyr and the flexibility purrr.

This is useful is for example, we have a function that returns a non-predictable number of results. Or if we do modeling and the output contains all the related stats.

#### Unnesting nested data.frame
The idea when using a nested dataframe (i.e., dataframe with a list column) is to keep everything inside a dataframe so that the workflow stays tidy and get back to a standard dataframe stucture once you've performed your operations.

##### nest() and unnest()
Nesting creates a list-column of data frames; unnesting flattens it back out into regular columns. Nesting is implicitly a summarising operation: you get one row for each group defined by the non-nested columns. This is useful in conjunction with other summaries that work with whole datasets, most notably models.

```R
summary_lm <- compose(summary, lm)
iris %>%
  group_by(Species) %>%
  nest() %>%
  mutate(data = map(data, ~ summary_lm(Sepal.Length ~ Sepal.Width, data = .x)),
			  data = map(data, "r.squared")) %>%
  unnest()
```

## Case Study - Analysing Tweets
##### vec_depth()
The depth of a vector is basically how many levels that you can index into it.

Nested lists might seem strange to you if you have always worked with dataframes. But actually, it's a pretty standard data format when you are retrieving data from the web: most APIs return JSON (short for JavaScript Object Notation), which is read as a nested list by R. Why this format? Because not everything can be put into rows, columns, and cells. JSON is a format that allows having a variety of elements at several levels of depth. It's also lighter, and quicker to run on the web.

#### Discovering the dataset
```R
rt <- keep(rstudioconf, "is_retweet") %>%
  map("user_id") %>% 
  unique()

non_rt <- discard(rstudioconf, "is_retweet") %>%
  map("user_id") %>% 
  unique()

union(rt, non_rt) %>% length()
setdiff(rt, non_rt) %>% length()
```

##### union(), intersect(), setdiff(), setequal()
Performs set union, intersection, (asymmetric!) difference, equality and membership on two vectors.

#### Extracting information from the dataset
```R
mean_na_rm <- partial(mean, na.rm = TRUE)
round_one <- partial(round, digits = 1)
rounded_mean <- compose(round_one, mean_na_rm)

non_rt <- discard(rstudioconf, "is_retweet")
non_rt %>%
  map_dbl("favorite_count") %>%
  rounded_mean()
```
```R
flatten_to_vector <- compose(as_vector, compact, flatten)
extractor <- function(list, what = "mentions_screen_name"){
  map( list , what ) %>%
    flatten_to_vector()
}

six_most <- compose(tail, sort, table)
extractor(rstudioconf) %>% 
  six_most()
```

##### flatten()
These functions remove a level hierarchy from a list. They are similar to unlist(), but they only ever remove a single layer of hierarchy and they are type-stable, so you always know what the type of the output is.

#### Manipulating URLs
```R
urls_clean <- map(rstudioconf, "urls_url") %>%
  flatten()
compact_urls <- compact(urls_clean)

has_github <- as_mapper(~ str_detect(.x, "github"))
map_lgl( compact_urls, has_github ) %>%
  sum()
```
```R
str_prop_detected <- function(string, pattern) {
  string %>%
    str_detect(pattern) %>%
    mean()
} 

flatten_and_compact <- compose(compact, flatten)
rstudioconf %>%
  map("urls_url") %>%
  flatten_and_compact() %>% 
  str_prop_detected("github")
```

#### Identifying influencers
```R
mean_above <- as_mapper(~ .x > 3.3)
above <- partial(map_at, .at = "retweet_count", .f := mean_above )
below <- partial(map_at, .at = "retweet_count", .f := negate(mean_above) )
ab <- map(non_rt, above) %>% keep("retweet_count")
bl <- map(non_rt, below) %>% keep("retweet_count")
length(ab)
length(bl)
```
```R
max_rt <- map_dbl(non_rt, "retweet_count") %>% 
  max()
max_rt_calc <- partial(map_at, .at = "retweet_count", .f := ~ .x == max_rt )

res <- non_rt %>%
  map(max_rt_calc) %>% 
  keep("retweet_count") %>% 
  flatten()

res$screen_name
res$text
```
##### map_at()
map_at() takes a vector of names or positions .at to specify which elements of .x are transformed with .f.

We get the same list back, but with targeted modifications. You can either use the name of the element or a number, to refer to the position of the element.

##### quasi-quotation equals operator, [`:=`](https://www.rdocumentation.org/packages/rlang/topics/quasiquotation), (sometimes known as the "walrus operator").
`:=` works like `=`, but lets `partial()` know that the argument should be passed to `map_at()` rather than being kept for itself.

