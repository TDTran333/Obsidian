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

##### expand_limit()
Expand the plot limits, using data.

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


