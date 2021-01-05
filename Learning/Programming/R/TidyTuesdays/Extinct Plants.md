---
aliases: TidyTuesday - Extinct Plants
tags: R 
---
Links: [YouTube ](https://www.youtube.com/watch?v=f7Rc1bvMgZY), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#plants-in-danger), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-08-18/readme.md)

# Tidy Tuesday : Extinct plants
## Topics: Data manipulation, Web scraping using `rvest` package
### Data
In total, 500 plant species are considered extinct as of 2020.
`plants.csv`
`threats.csv`
`actions.csv`

### Annotations
| Time  | Description                                                                                                                                                              |
| ----- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 2:00  | Getting an overview of categorical data                                                                                                                                  |
| 5:00  | Using fct_relevel to reorder the "Before 1900" level to the first location leaving the other levels in their existing order                                              |
| 8:05  | Using n and sum in fct_reorder to reorder factor levels when there are multiple categories in count                                                                      |
| 12:00 | Using reorder_within and scale_y_reordered such that the values are ordered within each facet                                                                            |
| 14:55 | Using axis.text.x to rotate overlapping labels                                                                                                                           |
| 19:05 | Using filter and fct_lump to lump all levels except for the 8 most frequest facet panels                                                                                 |
| 26:55 | Using separate to separate the character column binomial_name into multiple columns (genus and species)                                                                  |
| 28:20 | Using fct_lump within count to lump all levels except for the 8 most frequent genus                                                                                      |
| 45:30 | Using rvest and SelectorGadget to web scrape list of species                                                                                                             |
| 49:35 | Using str_trim to remove whitespace from character string                                                                                                                |
| 50:00 | Using separate to separate character string into genus, species, and rest/citation columns and using extra = "merge" to merge extra pieces into the rest/citation column |
| 51:00 | Using rvest and SelectorGadget to web scrape image links                                                                                                                 |
| 57:50 | Summary of screencast                                                                                                                                                    |

### Libraries and functions
##### fct_lump()
Lump together factor levels into "other".

###### parameter: w	
An optional numeric vector giving weights for frequency of each value (not level) in f.

##### element_text()
In conjunction with the theme system, the element_ functions specify the display of how non-data components of the plot are drawn.

##### str_trim()
str_trim() removes whitespace from start and end of string.

