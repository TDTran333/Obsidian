---
aliases: TidyTuesday - Beer Production
tags: R 
---
Links: [YouTube](https://www.youtube.com/watch?v=1R4X09w7tQ8&t), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#beer-production), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-03-31/readme.md)

# Tidy Tuesday : Beer Production
## Topics: Using `preview_metric` function from `shinymetrics` package to demonstrate `shinymetrics`

### Data
The data comes from the [Alcohol and Tobacco Tax and Trade Bureau (TTB)](https://www.ttb.gov/beer/statistics).

### Annotations
| Time    | Description                                                                                                                                  |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 4:25    | Asking, "What ingredients are used in beer?"                                                                                                 |
| 4:40    | Using filter and max functions to look at the most recent period of time                                                                     |
| 7:25    | Using paste and ymd functions (ymd is from lubridate package) to convert year-month field into an date-formatted field                       |
| 9:20    | Spotting potential missing or mis-parsed data                                                                                                |
| 13:50   | Introducing the tidymetrics framework                                                                                                        |
| 14:45   | Using install_github function to install tidymetrics from GitHub                                                                             |
| 15:25   | Using cross_by_dimensions function from tidymetrics package to get aggregations at different levels of multiple dimensions                   |
| 18:10   | Using cross_by_periods function from tidymetrics package to also get aggregations for different intervals (e.g, month, quarter, year)        |
| 22:00   | Using use_metrics_scaffold function from tidymetrics package to create framework for documenting dimensions in RMarkdown YAML header         |
| 24:00   | Using create_metrics function from tidymetrics package to save data as a tibble with useful metadata (good for visualizing interactively)    |
| 25:15   | Using preview_metric function from shinymetrics package (still under development as of 2020-04-24) to demonstrate shinymetrics               |
| 27:35   | Succesfuly getting shinymetrics to work                                                                                                      |
| 28:25   | Explanation of the shinymetrics bug David ran into                                                                                           |
| 34:10   | Changing order of ordinal variable (e.g., "1,000 to 10,000" and "10,000 to 20,000") using the parse_number, fct_lump, and coalesce functions |
| 41:25   | Asking, "Where is beer produced?"                                                                                                            |
| 46:45   | Looking up sf package documentation to refresh memory on how to draw state borders for a map                                                 |
| 48:55   | Using match function and state.abb vector (state abbreviations) from sf package to perform a lookup of state names                           |
| 51:05   | Using geom_sf function (and working through some hiccoughs) to create a choropleth map                                                       |
| 52:30   | Using theme_map function from ggthemes package to get more appropriate styling for maps                                                      |
| 55:40   | Experimenting with how to get the legend to display in the bottom right corner                                                               |
| 58:25   | Starting to build an animation of consumption patterns over time using gganimate package                                                     |
| 1:03:40 | Getting the year being animated to show up in the title of a gganimate map                                                                   |
| 1:05:40 | Summary of screencast                                                                                                                        |
| 1:06:50 | Spotting a mistake in a group_by call causing the percentages not to add up properly                                                         |
| 1:09:10 | Brief extra overview of tidymetrics code                                                                                                     |

### Libraries, Functions and Tricks

##### coalesce()
Find first non-missing element.

###### count's wt argument
If NULL (the default), counts the number of rows in each group.
If a variable, computes sum(wt) for each group.

#### library(maps)
Display of maps.

#### library(sf)
A package that provides [simple features access](https://en.wikipedia.org/wiki/Simple_Features) for R.

##### st_to_sf()
Convert foreign object to an sf object.

##### theme(legend.position =  c(x, y)) 
c(1,1) = bottom left, c(0, 0) = top right

#### library(gganimate)
`gganimate` extends the grammar of graphics as implemented by `ggplot2` to include the description of animation

##### transition_manual()
Create an animation by specifying the frame membership directly.

#### library(shinymetrics)

NOTE: Shinymetrics last updated was April 2020. The "bugs" I have been getting is that the periods use the current Sys.Date() and not the max date of the dataset. This means that most periods are not functional.

[Metric Design and Dashboarding with tidymetrics and shinybones](https://www.youtube.com/watch?v=BL5NBRxnl3E)

North Star Metric (NSM)
* ONE metric that measures how your product delivers value to its users

Gaming the NSM

> "When a metric becomes a target, it ceases to become a good measure."

"Safety" metrics
* Balance out the NSM by guarding against:
	* artificial inflations
	* gaming the system
	* the decisions you make that influence the metric

tidymetrics

cross_by_periods()

cross_by_dimensions()

use_metrics_scaffold()

shinymetrics & shinybones