---
aliases: msharpeScreening
---

# [[R package - PeerPerformance]]

### Description
Function which performs the screening of a universe of returns, and computes the modified Sharpe outperformance ratio.

### Usage
```R
msharpeScreening(X, level = 0.9, na.neg = TRUE, control = list())
```

### Arguments
* X: Matrix (T  N) of T returns for the N funds. NA values are allowed.
* level: Modified Value-at-Risk level. Default: level = 0.90.
* na.neg: A logical value indicating whether NA values should be returned if a negative modified Value-at-Risk is obtained. Default na.neg = TRUE.
* control: Control parameters (see *Details*).

### Value

A list with the following components:
- n: Vector (of length N) of number of non-NA observations.
- npeer: Vector (of length N) of number of available peers.
- msharpe: Vector (of length N) of unconditional modified Sharpe ratios.
- dmsharpe: Matrix (of size N x N) of modified Sharpe ratios differences.
- tstat: Matrix (of size N x N) of t-statistics.
- pval: Matrix (of size N x N) of p-values of test for alpha differences.
- lambda: Vector (of length N) of lambda values.
- pizero: Vector (of length N) of probability of equal performance.
- pipos: Vector (of length N) of probability of outperformance performance.
- pineg: Vector (of length N) of probability of underperformance performance.
