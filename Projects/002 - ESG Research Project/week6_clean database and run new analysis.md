## Analysis for week 6
1. We want to see how green and brown move over time
	* Can't do unconditional analysis because ESG Intensity score depends on GHG and revenues and some firms can switch between green/neutral or brown/neutral over time
	* Rolling Window 5-yr using mean and median to rank firms
	* Two methods
		* Backward-looking
		* Forward-looking
2. Analysis done with 3-factors and 6-factors
3. Relax assumptions on database because of survivorship bias
4. We want to see the transition matrix (4x4) to see the probability of changing categories over time. Green, Neutral, Brown, Undisclosed.
5.  Generate Graphs.

## To do
- [x] Verify reference code
- [x] Clean database
- [ ] Transition Matrix
- [ ] Dynamic rolling window analysis
- [ ] Figure out how to illustrate the results

### Notes

### Issues

They stop disclosing but the moving average don't catch that
We take the previous 5-yr window because today's data might not have been updated for this year so we can't assume they stopped disclosing

Two ways to smooth. Moving average 60-mth than summarized on a yearly basis or moving average 5-year of summarized yearly average data.

Question: How to build the transition matrix if some stocks die and we don't get the full years?