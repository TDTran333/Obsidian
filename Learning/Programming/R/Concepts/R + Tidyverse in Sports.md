---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=L-kRMiYwRC4)

# R + Tidyverse in Sports

### Hockey analytics with R
Features used
Adjustment to the data
Expected goals in hockey analytics
Play-by-play data from nhl than scraped and cleaned to moneypuck.com
Cleaned up and tidy data

#####  download.file()
Download File from the Internet.

##### unz()
unz reads (only) single files within zip files, in binary mode. 

##### unlink()
Delete Files and Directories.

##### map_dfr(), map_dfc()
map_dfr() and map_dfc() return a data frame created by row-binding and column-binding respectively. 

### Modeling
Logistic Regression on expected goals using distance to net as based model

Using xgboost to incorporate more features about shots and not assume linearity
Use cross-validation to choose the # of boosting rounds
Using machine learning to predict probability and expected goals

Shot distance is the most important variable

Using geom_smooth() to visualize the results between the xG models

Model comparisons
Log Loss
Area under the curve
Specific player probability vs. the models



