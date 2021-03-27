---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=HwRrEIPiTyk), [List-Column](https://jennybc.github.io/purrr-tutorial/ls13_list-columns.html)

# List-columns in data.table
Because of its efficiency and speed, being able to use data.table to work with list-columns would be beneficial in many data contexts (e.g. to reduce memory usage in large data sets).

Comparing the behavior of the data.table approaches to the dplyr::group\_nest() function and tidyr::unnest().

### Why use list-columns?
* Can make data manipulations safer
* Memory efficient (fewer redundancies)
* Cognitively easier to understand complex data

### Why data.table?
* Concise syntax `dt[i, j, by]`
	* i = filter() or arrange()
	* j = mutate()
	* by = group_by()
* Fast speed
* Memory efficient

### The grammar
##### Nest
Making a list-column of data tables or vectors or visualizations
##### Unbest
Unnesting list-columns that has vectors in them into dataframes

### Example
`library(tidyverse)`
`library(data.table)`

Have to tell R that it is a data.table for it to works with the syntax above. (as.data.table())
We want to join two df but one of the df has list-columns that is related to the 2nd one
Create a df unnesting the variable of interest
Create another df with a nested variable called data with all the other data associated
Join them

The `:=` operator change the df in place and not make another copy
Empty square brackets force a print in data.table

### What about performance?
Memory and speed

