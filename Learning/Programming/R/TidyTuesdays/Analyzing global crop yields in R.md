---
aliases: TidyTuesday - Global Crop Yields
tags: R
---
Links: [YouTube](https://www.youtube.com/watch?v=0uqAhIiK9Rc), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#global-crop-yields)

# TidyTuesday - Global Crop Yields

### Data 
Five datasets related to agricultural yields across crop types and by country

* key_crop_yields
* fertilizer
* tractors
* land_use
* arable_land 

### Libraries and functions
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


