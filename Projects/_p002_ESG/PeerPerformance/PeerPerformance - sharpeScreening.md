---
aliases: sharpeScreening
---

# [[R package - PeerPerformance]]

### Description
Function which performs the screening of a universe of returns, and computes the Sharpe outperformance
ratio.

### Usage
```R
sharpeScreening(X, control = list())
```

### Arguments
* X: Matrix (T x N) of T returns for the N funds. NA values are allowed.
* control Control parameters (see *Details*).

### Value

A list with the following components:
- n: Vector (of length N) of number of non-NA observations.
- npeer: Vector (of length N) of number of available peers.
- sharpe: Vector (of length N) of unconditional Sharpe ratios.
- dsharpe: Matrix (of size N x N) of Sharpe ratios differences.
- tstat: Matrix (of size N x N) of t-statistics.
- pval: Matrix (of size N x N) of p-values of test for alpha differences.
- lambda: Vector (of length N) of lambda values.
- pizero: Vector (of length N) of probability of equal performance.
- pipos: Vector (of length N) of probability of outperformance performance.
- pineg: Vector (of length N) of probability of underperformance performance.
