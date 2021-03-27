---
aliases: alphaScreening
---

# [[R package - PeerPerformance]]

### Description
Function which performs the screening of a universe of returns, and computes the alpha outperformance ratio -- defined as the percentage number of funds that have a significantly lower alpha and correcting for luck using the false discovery approach from Storey (2002).

### Usage
```R
alphaScreening(X, factors = NULL, control = list())
```

### Arguments
- X: Matrix (T x N) of T returns for the N funds. NA values are 				allowed.
- factors: Matrix (T x K) of T returns for the K factors. NA values are allowed.
- control: Control parameters (see *Details*).

### Value

A list with the following components:
- n: Vector (of length N) of number of non-NA observations.
- npeer: Vector (of length N) of number of available peers.
- alpha: Vector (of length N) of unconditional alpha.
- dalpha: Matrix (of size N x N) of alpha differences.
- tstat: Matrix (of size N x N) of t-statistics.
- pval: Matrix (of size N x N) of p-values of test for alpha differences.
- lambda: Vector (of length N) of lambda values.
- pizero: Vector (of length N) of probability of equal performance.
- pipos: Vector (of length N) of probability of outperformance performance.
- pineg: Vector (of length N) of probability of underperformance performance.
