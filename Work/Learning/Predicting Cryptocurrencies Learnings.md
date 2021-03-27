---
aliases:
tags: Finance
---
Link: [Website](https://hackernoon.com/what-i-learned-trying-to-predict-the-price-of-cryptocurrencies-9v2r32m1)

## Takeaways
Cryptocurrency price predictions is a solvable problem but not by a single approach and definitely not for all market conditions.
	* George E. P. Box once said, “essentially, all models are wrong, but some are useful”.

There are two fundamental ways to think about prediction: asset-based or factor-based.

### Approaches
There are three fundamental technical approaches to tackle crypto asset predictions.
	* Time-series forecasting, traditional machine learning and deep learning methods.
	
1. Time series forecasting methods are easy to implement but not very resilient
	* One of the biggest limitations of time series methods is that they rely on a small and fixed number of predictors which proven to be insufficient to describe the behavior of crypto-assets.
	* ARIMA, DeepAR+, Prophet
	* Easy to implement and fast to execute
	* Poor resiliency to market fluctuations
	* Limited number of potential preditors
	* Hard to estimate predictors ahead of time
	
2.  Traditional machine learning models showed poor generalization capabilities
	* Most traditional machine learning models have trouble generalizing knowledge and are very prompt to underfit.
	* Linear regression, decision trees
	* There is a lot of research available in this area
	* Poor resiliency to market fluctuations
	* Hard to achieve knowledge generalization (underfitting) in test sets
	* Prompt to overfit training sets
	
3. Deep learning models are hard to interpret but can perform well in complex market conditions.
	* Deep learning models can achieve decent levels of performance when comes to predictions. However, its near impossible to interpret what these models are doing internally given its complexity and they are definitely challenging to implement.
	* Computationally expensive to execute at scale
	* Difficult to interpret
	* Many of the benefits such as automated feature extraction are hard to materialize
	* Great to tack sophisticated theses

Bidirectional LSTM might work
Test on accurary
Retraining periodicity

### Challenges
There are some very interesting challenges that are not present in capital markets.
	1) Crypto orderbook datasets have many quality issues
	2) Behaviors like wash trading or spoofing are common
	3) There are many time gaps and missing data points
	4) Most research papers don't stand the test of real market data
	5) Most research methods haven't been designed for highly volatile markets