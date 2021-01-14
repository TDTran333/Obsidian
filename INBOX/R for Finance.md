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