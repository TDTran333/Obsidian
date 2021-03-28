---
aliases:
tags: stats
---
Link: [Wikipedia](https://en.wikipedia.org/wiki/Bessel%27s_correction)

# Bessel's correction
In statistics, Bessel's correction is the use of n − 1 instead of n in the formula for the sample variance and sample standard deviation, where n is the number of observations in a sample. This method corrects the bias in the estimation of the population variance. It also partially corrects the bias in the estimation of the population standard deviation. However, the correction often increases the mean squared error in these estimations. This technique is named after Friedrich Bessel.

You would only use Bessel’s correction (dividing by n-1 instead of n) if you were trying to estimate the variance of an underlying distribution - the variance of a raw dataset is still uses n.