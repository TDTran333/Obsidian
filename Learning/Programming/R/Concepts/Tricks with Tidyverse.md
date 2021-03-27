---
tags: R
---
Link: [Youtube](https://www.youtube.com/watch?v=NDHSBUN_rVU)

##### 1. count()
count() lets you quickly count the unique values of one or more variables: 
* `df %>% count(a, b)` is roughly equivalent to `df %>% group_by(a, b) %>% summarise(n = n())`. 
* count() is paired with tally(), a lower-level helper that is equivalent to `df %>% summarise(n = n())`. 
* Supply wt to perform weighted counts, switching the summary from `n = n() to n = sum(wt)`.

##### 2. creating new variables in group_by() or count()
The name parameter provide the name of the new column in the output. If omitted, it will default to n. If there's already a column called n, it will error, and require you to specify the name.

Example: `df %>% count(decade = 10 * (year %/% 10))`

##### 3. add_count()
add_count() and add_tally() are equivalents to count() and tally() but use mutate() instead of summarise() so that they add a new column with group-wise counts.

##### 4. summarize() with a list column
summarise() creates a new data frame. It will have one (or more) rows for each combination of grouping variables; if there are no grouping variables, the output will have a single row summarising all observations in the input. It will contain one column for each grouping variable and one column for each of the summary statistics that you have specified.

Using a list, you can do statistic test or modeling for example.
`summarize(t_test = list(t.test(avg_score))) %>%`
`mutate(tidied = map(t_test, tidy)) %>%`
`unnest(tidied)`

See chapter 25 of R for data science

##### 5. fct_reorder() + geom_col() + coord_flip()
Reorder factor levels by sorting along another variable
geom_col() uses stat_identity(): it leaves the data as is.
Flip cartesian coordinates so that horizontal becomes vertical, and vertical, horizontal.

##### 6. fct_lump()
Lump together factor levels into "other".

##### 7. scale_x/y_log10
The log transformation can be used to make highly skewed distributions less skewed. This can be valuable both for making patterns in the data more interpretable and for helping to meet the assumptions of inferential statistics.

Alot of data are log-normally distributed.

##### 8. crossing()
crossing() is a wrapper around expand_grid() that de-duplicates and sorts its inputs.
Doesn't convert strings to factors and can be used to cross two tibbles together.

##### 9. separate()
Separate a character column into multiple columns with a regular expression or numeric locations.

##### 10. extract()
Extract a character column into multiple columns using regular expression groups.