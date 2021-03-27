---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=ZM04jn95YP0)

# Tidyverse Tips and Tricks

### Create new columns in a count or group_by
Instead of using mutate() first

### Sample and randomly shuffle data with slice_sample()
##### slice_sample()
Randomly selects rows.

### Create a date column specifying year, month, and day
With lubridate. 

##### make_date()
Efficient creation of date-times from numeric representations.

### Parse numbers with parse_number()
##### parse_number()
This drops any non-numeric characters before or after the first number.

### Select columns with starts_with, ends_with, contains etc.
##### starts_with()
Select variables that match a pattern. Starts with a prefix.
 
##### ends_with()
Select variables that match a pattern. Ends with a suffix.

##### contains()
Select variables that match a pattern. Contains a literal string.

##### matches()
Select variables that match a pattern. Matches a regular expression.

### case_when to create or change a column when conditions are met
##### case_when()
This function allows you to vectorise multiple if_else() statements. It is an R equivalent of the SQL CASE WHEN statement. If no cases match, NA is returned.

### str_replace_all to find and replace multiple options at once
##### str_replace_all()
Replace matched patterns in a string.

### Transmute to create or change columns and keep only those columns
##### transmute()
transmute() adds new variables and drops existing ones. New variables overwrite existing variables of the same name. Variables can be removed by setting their value to NULL.

### Use pipes everywhere including inside mutates

### Filter groups without making a new column

### Split a string into columns based on a regular expression
##### extract()
Extract a character column into multiple columns using regular expression groups.

### semi_join to pick only rows from the first table which are matched in the second table

### anti_join to pick only rows from the first table which are NOT matched in the second table

### fct_reorder to sort bar charts

### coord_flip to display counts more beautifully

### fct_lump to lump some factor levels into "Other"

### Generate all combinations using crossing

### Create functions that take column names with double curly braces
##### across()
Apply a function (or a set of functions) to a set of columns.
`.names = "{.col}_{.fn}"`