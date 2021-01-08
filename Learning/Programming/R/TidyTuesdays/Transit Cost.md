---
aliases: TidyTuesday - Transit Cost
tags: R 
---
Links: [YouTube](https://www.youtube.com/watch?v=8jNQzce13SE), Annotations, [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2021/2021-01-05/readme.md)
# Tidy Tuesday : Transit Cost
## Topics: 
### Data
Database that spans more than 50 countries and totals more than 11,000 km of urban rail built since the late 1990s.

### Annotations



### Libraries and Functions
##### geom_errorbarh()
Horizontal error bars.

Error bars are graphical representations of the variability of data and used on graphs to indicate the error or uncertainty in a reported measurement.

##### parse_number()
This drops any non-numeric characters before or after the first number.

##### fct_reorder()
Reorder factor levels by sorting along another variable

It can be thrown off if there is NA's in the sorting variable.

##### add_count()
add_count() use mutate() instead of summarise() so that they add a new column with group-wise counts.

##### glue()
Format and interpolate a string

##### expand_limits()
Expand the plot limits, using data.

##### (year %/% 5) * 5
Group years in group of 5.

##### geom_jitter()
The jitter geom is a convenient shortcut for geom_point(position = "jitter"). It adds a small amount of random variation to the location of each point, and is a useful way of handling overplotting caused by discreteness in smaller datasets.

##### sym()
These functions take strings as input and turn them into symbols.

##### fct_infreq()
Reorder factor levels by first appearance, frequency, or numeric order
fct_infreq(): by number of observations with each level (largest first)