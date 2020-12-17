---
aliases: 
tags: status:wip, R
---
source: [datacamp](https://www.datacamp.com/)
author: Jeroen Boeye - Machine Learning Engineer @ Faktion

--- 
# Resharping Data with tidyr
### Tidy data
Tidy data is a standard way of mapping the meaning of a dataset to its structure. A dataset is messy or tidy depending on how rows, columns and tables are matched up with observations, variables and types. In tidy data: Each variable forms a column. Each observation forms a row.

##### Concepts
* Multiple variables per column
	* Use seperate functions
* Missing Values
	* Use imputation functions

#### Functions
##### separate()
Separate a character column into multiple columns with a regular expression or numeric locations. `convert = TRUE` option cause the value column to be converted from string to integer. 

##### separate_rows()
Separate a collapsed column into multiple rows.

##### unite()
Unite multiple columns into one by pasting strings together.

##### rename()
rename() changes the names of individual variables using new_name = old_name syntax.

##### replace_na()
Replace NAs with specified values.

##### fill()
Fill in missing values with previous or next value.

##### drop_na()
Drop rows containing missing values.

### From wide to long and back 
##### Concepts
* Deriving variables from column headers
* Deriving variables from complex column headers
* From long to wide data
* Transposing a data frame
	* Step 1: pivot_longer()
	* step 2: pivot_wider()

##### pivot_longer()
pivot_longer() "lengthens" data, increasing the number of rows and decreasing the number of columns. 

###### parameter: names_prefix	
A regular expression used to remove matching text from the start of each variable name.

###### parameters: names_transform, values_transform	
A list of column name-function pairs. Use these arguments if you need to change the type of specific columns. For example, names_transform = list(week = as.integer) would convert a character week variable to an integer.

###### ".value"
Use ".value" in the the names_to argument to re-use the part of the column headers.

###### Example
```R
bird_df %>%
  # Pivot the data to create a 2 column data frame
  pivot_longer(
    starts_with("vote_"),
    names_to = "rank",
    names_prefix = "vote_",
    names_transform = list(rank = as.integer),
    values_to = "species",
    values_drop_na = TRUE
  )
```

##### pivot_wider()
pivot_wider() "widens" data, increasing the number of columns and decreasing the number of rows. The inverse transformation is pivot_longer().

##### uncount()
Performs the opposite operation to dplyr::count(), duplicating rows according to a weighting variable (or expression).

##### scale_x_discrete()
scale_x_discrete() and scale_y_discrete() are used to set the values for discrete x and y scale aesthetics.

##### starts_with()
Select variables that match a pattern.

### Expanding data 
##### Concepts
* Creating unique combinations of vectors with expand_grid()
* Find values missing from dataframe with expand_grid() + anti_join()
* Completing data with all value combinations

##### expand_grid()
Create a tibble from all combinations of inputs.

##### anti_join()
anti_join() return all rows from x without a match in y. Find missing values from y.

##### complete()
Complete a data frame with missing combinations of data.

##### full_seq()
This is useful if you want to fill in missing values that should have been observed but weren't.

### Rectangling data 