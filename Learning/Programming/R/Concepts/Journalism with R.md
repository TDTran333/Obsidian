---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=vgYS-F8opgE)

# Journalism with R

Presenter from the Associated Press, not-for-profit cooperative news agency

### What Journalist do?
* Breaking news, investigative reporting
* Local, state, national, international
* Collaborate within and outside organization
* Text copy, graphics, interactive experience

### In term of Data Analysis
#### Loading in Data
* Using dbplyr for large data sets (hundred of millions of data values)
	*  Data so large that you need it hosted on a server and connect to it
	*  library(DBI), library(RPostgreSQL), library(dbplyr)
*  Using Google Forms & googlesheets4
	*  Using surveys to create data, "human-powered [[MapReduce]]"
*  Using httr for [[API]]s

#### Templated Graphics
* Existing newsroom style guide
	* Specific color palette and typeface 
	* theme packages with ggplot2 (theme_ap())
* Existing publishing workflows
	* Export graphics as [[Vector Graphics]]

#### Reporting the Findings
##### R Markdown is a crucial tool
* Everyone is in a hurry
* Multiple formats, mobile-friendly
* Popular features:
	* Data Tables with filters
	* leaflet for maps

#### Future Directions
* Templated interactives graphics
	* plotly, rbokeh, ggplot to d3 conversion
* Automation
	* Recurring data
	* Data validation
* Work with Python
* Member distributions

### Q&A
How to export plots as vector graphics?
ggsave with the file ending as .svg
caveat, artists dont like svg that R spits out

How to get involved doing data analysis for journalism?
State open data communities, alot of data sources waiting for people to find stories in them

How to convince management to invest in stuff like this that have high upfront cost?
Building good partnerships within the company and show the data angle value to the story

How do you know the data is right? Data validation
Soft process, be constantly critical, follow up with sources, verify.

Peer review of data analysis?
Set of principles, second set of eyes,  nothing's get out without multiple people's input on it, etc. Confirm with the experts if it is a valid use of the data.


