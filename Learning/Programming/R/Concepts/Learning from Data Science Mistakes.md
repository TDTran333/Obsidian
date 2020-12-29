---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=O5lP6XcopdQ)

# Learning from Data Science Mistakes

### Why share mistakes?
* Transparency
* To help
* Growth

### Two types of mistakes
* Technical mistakes
* Communication mistakes

Technical mistakes decreases over time.
Communication is harder than tech.

#### Example of technical mistakes
* Non-reproducible data prep step
* Evaluate model based on performance of training set
* Not noticing large outliers
* Dropping missing values when it makes sense to flag them
* Flagged missing values when it makes sense to drop them
* Set missing values to zero
* Not comparing a complex model to a simple baseline
* Failing to understand nuances of data collection
* Building model for the wrong point in time
* Deleting records with missing values
* Predicting the wrong outcome
* Make faulty assumptions about time zones
* Including anachronistic variables
* Treating categorical variables as continous
* Treating continuous variables as categorical
* Filtering training set to incorrect population
* Forget to include the y-variable in the training set
* Not looking at number of missing values in a column
* Make faulty assumptions about data format
* Not filtering for duplicates within the dataset
* Including ID fields as predictors
* Failing to bin or account for rare categories
* Using proxies of outcome as predictors
* Make faulty assumptions about data source
* Handling missing values incorrectly
* Capping outliers in a way that don't make sense with data
* Misunderstand variable relationships due to incomplete EDA
* Failing to create calculated variables from raw data
* Building a model on the wrong population
* Using the wrong measure to judge the model quality
* etc

#### The usual suspects
* Understanding of data source(s)
* Assumptions
* Filters
* Missing values
* Understanding of model goals

#### Mistakes regarding communicating with Devs
* Time zone problems
* Data munging decisions hid errors
* Lack of shared resources explaining what the data was

#### Lessons about communication with Devs
* Be willing to teach, and to learn (respectfully)
* Don't play telephone
* Avoid jargon for clarity
* Same team! (Focus on common goals)

#### Mistakes regarding communicating with Business Stakeholders
