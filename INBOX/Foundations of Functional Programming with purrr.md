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


##  More complex iterations

## Troubleshooting lists with purrr

## Problem solving with purrr