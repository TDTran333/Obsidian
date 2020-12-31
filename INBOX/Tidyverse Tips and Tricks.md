---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=ZM04jn95YP0)

# Tidyverse Tips and Tricks

### Create new columns in a count or group_by
Instead of using mutate() first

### Sample and randomly shuffle data with slice_sample()
##### slice_sample()


Create a date column specifying year, month, and day
Parse numbers with parse_number()
Select columns with starts_with, ends_with, etc.
case_when to create or change a column when conditions are met
str_replace_all to find and replace multiple options at once
Transmute to create or change columns and keep only those columns
Use pipes everywhere including inside mutates
Filter groups without making a new column
Split a string into columns based on a regular expression
semi_join to pick only rows from the first table which are matched in the second table
anti_join to pick only rows from the first table which are NOT matched in the second table
fct_reorder to sort bar charts
coord_flip to display counts more beautifully
fct_lump to lump some factor levels into "Other"
Generate all combinations using crossing
Create functions that take column names with double curly braces