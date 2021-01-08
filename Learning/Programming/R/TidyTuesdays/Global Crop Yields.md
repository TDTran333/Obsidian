---
aliases: TidyTuesday - Global Crop Yields
tags: R
---
Links: [YouTube](https://www.youtube.com/watch?v=0uqAhIiK9Rc), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#global-crop-yields), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-09-01/readme.md)

# TidyTuesday - Global Crop Yields
## Topic: Interactive Shiny dashboard
### Data 
Five datasets related to agricultural yields across crop types and by country
* key_crop_yields
* fertilizer
* tractors
* land_use
* arable_land 

###  Annotations
| Time  | Description                                                                                                                                      |
| ----- |:------------------------------------------------------------------------------------------------------------------------------------------------ |
| 03:35 | Using rename to shorten column name                                                                                                              |
| 06:40 | Using rename_all with str_remove and regex to remove characters in column name                                                                   |
| 07:40 | Using pivot_longer to change data from wide to long                                                                                              |
| 08:25 | Create a faceted geom_line chart                                                                                                                 |
| 09:40 | Using fct_reorder to reorder facet panels in ascending order                                                                                     |
| 11:50 | Create an interactive Shiny dashboard                                                                                                            |
| 33:20 | Create a faceted geom_line chart with add_count and filter(n = max(x)) to subset the data for crops that have observations in every year         |
| 36:50 | Create a faceted geom_point chart showing the crop yields at start and end over a 50 year period (1968 start date and 2018 end date)             |
| 45:00 | Create a geom_boxplot to visualize the distribution of yield ratios for the different crops to see how efficiency has increased across countries |
| 46:00 | Create a geom_col chart to visualize the median yield ratio for each crop                                                                        |
| 47:50 | Create a geom_point chart to visualize efficiency imporvement for each country for a specific crop (yield start / yield ratio)                   |
| 50:25 | Using the countrycode package to color geom_point chart by continent names                                                                       |
| 56:50 | Summary of screencast                                                                                                                            |

### Libraries and Functions
##### rename()
rename() changes the names of individual variables using new_name = old_name syntax.

##### rename_all()
rename_all() have been superseded by rename_with()

##### rename_with()
rename_with() renames columns using a function.

##### str_remove()
Remove matched patterns in a string.

##### str_to_title()
Convert first letter of every word to uppercase.

##### str_replace_all()
Replace matched patterns in a string.

##### pull()
Extract a single column.

##### write_rds()
Consistent wrapper around saveRDS() and readRDS(). write_rds() does not compress by default as space is generally cheaper than time.

##### expand_limits()
Expand the plot limits, using data.

##### ungroup()
ungroup() removes grouping.

Good practice if you have more than two variables in group_by() to ungroup() at the end.

##### geom_text()
geom_text() adds text to the plot. 

###### parameter: check_overlap
If TRUE, text that overlaps previous text in the same layer will not be plotted. 

###### parameters: hjust, vjust
Horizontal and vertical justification have the same parameterisation, either a string (“top”, “middle”, “bottom”, “left”, “center”, “right”) or a number between 0 and 1:

top = 1, middle = 0.5, bottom = 0
left = 0, center = 0.5, right = 1

**Note: The real values are reversed from what the vignette says**

##### geom_abline(), geom_hline(), geom_vline()
Reference lines: horizontal, vertical, and diagonal

#### ggrepel()
This package contains extra geoms for ggplot2.

##### geom_text_repel()
geom_text_repel adds text directly to the plot. geom_label_repel draws a rectangle underneath the text, making it easier to read. The text labels repel away from each other and away from the data points.

###### parameter: force
Force of repulsion between overlapping text labels. Defaults to 1.

### Making shiny dashboard
##### inputPanel()
A flowLayout() with a grey border and light grey background, suitable for wrapping inputs.

##### selectinput() and selectizeinput()
Create a select list that can be used to choose a single or multiple items from a list of values.

The JavaScript library [selectize.js](https://selectize.github.io/selectize.js/) provides a much more flexible interface compared to the basic select input. It allows you to type and search in the options, use placeholders, control the number of options/items to show/select, and so on. 

See https://shiny.rstudio.com/articles/selectize.html for more info.

##### renderPlot()
Renders a reactive plot that is suitable for assigning to an output slot

##### renderPlotly()
Output and render functions for using plotly within Shiny applications and interactive Rmd documents.

##### checkboxInput()
Create a checkbox that can be used to specify logical values.

##### radioButtons()
Create a set of radio buttons used to select an item from a list.


