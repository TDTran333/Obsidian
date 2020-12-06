---
aliases: sharpeTesting
---

# [[R package - PeerPerformance]]

### Description
Function which performs the testing of the difference of Sharpe ratios.

### Usage
```R
sharpeTesting(x, y, control = list())
```

### Arguments
* x: Vector (of lenght T) of returns for the first fund. NA values are allowed.
* y: Vector (of lenght T) returns for the second fund. NA values are allowed.
* control: Control parameters (see *Details*).

### Value
A list with the following components:
* n: Number of non-NA concordant observations.
* sharpe: Vector (of length 2) of unconditional Sharpe ratios.
* dsharpe: Sharpe ratios difference.
* tstat: t-stat of Sharpe ratios differences.
* pval: pvalues of test of Sharpe ratios differences.