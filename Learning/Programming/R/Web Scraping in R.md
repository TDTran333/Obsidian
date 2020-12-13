---
aliases: Web Scrapping
tags: status:complete, R
---
source: [datacamp](https://www.datacamp.com/)
author: Timo Grossenbacher - Project Lead Automated Journalism at Tamedia
related: [[library(rvest) + SelectorGadget|library(rvest) example]]

----
# Web Scraping in R
### Introduction to HTML and Web Scraping
* If you see something, you can scrape it
* Hypertext Markup Language (HTML)
* HTML is organized hierachically
* HTML tags can have attributes
* Indentation is not necessary to make HTML work but adds to its readability

| tag      | description          |
|:-------- |:-------------------- |
| \<a>     | attribute            |
| \<p>     | paragraph            |
| \<ol>    | ordered list         |
| \<ul>    | unordered list       |
| \<td>    | table data cell      |
| \<tr>    | table row            |
| \<th>    | table header cell    |
| \<body>  | document body        |
| \<table> | table                |
| \<head>  | metadata             |
| \<div>   | document section     |
| \<span>  | mark up part of text |
| \<em>    | emphasized text      |


##### library(rvest)
rvest helps you scrape information from web pages. It is designed to work with magrittr to make it easy to express common web scraping tasks, inspired by libraries like beautiful soup.

| function        | Description                                                                     |
|:--------------- |:------------------------------------------------------------------------------- |
| read_html()     | Read in the content from a .html file                                           |
| xml_structure() | Show the structure of an html/xml document without displaying any of the values |
| html_children() | Extract children from html                                                      |
| html_text()     | Extract attributes, text and tag name from html                                 |
| html_node()     | Select node from an HTML document                                               |
| html_nodes()    | Select nodes from an HTML document                                              |
| html_attr()     | Select attribute from an HTML document                                          |
| html_attrs()    | Select attributes from an HTML document                                         |
| html_table()    | Parse an html table into a data frame                                           |

### Navigation and Selection with CSS 
* Cascading Style Sheets (CSS)
* [CSS reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
* CSS type selectors matches elements by node name
* CSS classes and IDs
	* class selector matches elements based on the contents of their class attribute
		* use \. before the name
	* ID selector matches an element based on the value of the element’s id attribute
		* use \# before the name
		* IDs are unique
* Pseudo classes
	*  :first-child
	*  :nth-child()
	*  :last-child
* The power of CSS selectors often lies in their ability to be combined

| Selector type       | HTML                        | CSS selector  |
| :------------------ | :-------------------------- | :------------ |
| Type                | \<p>...\</p>                | p             |
| Multiple types      | \<p>...\</p><div>...\</div> | p, div        |
| Class               | \<p class = 'x'>...\</p>    | .x            |
| Multiple classes    | \<p class = 'x y'>...\</p>  | .x.y          |
| Type + Class        | \<p class = 'x'>...\</p>    | p.x           |
| ID                  | \<p id = 'x'>...\</p>       | \#x           |
| Type + Pseudo-class | \<p>...\</p>\<p>...\</p>    | p:first-child |

* CSS combinators
	* "space": Descendant combinator
	* \>: Child combinator
	* +: Adjacent sibling combinator
	* ~: General sibling combinator

### Advanced Selection with XPATH 
* XML Path Language
* Syntax: axes, steps, and predicates
	* Axes: / or // (child or general descendant)
	* Steps: HTML types such as span and a
	* Predicates: [...]
		* Positions() function and operators 
		* Count() function
* XPATH text() function
* (..) parent selector

### Scraping Best Practices 
* Hypertext Transfer Protocol (HTTP)
* HTTP request
![[HTTP Request.png]]
* Request methods: GET and POST
	* GET : Fetch resource without submitting data
		* read_html() actually issues an HTTP GET request if provided with a URL
	* POST: Send data to server
* Custom user agents
	*  GET(..., user_agent()) or set_config(add_headers(`User-Agent` = ...))
* Throttling requests
	* purrr::slowly(), purrr::rate_delay()

##### library(httr)
The aim of httr is to provide a wrapper for the curl package, customised to the demands of modern web APIs.

##### library(curl)
A Modern and Flexible Web Client for R
The curl() and curl_download() functions provide highly configurable drop-in replacements for base url() and download.file() with better performance, support for encryption (https, ftps), gzip compression, authentication, and other 'libcurl' goodies.

| function      | Description                                 |
|:------------- |:------------------------------------------- |
| http_status() | Give information on the status of a request |
| content()     | Extract content from a request              |
 