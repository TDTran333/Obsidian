---
aliases: TidyTuesday - Coffee Ratings
tags: R 
---
Links: [Youtube](https://www.youtube.com/watch?v=-1x8Kpyndss&t=495s), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#coffee-ratings), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-07-07/readme.md)

# TidyTuesday - Coffee Ratings
## Topics: Ridgeline plot, Pairwise correlation, Network plot, Singular value decomposition (SVD), Linear model

### Data
The two most economically important varieties of coffee plant are the Arabica and the Robusta; ~60% of the coffee produced worldwide is Arabica and ~40% is Robusta. Arabica beans consist of 0.8–1.4% caffeine and Robusta beans consist of 1.7–4% caffeine.

[Coffee Quality Database](https://github.com/jldbc/coffee-quality-database)
There is data for both Arabica and Robusta beans, across many countries and professionally rated on a 0-100 scale. 

* However, most of the data are about Arabica ratings. (Arabica: n = 1311, Robusta: n = 28)
* Coffee beans are green or blueish. See [[Green Coffee Beans]].

### Annotations
| Time  | Description                                                                                                                                                        |
| ----- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 08:15 | Using fct_lump within count and then mutate to lump the variety of coffee together except for the most frequent                                                    |
| 08:50 | Create a geom_boxplot to visualize the variety and the distribution of total_cup_points                                                                            |
| 09:55 | Create a geom_histogram to visualize the variety and the distribution of total_cup_points                                                                          |
| 11:40 | Using fct_reorder to reorder variety by sorting it along total_cup_points in ascending order                                                                       |
| 12:35 | Using summarize with across to calculate the percent of missing data (NA) for each rating variable                                                                 |
| 15:20 | Create a bar chart using geom_col with fct_lump to visualize the frequency of top countries                                                                        |
| 20:35 | Using pivot_longer to pivot the rating metrics for wide format to long format                                                                                      |
| 21:30 | Create a geom_line chart to see if the sum of the rating categories equal to the total_cup_points column                                                           |
| 23:10 | Create a geom_density_ridges chart to show the distribution of ratings across each rating metric                                                                   |
| 24:35 | Using summarize with mean and sd to show the average rating per metric with its standard deviation                                                                 |
| 26:15 | Using pairwise_cor to find correlations amongst the rating metrics                                                                                                 |
| 27:20 | Create a network plot to show the clustering of the rating metrics                                                                                                 |
| 29:35 | Using widely_svd to visualize the biggest source of variation with the rating metrics (Singular value decomposition)                                               |
| 37:40 | Create a geom_histogram to visualize the distribution of altitude                                                                                                  |
| 40:20 | Using pmin to set a maximum numeric altitude value of 3000                                                                                                         |
| 41:05 | Create a geom-point chart to visualize the correlation between altitude and quality (total_cup_points)                                                             |
| 42:00 | Using summarize with cor to show the correlation between altitude and each rating metric                                                                           |
| 44:25 | Create a linear model lm for each rating metric then visualize the results using a geom_line chart to show how each kilometer of altitude contributes to the score |
| 50:35 | Summary of screencast                                                                                                                                              |

### Libraries, Functions and Tricks

##### See % of missing data for each columns
Can also use gather() %>% View() but gather() is retired.
```R
df %>%
  summarize(across(everything(), ~ mean(!is.na(.)))) %>% 
  pivot_longer(everything()) %>% 
  View()
```
  
##### Verify graphically if the sum of the individuals ratings equals the total with geom_point()

##### library(ggraph) and library(igraph) to show correlations graphically

##### between()
This is a shortcut for x >= left & x <= right.

##### pmin()
pmax*() and pmin*() take one or more vectors as arguments, recycle them to common length and return a single vector giving the ‘parallel’ maxima (or minima) of the argument vectors.


