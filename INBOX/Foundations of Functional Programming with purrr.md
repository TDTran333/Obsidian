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
Returns a data frame.

### map2() and pmap()
If we have two list, we use map2(). If we have 3 or more list, we use pmap(). For pmap(), we need to create a list of all the lists we want to use, as our input. The second argument of pmap() is a custom function with the names of the elements from the input list as arguments instead of having to use .x and .y.

##### map2()
Map over multiple inputs simultaneously. map2() and walk2() are specialised for the two argument case

##### pmap()
Note that a data frame is a very important special case, in which case pmap() and pwalk() apply the function .f to each row. 

##### walk()
The walk functions work similarly to the map functions, but you use them when you’re interested in applying a function that performs an action instead of producing data (e.g., `print()`).

## Troubleshooting lists with purrr

## Problem solving with purrr