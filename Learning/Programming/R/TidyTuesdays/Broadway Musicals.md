---
aliases: TidyTuesday - Broadway Musicals
tags: R 
---
Links: [YouTube](https://www.youtube.com/watch?v=OhY5ZaILRpg), Annotations, [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-04-28/readme.md)

# Tidy Tuesday : Broadway Musicals
## Topics: Creating an interactive dashboard with `shinymetrics` and `tidymetrics`, moving windows, period aggregation

### Data
This data comes from [Playbill](https://www.playbill.com/grosses). Weekly box office grosses comprise data on revenue and attendance figures for theatres that are part of [The Broadway League](https://en.wikipedia.org/wiki/The_Broadway_League), an industry association for Broadway theatre.

* `grosses.csv`
* `synopses.csv`
* `cpi.csv`
* `pre-1985-starts.csv`

### Annotations
| Time  | Description                                                                                                                                                                                     |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8:15  | Use the cross_by_periods  function from the tidymetrics package to aggregate data over time (month, quarter, and year) then visualize with geom_line.                                           |
| 14:00 | Use the cross_by_periods  function from the tidymetrics package with windows = c(28)) to create a 4-week rolling average across month, quarter, and year.                                       |
| 21:50 | Create and interactive dashboard using the shinymetrics and tidymetrics packages.                                                                                                               |
| 25:00 | Use the str_remove function from the stringr package to remove matched pattern in a string.                                                                                                     |
| 25:20 | Use the cross_by_dimensions function from the tidymetrics package which acts as an extended group_by that allows complete summaries across each individual dimension and possible combinations. |
| 41:25 | Use the shinybones package to create an interactive dashboard to visualize all 3 metrics at the same time.                                                                                      |

### Libraries, Functions and Tricks

#### library(tidymetrics)
Tidymetrics allows you to easily calculate your metric by different periods (daily, weekly, monthly) and dimensions.

##### cross_by_periods()
Expand a table so that it can be aggregated by a period.

###### arguments: periods, windows and intervals
periods: 
* A vector of calendar periods. This supports "day", "week", "month", "quarter", and "year".
windows: 
* A vector of windows, each representing a # of days
intervals:
* Whether a preselected set of intervals starting from today, such as "Last Week", "Last 2 Weeks", or "All Time" should be included.

##### cross_by_dimension()
This function stacks an extra copy of the table for each dimension column specified as an argument, replaces the value of the column with the word "All", and finally groups by all the columns. It acts as an extended group_by that allows complete summaries across each individual dimension and possible combinations.

##### use_metrics_scaffold()
Create a scaffold for documenting metrics. Use this to generate a YAML scaffold for documenting metrics, just prior to running create_metrics().

##### create_metrics()
Given a metric tbl and an Rmd file, turn into a named list of metric objects.

#### library(shinymetrics)
A collection of shiny modules to visualize tidy metrics.

##### preview_metric()
Preview a metric in a shinydashboard.

#### library(shinybones)
A highly opinionated framework for building shiny dashboards.

##### [font awesome](https://fontawesome.com/) for icon in yaml

##### Find the name of a show
```R
grosses %>% filter(str_detect(show, "Book")) %>% distinct(show)
```