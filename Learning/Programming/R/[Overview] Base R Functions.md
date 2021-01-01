- [[data()]]
- [[with()]]
- [[which()]]
- [[sort()]]
- [[sample_fract()]]
- [[sample()]]
- [[by()]]

##### I()
Change the class of an object to indicate that it should be treated ‘as is’.

##### diff()
Returns suitably lagged and iterated differences.
[[I() in R formula]]

##### paste(), paste0()
Concatenate vectors after converting to character.

The difference between paste() and paste0() is that the argument sep by default is ” ” (paste) and “” (paste0). In conclusion, paste0() is faster than paste() if our objective is concatenate strings without spaces because we don't have to specify the argument sep

##### density()
The (S3) generic function density computes kernel density estimates. Its default method does so with the given kernel and bandwidth for univariate observations. 

Kernel density estimation is a non-parametric method of estimating the probability density function (PDF) of a continuous random variable. It is non-parametric because it does not assume any underlying distribution for the variable

##### colnames(), rownames()
Retrieve or set the row or column names of a matrix-like object. 

##### lines()
Add Connected Line Segments to a Plot.

##### qqplot()
qqplot produces a QQ plot of two datasets.

[How to interpret QQ-plot](https://stats.stackexchange.com/questions/101274/how-to-interpret-a-qq-plot)

##### qqnorm()
qqnorm is a generic function the default method of which produces a normal QQ plot of the values in y.

##### qqline()
qqline adds a line to a “theoretical”, by default normal, quantile-quantile plot which passes through the probs quantiles, by default the first and third quartiles.

##### tapply()
Apply a function to each cell of a ragged array, that is to each (non-empty) group of values given by a unique combination of the levels of certain factors.

##### cov(), var(), cor()
var, cov and cor compute the variance of x and the covariance or correlation of x and y if these are vectors. If x and y are matrices then the covariances (or correlations) between the columns of x and the columns of y are computed.

##### lm()
Fitting Linear Models.

##### predict()
predict is a generic function for predictions from the results of various model fitting functions. 

##### abline()
Add Straight Lines to a Plot.

##### print()
print prints its argument and returns it invisibly (via invisible(x)).
[[invisible() in R]]

##### gml()
glm is used to fit generalized linear models, specified by giving a symbolic description of the linear predictor and a description of the error distribution.

##### findInterval()
Given a vector of non-decreasing breakpoints in vec, find the interval containing each element of x.

##### seq_along()
`seq_along()` generates a sequence the same length of the argument passed, and in the context of a for loop is used to more easily generate the index to iterate over

##### data()
Loads specified data sets, or list the available data sets.
