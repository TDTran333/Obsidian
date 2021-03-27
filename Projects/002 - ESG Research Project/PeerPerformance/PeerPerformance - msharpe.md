---
aliases: msharpe
---

# [[R package - PeerPerformance]]

### Description
Function which computes the [[Modified Sharpe Ratio]]

### Usage
```R
msharpe(X, level = 0.9, na.rm = TRUE, na.neg = TRUE)
```

### Arguments
* X: Vector (of lenght T) or matrix (of size T x N) of returns. NA values are allowed.
* level: Modified Value-at-Risk level. Default: level = 0.90.
* na.rm: A logical value indicating whether NA values should be stripped before the computation. Default na.rm = TRUE.
* na.neg: A logical value indicating whether NA values should be returned if a negative modified Value-at-Risk is obtained. Default na.neg = TRUE.

### Value
Scalar or a vector (of size N) with the modified Sharpe ratios.