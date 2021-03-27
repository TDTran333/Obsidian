---
aliases: TidyTuesday - Beer Production
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=BUFNZv72ow4)

# TidyTuesday - Beer Production
### Data



### Libraries and Functions
##### library(geofacet)

This R package provides geofaceting functionality for ggplot2. Geofaceting arranges a sequence of plots of data for different geographical entities into a grid that strives to preserve some of the original geographical orientation of the entities.

##### library(prophet)

Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.

Prophet is open source software released by Facebook’s Core Data Science team. 

##### tidyr::nest()
Nesting creates a list-column of data frames; unnesting flattens it back out into regular columns. Nesting is a implicitly summarising operation: you get one row for each group defined by the non-nested columns. This is useful in conjunction with other summaries that work with whole datasets, most notably models.

##### assign()
Assign a value to a name in an environment.

##### do()
This is a general purpose complement to the specialised manipulation functions filter(), select(), mutate(), summarise() and arrange(). You can use do() to perform arbitrary computation, returning either a data frame or arbitrary objects which will be stored in a list. This is particularly useful when working with models: you can fit models per group with do() and then flexibly extract components with either another do() or summarise().

##### ggsave()
ggsave() is a convenient function for saving a plot. It defaults to saving the last plot that you displayed, using the size of the current graphics device. It also guesses the type of graphics device from the extension.

### Tasks
##### How to set picture size in R chunk?
```R
{r, fig.width = x, fig.height = y}
```

##### How to disable scientific notion in R?
```R
options(scipen = 999)
```