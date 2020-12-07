---
aliases: sharpe
---

# [[R package - PeerPerformance]]

### Description
Function which computes the [[Sharpe ratio]].

### Usage
```R
sharpe(X, level = 0.9, na.rm = TRUE)
```

### Arguments
* X: Vector (of lenght T) or matrix (of size T x N) of returns. NA values are allowed.
* na.rm: A logical value indicating whether NA values should be stripped before the computation. Default na.rm = TRUE.

### Value
Scalar or a vector (of size N) with the Sharpe ratios.