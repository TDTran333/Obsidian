---
aliases: tidyr
tags: R
---
Link: [Website](https://tidyr.tidyverse.org/reference/index.html)

# Reference
### Pivoting
Pivoting changes the representation of a rectangular dataset, without changing the data inside of it. See vignette("pivot") for more details and examples.

| function       | definition                                      |
| :------------- | :---------------------------------------------- |
| pivot_longer() | Pivot data from wide to long                    |
| pivot_wider()  | Pivot data from long to wide                    |
| spread()       | Spread a key-value pair across multiple columns |
| gather()       | Gather columns into key-value pairs             |

### Rectangling
Rectangling turns deeply nested lists into tidy tibbles. See vignette("rectangle") for more details and examples.

| function        | definition                                 |
|:--------------- |:------------------------------------------ |
| hoist()         | Rectangle a nested list into a tidy tibble |
| unnest_longer() | "                                          |
| unnest_wider()  | "                                          |
| unnest_auto()   | "                                          |

  ### Nesting
Nesting uses alternative representation of grouped data where a group becomes a single row containing a nested data frame. See vignette("nest") for more details and examples.

| function | definition |
|:-------- |:---------- |
| nest()   | -          |
| unnest() | -          |

### Character vectors
Multiple variables are sometimes pasted together into a single column, and these tools help you separate back out into individual columns.

| function        | definition                                                                                       |
|:--------------- |:------------------------------------------------------------------------------------------------ |
| extract()       | Extract a character column into multiple columns using regular expression groups                 |
| separate()      | Separate a character column into multiple columns with a regular expression or numeric locations |
| separate_rows() | Separate a collapsed column into multiple rows                                                   |
| unite()         | Unite multiple columns into one by pasting strings together                                      |
	
### Missing values
Tools for converting between implicit (absent rows) and explicit (NA) missing values, and for handling explicit NAs.

| function      | definition                                                       |
|:------------- |:---------------------------------------------------------------- |
| complete()    | Complete a data frame with missing combinations of data          |
| drop_na()     | Drop rows containing missing values                              |
| expand()      | Expand data frame to include all possible combinations of values |
| crossing()    | "                                                                |
| nesting()     | "                                                                |
| expand_grid() | Create a tibble from all combinations of inputs                  |
| fill()        | Fill in missing values with previous or next value               |
| full_seq()    | Create the full sequence of values in a vector                   |
| replace_na()  | Replace NAs with specified values                                |

### Miscellanea
| function        | definition                  |
|:--------------- |:--------------------------- |
| chop() unchop() | Chop and unchop             |
| pack() unpack() | Pack and unpack             |
| uncount()       | "Uncount" a data frame Data |

 




	

