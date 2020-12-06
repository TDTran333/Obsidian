---
aliases: msharpeTesting
---

# [[R package - PeerPerformance]]

### Description
Function which performs the testing of the difference of modified Sharpe ratios.

### Usage
```R
msharpeTesting(x, y, level = 0.9, na.neg = TRUE, control = list())
```

### Arguments
* x: Vector (of lenght T) of returns for the first fund. NA values are allowed.
* y: Vector (of lenght T) of returns for the second fund. NA values are allowed.
* level: Modified Value-at-Risk level. Default: level = 0.90.
* na.neg: A logical value indicating whether NA values should be returned if a negative modified Value-at-Risk is obtained. Default na.neg = TRUE.
* control: Control parameters (see *Details*).

### Value
A list with the following components:
* n: Number of non-NA concordant observations.
* msharpe: Vector (of length 2) of unconditional modified Sharpe ratios.
* dmsharpe: Modified Sharpe ratios difference.
* tstat: t-stat of modified Sharpe ratios differences.
* pval: pvalues of test of modified Sharpe ratios differences.