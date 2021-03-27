---
aliases: TidyTuesday - Friends
tags: R
---
Links: [YouTube](https://www.youtube.com/watch?v=bgcBEBqVnx8), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#friends), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-09-08/readme.md)

# TidyTuesday - Friends
## Topics: Data Manipulation, Linear Modeling, Pairwise Correlation, Text Mining, Tidylo

### Data
[`friends` R package](https://github.com/EmilHvitfeldt/friends) for the Friends transcripts and additional information.T

### Annotations
| Time    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:------- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 7:30    | Use dplyr package's count function to count the unique values of multiple variables.                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9:35    | Use geom_col to show how many lines of dialogue there is for each character. Use fct_reorder to reorder the speaker factor levels by sorting along n.                                                                                                                                                                                                                                                                                                                                                        |
| 12:07   | Use semi_join to join friends dataset with main_cast with by = ""speaker returning all rows from friends with a match in main_cast.                                                                                                                                                                                                                                                                                                                                                                          |
| 12:30   | Use unite to create the episode_number variable which pastes together season and episode with sep = ".". Then, use inner_join to combine above dataset with friends_info with by = c("season", "episode"). Then, use mutate and the glue package instead to combine { season }.{ episode } { title }. Then use fct_reorder(episode_title, season + .001 * episode) to order it by season first then episode.                                                                                                 |
| 15:45   | Use geom_point to visualize episode_title and us_views_millions. Use as.integer to change episode_title to integer class. Add labels to geom_point using geom_text with check_overlap = TRUE so text that overlaps previous text in the same layer will not be plotted.                                                                                                                                                                                                                                      |
| 19:95   | Run the above plot again using imdb_rating instead of us_views_millions                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 21:35   | Ahead of modeling: Use geom_boxplot to visualize the distribution of speaking for main characters. Use the complete function with fill = list(n = 0) to replace existing explicit missing values in the data set. Demonstration of how to account for missing imdb_rating values using the fill function with .direction = "downup" to keep the imdb rating across the same title.                                                                                                                           |
| 26:45   | Ahead of modeling: Use summarize with cor(log2(n), imdb_rating)  to find the correlation between speaker and imdb rating -- the fact  that the correlation is positive for all speakers gives David a  suspicion that some episodes are longer than others because they're in 2  parts with higher ratings due to important moments. David addresses  this confounding factor by including percentage of lines instead of number of lines. Visualize results with geom_boxplot, geom_point with geom_smooth. |
| 34:05   | Use a linear model to predict imdb rating based on various variables.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 42:00   | Use the tidytext and tidylo  packages to see what words are most common amongst characters, and  whether they are said more times than would be expected by chance. Use geom_col to visualize the most overrepresented words per character according to log_odds_weighted.                                                                                                                                                                                                                                   |
| 54:15   | Use the widyr package and pairwise correlation to determine which characters tend to appear in the same scences together? Use geom_col to visualize the correlation between characters.                                                                                                                                                                                                                                                                                                                      |
| 1:00:25 | Summary of screencast                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

### Libraries, Functions and Tricks
##### unite()
Unite multiple columns into one by pasting strings together.

###### parameter: remove = TRUE by default.
If TRUE, remove input columns from output data frame.

##### trick to order episodes correctly
```R
fct_reorder(episode_title, season + .001 * episode)
```

##### remove x.axis labels
```R
theme(axis.text.x = element_blank())
```

##### change episode_title to integer to put the chart on numeric scale instead

##### fill()
Fill in missing values with previous or next value.

##### Scoped verbs (\_if,\_at,\_all) 
Have been superseded by the use of across() in an existing verb. 

##### anova()
Compute analysis of variance (or deviance) tables for one or more fitted model objects.

##### aov()
Fit an analysis of variance model by a call to lm for each stratum.

#### library(tidylo)
This package implements a different approach for measuring which words are important to a text, a weighted log odds. The analytical question is focused on differences in frequency across sets. A log odd ratio is about how frequently a word is used by a speaker vs. how frequently it is used across speakers.

See: [[td-idf]]