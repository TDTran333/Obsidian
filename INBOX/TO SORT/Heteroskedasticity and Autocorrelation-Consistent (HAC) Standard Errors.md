---
aliases: HAC, HAC Standard Errors
---

http://econweb.umd.edu/~chao/Teaching/Econ423/Econ423_HAC_Estimation.pdf

https://www.econometrics-with-r.org/15-4-hac-standard-errors.html

The error term ut in the distributed lag model (15.2) may be serially correlated due to serially correlated determinants of Yt

that are not included as regressors. When these factors are not correlated with the regressors included in the model, serially correlated errors do not violate the assumption of exogeneity such that the OLS estimator remains unbiased and consistent.

However, autocorrelated standard errors render the usual homoskedasticity-only and heteroskedasticity-robust standard errors invalid and may cause misleading inference. HAC errors are a remedy.