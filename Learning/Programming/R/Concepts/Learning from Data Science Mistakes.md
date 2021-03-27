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

#### Learnings about communication with Devs
* Be willing to teach, and to learn (respectfully)
* Don't play telephone
* Avoid jargon for clarity
* Same team! (Focus on common goals)

#### Mistakes regarding communicating with Business Stakeholders
Don't roll out several features at the same time

Communicate the value of the data
How to frame your analysis for anyone
The rhetorical triangle consist of three parts: 
Speaker: Credentials and awareness of how people see analytics within the organization
Audience: What is the audience? Are they technical or non-technical? Are they informed?
Do they make decisions as part of a larger meeting? Who are you talking to?
Context: Are you delivering good news or bad news? What are you asking for? What can they help with? Do they understand the kind of problems you have?

#### Data Meta-Metrics

##### Relevance
a. Data is perfectly relevant and usable as-is to make important decisions.
b. Data is useful to add color to arguments or decisions but isn't a single definitive source of truth by itself
c. We don't recommend using this data to make important decisions

##### Trustworthiness
a. We trust this data, including the source and  the way it's captured, and feel comfortable using it to make important decisions.
b. We have some reservations with this data -- could be based on the way it's created, accessed, or an unexplained weirdness.
c. We don't trust this data due to the way it is collected or stored in current state.

##### Repeatability
a. The proces to get this metric is fully automated or automatable.
b. The process to get this data is standardized, but not fully automatable (involves a manual download or have to go through a point person).
c. Data does not live in a database; the process to get this data is very manual and cannot be automated in current state.

#### Learnings about communication with Business Stakeholders
* Get stakeholders involved early
* Make sure you understand the business problem
* Frame analyses in a way that makes sense, use proper terminology in the business
* Basiscs: who, what, how many?
* Know where to get their data

#### Problems regarding Infrastructure / Team
Need documentations in case people leave

Write pseudocode
* Inputs
* Outputs
* Business problem you're trying to solve
* Process
* Explanation
* ...all in plain English

#### Learnings about Infrastructure / Team
* Documentation
	* Data dictionaries
	* SQL query library
* Code review
* Core team meetings
* Pseudocode

Context is key.

### Advice for aspiring data scientists
* Learn SQL
* Communication is a technical skill
* Start a blog
* Teach others
* Don't worry about learning everything at first
* Find your community
* Stay curious
* Have fun
* Don't be afraid to Google
* Everyone is winging it