---
aliases: 
tags: status:wip, R
---

# Resharping Data with tidyr
### Tidy data
Tidy data is a standard way of mapping the meaning of a dataset to its structure. A dataset is messy or tidy depending on how rows, columns and tables are matched up with observations, variables and types. In tidy data: Each variable forms a column. Each observation forms a row.

#### Concepts
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
#### Concepts
* Deriving variables from column headers
* Deriving variables from complex column headers
* From long to wide data
* Transposing a data frame
	* Step 1: pivot_longer()
	* step 2: pivot_wider()

#### Functions
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
#### Concepts
* Creating unique combinations of vectors with expand_grid()
* Find values missing from dataframe with expand_grid() + anti_join()
* Completing data with all value combinations with complete and full_seq()
* Advanced completions
	* Nesting connected variables with nesting() inside complete()
	* Counting simultaneous events by the sequence of
		* pivot_longer() , complete(date = full_seq()), group_by(), then count()
	* Timestamp completions for time series

#### Functions
##### expand_grid()
Create a tibble from all combinations of inputs.

##### anti_join()
anti_join() return all rows from x without a match in y. Find missing values from y.

##### complete()
Complete a data frame with missing combinations of data.

##### full_seq()
This is useful if you want to fill in missing values that should have been observed but weren't.

##### seq()
Generate regular sequences. seq is a standard generic with a default method.

##### nesting()
nesting() is a helper that only finds combinations already present in the data. It tells complete() to consider it as a single variable.

##### geom_rect()
Generate a rectange in the plot.

###### Example
```R
df %>%
ggplot(aes(date, total_bombs, color = country)) +
  # These two lines will mark the Cuban Missile Crisis 
  geom_rect(xmin = as.Date("1962-10-16"), xmax = as.Date("1962-10-29"), ymin = -Inf, ymax = Inf, color = NA)+ 
  geom_text(x = as.Date("1962-10-22"), y = 15, label = "Cuban Missile Crisis", angle = 90, color = "white")+
  geom_line()
```

### Rectangling data 
#### Concepts
* Non-rectangular data like JSON or XML
* Unnnesting lists to columns and rows with unnest_wider() and unnest_longer()
	* These are the two situations where it is clear which unnesting function to try: named lists of fixed length = unnest_wider(), unnamed lists of varying length = unnest_longer(). There are other situations, like named lists with varying number of elements, where some trial and error will be necessary.
* Selecting nested variables using hoist()
* Nesting data for modeling with broom + purrr + dplyr + tidyr
	* The tidyr nest() function will nest a subset of a data frame based on some grouping variable. The result is a list column, data that has tibbles inside. 
	* map() function from the purrr package to apply a function to each tibble individually. 
	* Using purrr's map() function once more, we can apply broom's glance() or tidy() function on this fitted model.
	* unnest our model results using tidyr's unnest() function on the glanced column. 
	* We get a tidy overview of the model metrics. 

##### unnest_wider()
unnest_wider() turns each element of a list-column into a column.

##### unnest_longer()
unnest_longer() turns each element of a list-column into a row.

##### hoist()
hoist() allows you to selectively pull components of a list-column out in to their own top-level columns.

