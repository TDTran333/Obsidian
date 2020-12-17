---
aliases: R Markdown
tags: R
---
source: [datacamp](https://www.datacamp.com/)
author: Amy Peterson - Curriculum Manager at DataCamp
related: [[library(rvest) + SelectorGadget Vignettes|library(rvest) example]]

----
# Reporting with R Markdown
### Getting Started with R Markdown
* Knitting R Markdown File
* Adding code chunks
* Adding and formatting text (with markdown syntax)
	* Header with hashes
	* In line code with \` \`
	* Link with \[]()
	* Embedded image with \!\[]()
* The YAML header
```R
---
	title:
	author: 
	date: "`r Sys.Date()``"
	output: html_document
---
```
* Formatting the date
	* Sys.time(). Ex: "`format(Sys.time(), '%d %B %Y')`"
	
### Adding Analyses and Visualizations 
* Naming code chunks
* Referencing code results : 'r object_name'
* Adding plots
	* Figure dimensions: fig.width, fig.height, fig.dim
	* Output dimensions: out.width, out.height
	*  Figure alignment: fig.align: 'left', 'right', 'center' 
	*  Adding captions: fig.cap
*  Local vs. global options: knitr::opts_chunk()

### Improving the Report 
* Bulleted and numbered lists
* Adding a table
	* `knitr::kable(data, col.names = c(), align = 'lcr', caption = "")`
* Code chunk options
	* include
	* echo
	* eval
	* collapse
* Warnings, messages, and errors

### Customizing the Report 
* Adding a table of contents
	* Default depth is 3 for HTML documents and 2 for PDF documents. 
```R
---
	title:
	output: html_document
		toc: true
		toc_depth: 3
		number_sections: TRUE
		toc_float:
			collapsed:
			smooth_scroll:
---
```

* Creating a report with a parameter or multiple parameters
```r
---
	title:
	output: html_document
		toc: true
		toc_float: true
	params:
		var1: var1_name
		var2: var2_name
---
```

* Customizing the report style using CSS
	* TOC, title, author and date, headers, body, background, etc.

```R
<style>
#TOC {
  color: #708090;
  font-family: Calibri;
  font-size: 16px;
  border-color: #708090;
}
h1.title {
  color: #F08080;
  background-color: #F5F5F5;
  opacity: 0.6;
  font-family: Calibri;
  font-size: 20px;
}
h4.author {
  color: #708090;
  font-family: Calibri;
  background-color: #F5F5F5;
}
h4.date {
  color: #708090;
  font-family: Calibri;
  background-color: #F5F5F5;
}
#header{
  color: #F08080;
  font-family: Calibri;
  font-size: 20px;
  background-color: #F5F5F5;
  opacity: 0.6;
}
body {
  color: #708090;
  font-family: Calibri;
  background-color: #F5F5F5;
}
pre {
  color: #708090;
  background-color: #F8F8FF;
}
</style>
```
* Referencing the CSS file

```R
---
title: "Investment Report for Projects in `r params$country`"
output: 
  html_document:
    css: styles.css
    toc: true
    toc_float: true
date: "`r format(Sys.time(), '%d %B %Y')`"
params:
  country: Brazil
  year_start: 2017-07-01
  year_end: 2018-06-30
  fy: 2018
---
```