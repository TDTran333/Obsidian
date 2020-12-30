---
aliases: Statistics interview questions, R interview questions
tags: R, stats
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

##### Time series
* Time series analysis
	* Trends
	* Seasonal variation
	* Serial correlation
	* Prediction models (Arima, Garch etc.)
*  xts object in R
*  [[Data Wrangling|Wrangling]] time series
	*  Subsetting
	*  Merging
	*  Functions over calendar periods
		*  apply.monthly()
		*  apply.yearly()

##### Principal components analysis
* Technique to reduce the dimensions of the dataset
* PCA allows reducing the number of variables without significant loss of informational value.
* prcomp(), predict(), summary()

###### prcomp()
Performs a principal components analysis on the given data matrix and returns the results as an object of class prcomp.

The following parameters of prcomp() reduce dimensions based on:

* `tol` - the standard deviation as percentage of the first component's standard deviation,
* `rank` - the maximal number of components.

##### Notes
* Central tendency measures and skewness
* The primary purpose of descriptive statistics is to provide a summary of the data. 
* Measures of central tendency represent the center point of values in a dataset. Measures of variability represent the extent to which a distribution is stretched or squeezed. 
* A categorical variable is a variable that can take on one of a limited number of possible values.
* Encoding of categorical data makes them useful for machine learning algorithms.
* Principal Component Analysis, or PCA, is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets, by transforming a large set of variables into a smaller one that still contains most of the information in the large set.
* PCA is essentially a rotation of the coordinate axes, chosen such that each successful axis captures as much variance as possible.
* In other words: The PCA's first component is the direction in which most of the most variability in the data lies. The second component is 90 degrees to the first component and gives the direction in which the most variability lies after the first principle component has been accounted for. This goes on until you run out of dimensions (determined by the number of variables).
* We say that 2 vectors are orthogonal if they are perpendicular to each other. i.e. the dot product of the two vectors is zero.

### Statistical Tests 
##### Normality tests
* Testing normality
	* Statistical test
		* Shapiro-Wilk test
		* Kolmogorov-Smirnov test
	*  Visual measure
		*  Q-Q plot
* Transformation of data for normality using log()
* Checking for normality in R

| Method                  | Function                |
|:----------------------- |:----------------------- |
| Shapiro-Wilk test       | shapiro.test(x)         | 
| Kolmogorov-Smirnov test | ks.test(x, Y = "pnorm") |
| Q-Q plot                | qqnorm(x); qqline(x)    |

`qqplot(x, y)` - produces a Q-Q plot of two datasets,
`qqnorm(x)` - produces a Q-Q plot against normal distribution.
`qqline(x)` adds a normal line by default.

##### Inference for a mean
* Confidence interval
* One-sample mean
* T-test assumptions
	* **Normally distributed ** underlying data
	* Random sample
	* Independent observations
* T-test in R: 
	* `t.test(x, mu = mu, conf.level = conf.level)`
	* `t.test(x)$conf.int`

##### Comparing two means
* Null hypothesis is that the two samples mean are equal
* Two-sample t-test assumptions
	* **Normally distributed ** underlying data 
	* Random sample
	* Independent observations
	* Homogeneity of variances
		* [[bartlett.test()|Bartlett]]'s test is used to test if k samples have equal variances.
* Two-sample (unpaired) t-test vs. paired t-test
* T-test in R
	* Two-sample t-test: `t.test(value ~ group, data = df, var.equal = TRUE)`
	* Paired t-test: `t.test(value ~ group, data = df, paired = TRUE)`

##### ANOVA
* ANalysis Of VAriance
* Test for multiple means using variance
* Why not multiple t-test?
	* Introduce multiple type I and type II errors
* ANOVA control for errors so that type I error remains at target %.
* ANOVA assumptions
	* Independence of cases
	* Normal distributions
	* Homogeneity of variances
* ANOVA in R
	* `oneway.test(value ~ group, data, var.equal = TRUE)`
* Boxplot to visualize  (Q1, Q3, IQR, min(Q1-1.5 x IQR), max (Q3+1.5 IQR), outliers)

##### Notes
* P-value: probability of observing what we've observed, assuming that the null hypothesis is true. 
* The Shapiro-Wilk test calculates a W statistic that tests whether a random sample comes from a normal distribution . We look at the p-value to reject $h_0$.
	* The test has the best power for a given significance level
* The Kolmogorov-Smirnov Goodness of Fit Test compares your data with a known distribution and lets you know if they have the same distribution.
* A Q-Q plot is a scatterplot created by plotting two sets of quantiles against one another. If both sets of quantiles came from the same distribution, we should see the points forming a line that's roughly straight.
* Normal data is an underlying assumption for many statistical tests. 
* The log transformation can be used to transform skewed data to approximately conform to normality.
* A t-test is a type of inferential statistic used to determine if there is a significant difference between the means of two groups, which may be related in certain features
* The confidence interval is a range in which we suspect the population's mean to land.
* The confidence interval of a population mean is generated from a t statistic and sample mean.
* The higher the confidence level, the more probable it is that the population's mean lands in the range. 
* The one-sample t-test is a statistical hypothesis test used to determine whether an unknown population mean is different from a specific value.
* The two-sample t-test (also known as the independent samples t-test) is a method used to test whether the unknown population means of two groups are equal or not.
* The one-way analysis of variance (ANOVA) is used to determine whether there are any statistically significant differences between the means of three or more independent (unrelated) groups.

### Regression Models 
##### Covariance and correlation
* Covariance is a measure of the joint variability of two random variables. 
	* For a sample, you divide by n minus 1, for the population, divide by n
* The correlation coefficient is measure of a linear relationship between two variables.
* Correlation does not imply causation.

##### Linear regression model
* Linear regression model
	* Dependent variable also called response
	* Independent variables or explanatory variables
	* Parameters
	* Error term
* Linear predictor function
	*  The beta coefficients reflect the degree of change in the outcome variable for every one unit of change in the predictor variables. 
* Assumptions
	* Linear relationship
	* Normally distributed errors
	* Homoscedastic errors (variance must be uniform) 
	* Independent observations 
* Linear model in R
	* lm()
	* predict()
	* plot() for diagnostic plots
		* The first plot shows if the residuals have non-linear patterns. 
		* The second plot shows a Q-Q plot to see if residuals are normally distributed. 
		* The third plot shows if residuals are spread equally along the ranges of predictors.
		* The last plot helps us to find influential cases.

##### Logistic regression model
* Logistic regession model
	* Go-to method for binary classification problems
	* Estimates the value of p, which is the probability that y amounts to 1
	* Logit is a logarithm of the odds
* Logistic function
	*  Takes only values from the range 0 to 1. And so does the probability. 
* Prediction of a binary response variable
	*  The rule of thumb says that if the returned value is above 0.5, we predict one. Otherwise, we predict zero. 
* Logistic regression in R 
	* `glm(formula, data, family = "binomial")`
	* `predict(model, data, type = "response")`

##### Model evaluation
* Training set and test set
* K-fold cross-validation
* Confusion matrix & Classification metrics
	* Accuracy
	* Precision
	* Recall
* Regression metrics
	* Root Mean Squared Error (correct for large errors) `Metrics::rmse() `
	* Mean Absolute Error (straightforward) `Metrics::mae()`
