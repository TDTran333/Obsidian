---
tags: wip, R, dataviz
---

# Interactive Data Visualization with plotly in R
## Introduction to plotly
### Static vs. Interactive graphics
Interactive graphics are great tools for exploring your data and communicating your findings. However, you should still keep data-viz best practices in mind.

#### library(plotly)
Create interactive web graphics from 'ggplot2' graphs and/or a custom interface to the (MIT-licensed) JavaScript library 'plotly.js' inspired by the grammar of graphics.

Plotly work in multiple formats:
* viewer windows
* R Markdown documents
* shiny apps

Competitors: rbokeh and highcharter

##### ggplotly()
This function converts a ggplot2::ggplot() object to a plotly object.

By default, `plotly` adds some very useful interactive tools: hover information including the values of the x and y-coordinates, the ability to pan and zoom, and the box and lasso selection tools.

### Univariate graphics
##### plot_ly()
This function maps R objects to plotly.js, an (MIT licensed) web-based interactive charting library. 

##### add_*() such as add_bars(), add_histogram(), add_markers, add_boxplots()
Add trace(s) to a plotly visualization.

From the Plotly website: “A trace is just the name we give a collection of data and the specifications of which we want that data plotted. Notice that a trace will also be an object itself, and these will be named according to how you want the data displayed on the plotting surface.”

#### Bar charts with plotly
```R
 wine %>%
	count(Type) %>%
	mutate(Type = fct_reordere(Type, n, .desc = TRUE)) %>%
	plot_ly(x = ~Type, y = ~n) %>%
	add_bars()
```

#### Histograms with plotly
```R
wine %>%
	plot_ly(x = ~Phenols) %>%
	add_histogram(nbinsx = 10) or add_histogram(xbins = list(start = 0.8, end = 4, size = 0.25))
```

### Bivariate graphics
#### Scatterplots with plotly
```R
winequality %>%
	plot_ly(x = ~residual_sugar, y = ~fixed_acidity) %>%
	add_markers()
```

#### Stacked bar charts with plotly
```R
winequality %>%
	count(type, quality_label) %>%
	plot_ly(x = ~type, y = ~n, color = ~quality_label) %>%
	add_bars() %>%
	layout(barmode = "stack")
```

##### Changing from counts to proportions
```R
winequality %>%
	group_by(type) %>%
	mutate(prop = n / sum(n)) %>%
	count(type, quality_label) %>%
	plot_ly(x = ~type, y = ~prop, color = ~quality_label) %>%
	add_bars() %>%
	layout(barmode = "stack")
```

#### Boxplots with plotly
```R
winequality %>%
	plot_ly(x = ~quality_label, y = ~alcohol) %>%
	add_boxplot()
```

## Styling and customizing your graphics
### Customize your traces
#### Changing color
```R
winequality %>%
	plot_ly(x = ~fixed_acidity) %>%
	add_histogram(color = I("red"))
```
`plotly` allows you to specify colors using other formats, including RGB, RGBA, HEX, HCL, HSL, and HSV.

##### I()
Change the class of an object to indicate that it should be treated ‘as is’.

#### Adjust opacity
```R
winequality %>%
	plot_ly(x = ~residual_sugar, y = ~fixed_acidity) %>%
	add_markers(marker = list(opacity = 0.2))
```

#### Change the plotting symbol
```R
winequality %>%
	plot_ly(x = ~residual_sugar, y = ~fixed_acidity) %>%
	add_markers(marker = list(symbol = "circle-open"))
```

#### Changing the size
The default marker size is 6 pixels in `plotly`.

#### Changing the width

### Thoughtful use of color
#### Mapping variables by color
#### Changing color palette
```R
	add_markers(color = "Dark2") or add_markers(colors = c("orange", "black", "skyblue"))
```

if you map a variable to the symbol, `plotly` automatically maps the variable to the color.

### Hover info
By default, the hover reveals the coordinate but lacks variable names.

#### Changing the default
```R
 wine %>%
	count(Type) %>%
	plot_ly(x = ~Type, y = ~n, hoverinfo = "y") %>%
	add_bars()
```
By default, hoverinfo = "all".

#### Custom hover text
```R
 wine %>%
	plot_ly(x = ~Flavanoids, y = ~Alcohol, hoverinfo = "text",
		   		text = ~paste("Flavanoids:", Flavanoids, "<br>", 
					  			 	  "Alcohol:", Alcohol)) %>%
	add_markers()
```
The tilde parameter, ~, is used to map columns to aesthetic parameters
It is also possible to add a `text` argument to the `plot_ly()` command without specifying `hoverinfo = "text"`.

### Customizing your layout
##### layout()
Modify the layout of a plotly visualization
* axes: type, labels, tick marks, transformations, etc.
* legend: position
* canvas: grid lines, background color
* size: height, width, margins

```R
	layout(xaxis = list(title = ..., type = "log", zeroline = FALSE),
		       yaxis = list(title = ..., type = "log", zeroline = FALSE, showgrid = FALSE),
		   	   title = ...)
```
Other types of axis include "linear", "date" and "category".

#### Customizing the canvas
```R
	layout(plot_bgcolor = toRGB("gray90"),
		   	   paper_bgcolor - toRGB("skyblue"))
```

## Advanced charts
### Layering traces



## Case Study