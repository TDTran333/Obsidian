## Analysis for week 9 and week 10
We would like to see the impact of choosing stocks based on ESG indicators combined with the False Rate Discovery methodology.
To that effect, we will build portfolios and backtest them.

What are the portfolios we need:
Within ESG group type
* Top 10 green pipos minus top 10 pineg
* Top 10 brown pipos minus top 10 pineg
* Remaining stocks as benchmark

Across ESG group types
* Green ESG Portfolio according to ESG classification
* Brown ESG Portfolio according to ESG classification
* Neutral Portfolio as benchmark
* G minus Brown
* No transaction fees

Do it twice for GHG and Envscore

Also verify vs. portfolio based on alpha alone. To see if our methodology adds value vs. the naive methodology.

## To do
- [x] Plot perf ratios, concordant obs and cor
- [x] Add a table with summary stats of perf ratios, concordant obs and cor
- [ ] Maybe add a herfindahl index
- [x] Top green, top brown
	- [x] 3 portfolios
		- [x] Long-short top 10 / bottom 10 equi-weighted
		- [x] Remaining stock as benchmark
		- [x] Rebalanced every quarter / month
		- [x] Summary stats of portfolios
		- [x] Add indices stats?
		- [x] Annualized returns, stdev and sharpe ratios
		- [x] Chart of cumulative Return, Daily Return, Drawdown

### Notes

### Issues