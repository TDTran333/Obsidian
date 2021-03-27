---
aliases: Into to purrr
tags: R
---

# Foundations of Functional Programming with purrr

##  Simplifying Iteration and Lists With purrr
### The power of iteration
purrr allows us to simplify iteration, either with vectors or lists, without having to deal with for loops. Iteration is the process of doing the same process to multiple inputs. Being able to iterate is important to make your code efficient, and is powerful when working with lists. Iteration saves time, reduces lines of code, and prevent typos. purrr wraps a for loop into a single function, map().

map() takes two arguments. map(object, function), map(.x, .f).
* .x, object - can be a vector or a list
* .f, function - any function in R that takes the input offered by the object

##### seq_along()
`seq_along()` generates a sequence the same length of the argument passed, and in the context of a for loop is used to more easily generate the index to iterate over

##### map()
The map functions transform their input by applying a function to each element of a list or atomic vector and returning an object of the same length as the input. map() always returns a list.

### Subsetting lists
List indexing is one key place where lists differ from dataframes and vectors. 
Both named and unnamed lists can be subset using double square brackets `[[ ]]` list this: `listname[[ index ]]`
If a list is named, you can also use `$` for subsetting. The syntax `list$elementname` pulls out the named element from the list.

You can also subset within list elements using bracket notation like this: `ListName$ElementName[VectorNumber]`. If a list element is a dataframe, you can pull out a column like this: `ListName$ElementName$ColumnName` or `ListName[[1]][,1]`.

#### repurrrsive package
Examples of Recursive Lists and Nested or Split Data Frames

### The many flavors of map()
The second way to use map() is: `map(list, ~function(.x))`
To specify how the list is used in the function, use the argument `.x` to denote where the list element goes inside the function. When you want to use `.x` to show where the element goes in the function, you need to put a `~` in front of the function in the second argument of `map()`

##### map_lgl(), map_int(), map_dbl() and map_chr() 
return an atomic vector of the indicated type.
`map_chr()`: character vector
`map_lgl()`: logical vector \[TRUE or FALSE\]
`map_int()`: integer vector
`map_dbl()`: double vector

##  More complex iterations
### Working with unnamed lists
It is easy to determine if a list has names using `names()`. Understanding the named elements of a list can make working with the list elements easier because you can pull out the information you need by name, instead of searching for the correct numbered element. If you have an unnamed list, you can name each element with set_names(map_chr(list, name_vec)).

##### set_names()
Set names of a vector

A pipe `%>%` takes the output from the function that comes before it, and feeds it into the function that comes after the pipe as its first argument. You can also use pipes on the _inside_ of `map()` function to help you iterate a pipeline of tasks over a list of inputs.

### More map()
map() makes simulating multiple datasets simple.
We can also use map() to run the same model with different inputs, where each different input is one element from a list.

##### map_df(), map_dfc(), map_dfr()
Returns a data frame. map_dfr() and map_dfc() return a data frame created by row-binding and column-binding respectively. They require dplyr to be installed.

### map2() and pmap()
The `map()` function is great if you need to iterate over _one_ list, however, you will often need to iterate over two lists at the same time. This is where `map2()` comes in. While `map()` takes the list as the `.x` argument; `map2()` takes two lists as two arguments: `.x` and `.y`.

If we have 3 or more list, we use pmap(). To use `pmap()`, you first need to create a _master list_ of all the lists we want to iterate over. The master list is the input for `pmap()`. Instead of using `.x` or `.y`, use the list names _as_ the argument names.

##### map2()
Map over multiple inputs simultaneously. map2() and walk2() are specialised for the two argument case

##### pmap()
Note that a data frame is a very important special case, in which case pmap() and pwalk() apply the function .f to each row. 

## Troubleshooting lists with purrr
If you `map()` over a list, and one of the elements does not have the right data type, you will not get the output you expect. If you have a very large list, figuring out where things went wrong, and what exactly went wrong can be hard. That is where `safely()` comes in; it shows you both your results and where the errors occurred in your `map()` call. Piping into `transpose()` creates two lists, one of `result` and of `error`.

##### safely()
Wrapped function instead returns a list with components result and error. If an error occurred, error is an error object and result has a default value (otherwise). Else error is NULL.

##### transpose()
Transpose turns a list-of-lists "inside-out"; it turns a pair of lists into a list of pairs, or a list of pairs into pair of lists

Once you have figured out how to solve an issue with `safely()`, (e.g., output an `NA` in place of an error), swap out `safely()` with `possibly()`. `possibly()` will run through your code and implement your desired changes without printing out the error messages.

##### possibly()
Wrapped function uses a default value (otherwise) whenever an error occurs.

Printing out lists with `map()` shows a lot of bracketed text in the console, which can be useful for understanding their structure, but this information is usually _not_ important for communicating with your end users. If you need to print, using `walk()` prints out lists in a more compact and human-readable way, without all those brackets. `walk()` is also great for printing out plots without printing anything to the console.

##### walk()
The walk functions work similarly to the map functions, but you use them when you’re interested in applying a function that performs an action instead of producing data (e.g., `print()`).

## Problem solving with purrr
### Using purrr in your workflow
#### Setting Names
When working with a list, often the fist step is to check if a list has names with the names() function. If there is no names, we can set_names() combined with map_chr().

#### Asking questions from a list
Piping `map()` into `set_names()` and then `sort()` to answer questions.

### Solving complex problems
#### Nested lists
Sometimes the elements of a list are another list which means the variables names we are interested in are buried or nested. To extract data in a list that is inside another list, we will use nested `map() `functions. 
`map(list_of_lists, ~map(.x, ~.x\[\["element"]]))`

#### Summary stats
Pulling data from lists into dataframes to generate summary statistics. Outside of purrr, we would need to create an empty dataframe, extract the names, and then use a for loop and put that output into `summary()`. With purrr, we would use the `data_frame()` or `tibble()` function inside `map_df()`.

### Graphs in purrr
Go from a list to a graph. Each `ggplot()` graph requires a dataframe as input, so we cannot input a list. We can use `map_df()` to transform the data from a list, into the dataframe we need and pipe directly into the `ggplot()` code.

`` `[` `` can be used to subset a list of a lists inside the map_\*() function.
See [[R Accessors]].