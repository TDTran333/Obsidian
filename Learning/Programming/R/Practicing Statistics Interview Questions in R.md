---
aliases: Statistics interview questions
tags: status:wip, R
---
source: [datacamp](https://www.datacamp.com/)
author: Zuzanna Chmielewska - Actuary

---
# Practicing Statistics Interview Questions in R
### Probability Distributions
##### Overview of common distributions
![[Common distributions.png]]
https://en.wikipedia.org/wiki/List_of_probability_distributions
##### Probability functions in R

| prefix | purpose               | example |
|:------ |:--------------------- |:------- |
| d      | density               | dnorm() |
| p      | distribution function | pnorm() |
| q      | quantile function     | qnorm() |
| r      | random variables      | rnorm() |

`dbinom(x = k, size = n, prob = p)` calculates $P(X = k)$ for $X \sim B(n, p)$
`binom(q = k, size = n, prob = p)` calculates $P(X \le k)$ for  $X \sim B(n, p)$
For the discrete distribution with whole numbers: $P(X \ge k) = 1 - P(X \le k-1)$

##### Discrete distributions
| Discrete distributions        | R Code                       |
| ----------------------------- | -----------------------------|
| Discrete uniform distribution | `sample(1:6, size = 1)`        |
| Bernouilli distribution       | `rbinom(n, size = 1, prob = p)` |
| Binomial distribution         | `rbinom(n, size = k, prob = p)` |
 
* Frequency table & chart
	* table(sample) for discrete distributions
	* barplot(table(sample)) for discrete distributions
	* hist() for continuous distributions
* Reproducibility
	* set.seed()

##### Continuous distributions
* Discrete vs. continuous distributions (see notes)
* Normal distribution $N(\mu, \sigma^2)$
	* bell-shaped curve with two parameters
		* mean $\mu$
		* variance $\sigma^2$
			* standard deviation is the square root of the variance
	* fundamental to
		* sampling
		* hypothesis testing
	* 68-95-99.7 rule 

`punif(q = k, min = a, max = b)` calculates $P(X \le k)$ for $X \sim U(a, b)$
`pnorm(q = k)` returns $P(X \le k)$ for $X \sim N(0, 1)$

##### Central limit theorem
* The cental limit theorem (CLT) is a statistical theory stating that given a sufficiently large sample size from a population with a finite level of variance, the mean of all samples from the same population will be approximately equal to the mean of the population.
* The CLT implies that we can apply statistical methods that work for normal distributions to problems involving other types of distributions.
* Central limit theorem =/= law of large numbers
	* The Central limit Theorem states that when sample size tends to infinity, the sample mean will be normally distributed. 
	* The Law of Large Number states that when sample size tends to infinity, the sample mean equals to population mean.

##### Notes
- A probability distribution is a list of outcomes and their associated probabilities.
- A discrete distribution is one in which the data can only take on certain values, for example integers. A continuous distribution is one in which data can take on any value within a specified range (which may be infinite).
-  A function that represents a discrete probability distribution is called a probability mass function (pmf).
- A function that represents a continuous probability distribution is called a probability density function (pdf).
- The output of a probability mass function is a probability whereas the area under the curve produced by a probability density function represents a probability.
- A random sample is a set of observed items from the whole population. You can make inferences about the population based on a random sample taken from the population. 
- A/B testing, at its most basic, is a way to compare two versions of something to figure out which performs better.

### Exploratory Data Analysis 
##### Descriptive statistics
* Central tendency measures
	* mean
	* median
	* mode
* Variability measures
	* Variance
	* Standard deviation
	* Range

##### Categorical Data
* Types of categorical data
	* nominal
	* ordinal
* Factors in R
* Categorical data analysis
	* table()
	* barplot()
	* tapply()
* Categorial data encoding
	* label encoding
	* one hot encoding

###### tapply()
tapply() computes a measure (mean, median, min, max, etc..) or a function for each factor variable in a vector. It is a very useful function that lets you create a subset of a vector and then apply some functions to each of the subset. 

###### One hot encoding
For one hot encoding, you can use dummyVars() from the caret package.
```R
encoder <- dummyVars(~ category, data = df)
predict(encoder, newdata = df)
```

##### Notes
* Central tendency measures and skewness
* The primary purpose of descriptive statistics is to provide a summary of the data. 
* Measures of central tendency represent the center point of values in a dataset. Measures of variability represent the extent to which a distribution is stretched or squeezed. 
* A categorical variable is a variable that can take on one of a limited number of possible values.
* Encoding of categorical data makes them useful for machine learning algorithms.

### Statistical Tests 

### Regression Models 
