---
aliases:
tags: R, finance
---
Link:

# R for Finance

### Libraries, Function and Tricks

#### library(quantmod)
Specify, build, trade, and analyse quantitative financial trading strategies.

#### library(ttr)
A collection of over 50 technical indicators for creating technical trading rules. The pack-age also provides fast implementations of common rolling-window functions, and several volatil-ity calculations.



[Equity Factor Portfolio Case Study](https://www.youtube.com/watch?v=IAz1M16Mtlg) 
### Equity Factor Portfolio

###  Key Criteria
* Substantiated by academic and practitioner research
* Demonstrated historical return premium expected to persist
* Investable and defined with a systematic, rules based approach

### Factors
* Market
* Size
* Value
* Momentum
* Yield
* Volatility
* Quality
* Liquidity

### Single-Factor Indexes
Index differs across providers. Qualitative and quantitative differences.
* Similar factor definitions, but unique index construction process across providers.
* Different universe of assets depending on provider and parent index.
* Different risk and return characteristics
* Caveat of relying on historical backtest data, several of the indexes have less than 5 years of live performance.

### Multi-Factor Portfolio Construction

#### library(PortfolioAnalytics)
Portfolio optimization and analysis routines and graphics.

![[Pasted image 20210114111316.png]]
![[Pasted image 20210114111334.png]]
![[Pasted image 20210114111614.png]]
![[Pasted image 20210114111705.png]]
![[Pasted image 20210114111743.png]]
![[Pasted image 20210114111814.png]]

### Portfolio Simulation
![[Pasted image 20210114112053.png]]
![[Pasted image 20210114112124.png]]

## To learn: QuantLib

[Portfolio Optimization App with R Shiny](https://www.youtube.com/watch?v=wj8hNQNFlPI)

https://getwyze.com/from-excel-to-r-personal-finance-edition/
### From Excel to R
Excel is meant for data collection and display, not necessarily for further analysis.
R forces you to think about your data in specific ways so that it can be _further_ analyzed, visualized and/or modeled.

[Computational Finance in R: quantmod-package](https://www.youtube.com/watch?v=K3nOpzEfVwE)

##### new.env()
new.env returns a new (empty) environment with (by default) enclosure the parent frame.

##### eapply()
Apply a Function Over Values in an Environment.

##### merge()
Merge Two Data Frames.

##### do.call()
Execute a Function Call.


[Tidy Trading](https://www.youtube.com/watch?v=krdgh0e2t6g)
### Data Science and R for Investors

#### library(timetk)
The timetk package combines a collection of coercion tools for time series analysis.

#### library(tibbletime) - retired
Built on top of the 'tibble' package, 'tibbletime' is an extension that allows for the creation of time aware tibbles. Some immediate advantages of this include: the ability to perform time based subsetting on tibbles, quickly summarising and aggregating results by time periods, and calling functions similar in spirit to the map family from 'purrr' on time based tibbles.

#### library(tsibble)
The tsibble package provides a data infrastructure for tidy temporal data with wrangling tools.

#### library(PerformanceAnalytics)
PerformanceAnalytics provides an R package of econometric functions for performance and risk analysis of financial instruments or portfolios. This package aims to aid practitioners and researchers in using the latest research for analysis of both normally and non-normally distributed return streams.

#### library(PortfolioAnalytics)
PortfolioAnalytics is an R package to provide numerical solutions for portfolio problems with complex constraints and objective sets. The goal of the package is to aid practicioners and researchers in solving portfolio optimization problems with complex constraints and objectives that mirror real-world applications.

### Check later: Visualizing ML Models with LIME
