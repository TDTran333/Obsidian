---
tags: wip, R
---
Link: [Vignette](https://dplyr.tidyverse.org/articles/programming.html)

# Programming with dplyr
Most dplyr verbs use **tidy evaluation** in some way. Tidy evaluation is a special type of non-standard evaluation used throughout the tidyverse. There are two basic forms found in dplyr:

* `arrange(), count(), filter(), group_by(), mutate(), and summarise()` use **data masking** so that you can use data variables as if they were variables in the environment (i.e. you write my_variable not df$myvariable).

* `across(), relocate(), rename(), select(), and pull()` use **tidy selection** so you can easily choose variables based on their position, name, or type (e.g. starts_with("x") or is.numeric).

## Data masking
Data masking makes data manipulation faster because it requires less typing. In most (but not all) base R functions you need to refer to variables with $, leading to code that repeats the name of the data frame many times

### Data- and env-variables
The key idea behind data masking is that it blurs the line between the two different meanings of the word “variable”:

* env-variables are “*programming*” variables that live in an environment. They are usually created with `<-`.

* data-variables are “statistical” variables that live in a data frame. They usually come from data files (e.g. .csv, .xls), or are created manipulating existing variables.

### Indirection
The main challenge of programming with functions that use data masking arises when you introduce some indirection, i.e. when you want to get the data-variable from an env-variable instead of directly typing the data-variable’s name. There are two main cases:

* When you have the data-variable in a function argument (i.e. an env-variable that holds a promise), you need to **embrace** the argument by surrounding it in doubled braces, like filter(df, {{ var }}).

```R
var_summary <- function(data, var) {
  data %>%
    summarise(n = n(), min = min({{ var }}), max = max({{ var }}))
}
```
* When you have an env-variable that is a character vector, you need to index into the .data pronoun with \[\[, like summarise(df, mean = mean(.data\[\[var]])).

```R
for (var in names(mtcars)) {
  mtcars %>% count(.data[[var]]) %>% print()
}
```

Note that .data is not a data frame; it’s a special construct, a pronoun, that allows you to access the current variables either directly, with .data$x or indirectly with .data\[\[var]]. Don’t expect other functions to work with it.

Another note: In R, arguments are lazily evaluated which means that until you attempt to use, they don’t hold a value, just a promise that describes how to compute the value. You can learn more at https://adv-r.hadley.nz/functions.html#lazy-evaluation

## Tidy selection
Data masking makes it easy to compute on values within a dataset. Tidy selection is a complementary tool that makes it easy to work with the columns of a dataset.

### The tidyselect DSL
Underneath all functions that use tidy selection is the tidyselect package. It provides a miniature domain specific language that makes it easy to select columns by name, position, or type. For example:

* `select(df, 1)` selects the first column; 
   `select(df, last_col())` selects the last column.
* `select(df, c(a, b, c))` selects columns a, b, and c.
* `select(df, starts_with("a"))` selects all columns whose name starts with “a”;
   `select(df, ends_with("z")) `selects all columns whose name ends with “z”.
* `select(df, is.numeric) `selects all numeric columns.

You can see more details in [?dplyr_tidy_select](https://dplyr.tidyverse.org/reference/dplyr_tidy_select.html).

### Indirection
As with data masking, tidy selection makes a common task easier at the cost of making a less common task harder. When you want to use tidy select indirectly with the column specification stored in an intermediate variable, you’ll need to learn some new tools. Again, there are two forms of indirection:

* When you have the data-variable in an env-variable that is a function argument, you use the same technique as data masking: you embrace the argument by surrounding it in doubled braces.

```R
summarise_mean <- function(data, vars) {
  data %>% summarise(n = n(), across({{ vars }}, mean))
}
```

* When you have an env-variable that is a character vector, you need to use all_of() or any_of() depending on whether you want the function to error if a variable is not found.

``` R
vars <- c("mpg", "vs")
mtcars %>% select(all_of(vars))
mtcars %>% select(!all_of(vars))
```

## How tos
The following examples solve a grab bag of common problems. We show you the minimum amount of code so that you can get the basic idea; most real problems will require more code or combining multiple techniques.

### User-supplied data
If you check the documentation, you’ll see that .data never uses data masking or tidy select. That means you don’t need to do anything special in your function:

### Eliminating R CMD check NOTEs
If you’re writing a package and you have a function that uses data-variables.
You’ll get an R CMD CHECK NOTE.
You can eliminate this by using .data$var and importing .data from its source in the rlang package (the underlying package that implements tidy evaluation).

### One or more user-supplied expressions
If you want the user to supply an expression that’s passed onto an argument which uses data masking or tidy select, embrace the argument.

If you want to use the names of variables in the output, you can use `glue syntax` in conjunction with `:=`.

```R
my_summarise <- function(data, mean_var, sd_var) {
  data %>% 
    summarise(
      "mean_{{mean_var}}" := mean({{ mean_var }}), 
      "sd_{{sd_var}}" := mean({{ sd_var }})
    )
}
```

### Any number of user-supplied expressions
If you want to take an arbitrary number of user supplied expressions, use `...`. This is most often useful when you want to give the user full control over a single part of the pipeline, like a `group_by() or a mutate()`.

```R
my_summarise <- function(.data, ...) {
  .data %>%
    group_by(...) %>%
    summarise(mass = mean(mass, na.rm = TRUE), height = mean(height, na.rm = TRUE))
}
```

When you use ... in this way, make sure that any other arguments start with . to reduce the chances of argument clashes; see https://design.tidyverse.org/dots-prefix.html for more details.

### Transforming user-supplied variables
If you want the user to provide a set of data-variables that are then transformed, use `across()`.

```R
my_summarise <- function(data, group_var, summarise_var) {
  data %>%
    group_by(across({{ group_var }})) %>% 
    summarise(across({{ summarise_var }}, mean))
}
```

Use the .names argument to across() to control the names of the output.

### Loop over multiple variables
If you have a character vector of variable names, and want to operate on them with a for loop, index into the special .data pronoun.

``` R
for (var in names(mtcars)) {
  mtcars %>% count(.data[[var]]) %>% print()
}
```

This same technique works with for loop alternatives like the base R apply() family and the purrr map() family.

``` R
mtcars %>% 
  names() %>% 
  purrr::map(~ count(mtcars, .data[[.x]]))
}
```

### Use a variable from an Shiny input
Many Shiny input controls return character vectors, so you can use the same approach as above: .data\[\[input$var]].
