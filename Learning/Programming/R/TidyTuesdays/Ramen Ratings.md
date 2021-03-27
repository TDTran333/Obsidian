---
aliases: TidyTuesday - Ramen Ratings
tags: wip, R
---
Links: [Youtube](https://www.youtube.com/watch?v=tCa2di7aEP4), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#ramen-reviews), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/README.md), [Ramen Rater](https://www.theramenrater.com/resources-2/the-list/)

# TidyTuesday - Ramen Ratings
## Topic: Web scraping using `rvest` package
### Data
| variable      | class | description                                       |
|:------------- |:----- |:------------------------------------------------- |
| review_number | int   | Ramen review number, increasing from 1            |
| brand         | chr   | Brand of the ramen                                |
| variety       | chr   | The ramen variety, eg a flavor, style, ingredient |
| style         | chr   | Style of container (cup, pack, tray,              |
| country       | chr   | Origin country of the ramen brand                 |
| stars         | dbl   | 0-5 rating of the ramen, 5 is best, 0 is worst    |

### Annotations
| Time  | Description                                                                                                                                    |
| ----- |:---------------------------------------------------------------------------------------------------------------------------------------------- |
| 1:45  | Looking at the website the data came from                                                                                                      |
| 2:55  | Using gather function (now pivot_longer) to convert wide data to long (tidy) format                                                            |
| 4:15  | Graphing counts of all categorical variables at once, then exploring them                                                                      |
| 5:35  | Using fct_lump function to lump three categorical variables to the top N categories and "Other"                                                |
| 7:45  | Using reorder_within function to re-order factors that have the same name across multiple facets                                               |
| 9:10  | Using lm function (linear model) to predict star rating                                                                                        |
| 9:50  | Visualising effects (and 95% CI) of indendent variables in linear model with a coefficient plot (TIE fighter plot)                             |
| 11:30 | Using fct_relevel function to get "Other" as the base reference level for categorical independent variables in a linear model                  |
| 13:05 | Using extract function and regex to split a camelCase variable into two separate variables                                                     |
| 14:45 | Using facet_wrap function to split coefficient / TIE fighter plot into three separate plots, based on type of coefficient                      |
| 15:40 | Using geom_vline function to add reference line to graph                                                                                       |
| 17:20 | Using unnest_tokens function from tidytext package to explore the relationship between variety (a sparse categorical variable) and star rating |
| 18:55 | Explanation of how he would approach variety variable with Lasso regression                                                                    |
| 19:35 | Web scraping the using rvest package and SelectorGadget (Chrome Extension CSS selector)                                                        |
| 21:20 | Actually writing code for web scraping, using read_html, html_node, and html_table functions                                                   |
| 22:25 | Using clean_names function from janitor package to clean up names of variables                                                                 |
| 23:05 | Explanation of web scraping task: get full review text using the links from the review summary table scraped above                             |
| 25:40 | Using parse_number function as alternative to as.integer function to cleverly drop extra weird text in review number                           |
| 26:45 | Using SelectorGadget (Chrome Extension CSS selector) to identify part of page that contains review text                                        |
| 27:35 | Using html_nodes, html_text, and str_subset functions to write custom function to scrape review text identified in step above                  |
| 29:15 | Adding message function to custom scraping function to display URLs as they are being scraped                                                  |
| 30:15 | Using unnest_tokens and anti_join functions to split review text into individual words and remove stop words (e.g., "the", "or", "and")        |
| 31:05 | Catching a mistake in the custom function causing it to read the same URL every time                                                           |
| 31:55 | Using str_detect function to filter out review paragraphs without a keyword in it                                                              |
| 32:40 | Using str_remove function and regex to get rid of string that follows a specific pattern                                                       |
| 34:10 | Explanation of possibly and safely functions in purrr package                                                                                  |
| 37:45 | Reviewing output of the URL that failed to scrape, including using character(0) as a default null value                                        |
| 48:00 | Using pairwise_cor function from widyr package to see which words tend to appear in reviews together                                           |
| 51:05 | Using igraph and ggraph packages to make network plot of word correlations                                                                     |
| 51:55 | Using geom_node_text function to add labels to network plot                                                                                    |
| 52:35 | Including all words (not just those connected to others) as vertices in the network plot                                                       |
| 54:40 | Tweaking and refining network plot aesthetics (vertex size and colour)                                                                         |
| 56:00 | Weird hack for getting a dark outline on hard-to-see vertex points                                                                             |
| 59:15 | Summary of screencast                                                                                                                          |

### Libraries and functions
##### pivot_longer()
pivot_longer() "lengthens" data, increasing the number of rows and decreasing the number of columns. gather() is similar and has been depreciated.

```R
gather(key = category, value = value, -review_number, -stars)
pivot_longer(cols = c(-review_number, -stars) , names_to = "category", values_to = "value")
```

##### pivot_wider()
pivot_wider() "widens" data, increasing the number of columns and decreasing the number of rows. spread() is similar and has been depreciated.

##### slice_max()
slice_max() select rows with highest or lowest values of a variable. top_n() has been superseded in favour of slice_min()/slice_max().

```R
top_n(n = 16, wt = n)
slice_max(order_by = n, n = 16)
```

##### fct_reorder()
Reorder factor levels by sorting along another variable.

##### fct_lump()
Lump together factor levels into "other". Positive n preserves the most common n values. Negative n preserves the least common -n values.

##### fct_relevel()
Reorder factor levels by hand.

##### replace_na()
Replace NAs with specified values. If data is a data frame, replace takes a list of values, with one value for each column that has NA values to be replaced.

##### extract()
Extract a character column into multiple columns using regular expression groups.

##### parse_number()
This drops any non-numeric characters before or after the first number. 

##### str_subset()
Keep strings matching a pattern, or find positions.

##### message()
Generate a diagnostic message from its arguments.

##### stop_words
English stop words from three lexicons, as a data frame. 

##### slice()
slice() lets you index rows by their (integer) locations. It allows you to select, remove, and duplicate rows.

##### semi_join()
semi_join() return all rows from x with a match in y.

#### library(githubinstall)
The githubinstall package provides a way to install packages on GitHub by only their package names just like install.packages().

#### library(drlib)
Personal R package of David Robinson

##### reorder_within() + scale_x_reordered() custom functions
Reorder an x or y axis within facets

#### library(broom)
Convert statistical analysis objects from R into tidy tibbles, so that they can more easily be combined, reshaped and otherwise processed with tools like dplyr, tidyr and ggplot2.

##### tidy()
Tidy summarizes information about the components of a model. conf.int = TRUE to generate confidence interval.

#### library(tidytext)
Text Mining using 'dplyr', 'ggplot2', and Other Tidy Tools.

##### unnest_token()
Split a column into tokens using the tokenizers package.

#### library(widyr)
Widen, process, and re-tidy a dataset.

A wide dataset is one or more matrices where:

* Each row is one **item**
* Each column is one **feature**
* Each value is one **observation**
* Each matrix is one **variable**

When would you want data to be wide rather than tidy? Notable examples include classification, clustering, correlation, factorization, or other operations that can take advantage of a matrix structure. In general, when you want to compare between items rather than compare between variables, this is a useful structure.

#### library(igraph)
igraph is a library and R package for network analysis.

#### library(ggraph)
An Implementation of Grammar of Graphics for Graphs and Networks.

#### library(graphlayouts)
Layout algorithms for network visualizations.

More on correlation graph: https://www.tidytextmining.com/ngrams.html
More on igraph: [Network Analysis and Visualization with R and igraph](https://kateto.net/networks-r-igraph)
More on ggraph: [layouts](https://www.data-imaginist.com/2017/ggraph-introduction-layouts/), [nodes](https://www.data-imaginist.com/2017/ggraph-introduction-nodes/), [edges ](https://www.data-imaginist.com/2017/ggraph-introduction-edges/), [Network Visualizations in R](http://mr.schochastics.net/netVizR.html)

```R
filtered_cors %>% 
  graph_from_data_frame(vertices = nodes) %>% 
  ggraph(layout = 'fr') +
  geom_edge_link() +
  geom_node_point(aes(size = reviews * 1.1)) +
  geom_node_point(aes(size = reviews, color = avg_rating)) +
  geom_node_text(aes(label = name), repel = TRUE) +
  scale_color_gradient2(low = "red", high = "blue", midpoint = 4) +
  theme_void()
```