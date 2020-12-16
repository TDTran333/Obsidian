## Analysis for week 7
* Backward-looking analysis is for manager selection and performance ex-post
* Forward-looking analysis is for scope of skills
	* Ideally, we want to see Green has more scope for outperformance

## To do
- [x] Clean code even more
- [x] Redo rmd file
- [x] [[Transition Matrix]]
- [x] Verify reference code
- [x] Verify graph from Sidita thesis
	- [ ] Requires daily observations and aggregating to yearly because monthly is not enough
- [ ] Looping analysis
	- [x] Run analysis with buckets of 5 firms per bucket
	- [ ] Capture all the years
	- [ ] Save graph to png automatically
	- [ ] Calculate % of outperformance over time
- [ ] Test different options 
	- [ ] Modify the lambda parameter
	- [ ] Modify the hac option
	
### Notes
* Figured how to calculate the transition matrix
* Figured how to generate buckets for analysis
* Figure out how to loop the analysis
* What's the impact of setting the lambda rate?
*  Isn't the provided lambda already optimal?
*  Is there a function to test the MSE?
*  Do I have to build it?

### Issues
Erroneous prices and returns?
Ferson and Chen 2015 mentions that Barras pizeros are too large and discount funds with abnormal performances
Low test power
They tested mutual funds and hedge funds
* Lower pizero / almost no pizero
* Alot of bad and ugly / alot of good and some bad
Probability model to improve the power
Three simulations to estimate power and confusion matrix
Assume zero alpha, all good and all bad

The classic FDR method is good if the fraction of zero alpha funds is known to be large and the power of the test is high


