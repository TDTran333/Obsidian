---
aliases: TidyTuesday - Cocktails
tags: R 
---
Links: [YouTube](https://www.youtube.com/watch?v=EC0SVkFB2OU), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#cocktails), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-05-26/readme.md)

# TidyTuesday - Cocktails
## Topics: Pairwise correlation, Network diagram, Principal component analysis (PCA)

### Data
* Mr Boston dataset was acquired from the [Mr. Boston Bartender's Guide](http://swizzle.ru/uploads/article_file/17/mr_boston.pdf)
* `cocktails.csv` dataset was web-scraped as part of a hackathon.

### Annotations
| Time  | Description                                                                                                                                                                                                                 |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 6:20  | Use fct_reorder from the forcats package to reorder the ingredient factor levels along n.                                                                                                                                   |
| 7:40  | Use fct_lump from the forcats package to lump together all the levels except the n most frequent in the category and ingredient variables.                                                                                  |
| 11:30 | Use pairwise_cor from the widyr package to find the correlation between the ingredients.                                                                                                                                    |
| 16:00 | Use reorder_within from the tidytext package with scale_x_reordered to reorder the the columns in each facet.                                                                                                               |
| 19:45 | Use the ggraph and igraph packages to create a network diagram                                                                                                                                                              |
| 25:15 | Use extract from the tidyr package with regex = (\.\*) oz to create a new variable amount which doesn't include the oz.                                                                                                       |
| 26:40 | Use extract with regex to turn the strings in the new amount variable into separate columns for the ones, numerator, and denominator.                                                                                       |
| 28:53 | Use replace_na from the tidyr package to replace NA with zeros in the ones, numberator, and denominator columns. David ends up reaplcing the zero in the denominator column with ones in order for the calculation to work. |
| 31:49 | Use geom_text_repel from the ggrepel package to add ingredient labels to the geom_point plot.                                                                                                                               |
| 32:30 | Use na_if from the dplyr package to replace zeros with NA                                                                                                                                                                   |
| 34:25 | Use scale_size_continuous with labels = percent_format() to convert size legend values to percent.                                                                                                                          |
| 36:35 | Change the size of the points in the network diagram proportional to n using vertices = ingredient_info within graph_from_data_frame and aes(size = n) within geom_node_point.                                              |
| 48:05 | Use widely_svd from the widyr package to perform principle component analysis on the ingredients.                                                                                                                           |
| 52:32 | Use paste0 to concatenate PC and dimension in the facet panel titles.                                                                                                                                                       |
| 57:00 | Summary of screencast                                                                                                                                                                                                       |

### Libraries, Functions and Tricks

In SVD, the first dimension is usually the frequency.