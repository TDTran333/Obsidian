Related Document:[[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds|Ardia & Boudt (2018)]]

What we want to do:

This figure presents the concept of screening plot. The left plot displays the average (annualized) monthly alpha for hedge funds ranked by decreasing alpha and grouped in 50 buckets. The right plot displays, for each of the 50 buckets, the average of the outperformance (black), equal–performance (light gray), and underperformance (dark gray) ratios of the hedge funds belonging to that bucket based on sorting on alpha.

![[Pasted image 20201201180811.png]]

### Methodology


### Notes from call on Nov 25 2020

* GHG Emission Intensity is defined as GHG / Revenues
	* How to define Green or Brown? top/bottom 10%/25%?
* Data was based on a yearly basis (either all available as at December or as at January) vs. mine who were monthly and converted to yearly (using average values during the year)
	* Add in industry category data?
* Extreme values were winsorized 
	* Replaced them by their 0.005 and 0.995 quantiles 

##### Analysis for next week:
1. Unconditional analysis
	* Apply peer perf on all data
		* Use mean of data
		* Use factor model
2. There are three groups: Green, Brown, Non-Disclosed (Grey)
	* Verify peer performance within each group
3. Find top green firms vs. top brown firms (Green Minus Brown Index)
	* Peer perf over time with equal weighted portfolio

##### To do

- [ ] Set up data
- [ ] Set up factor model
- [ ] Run alphaScreening]
- [ ] Make charts

### Notes - Week 5
- Windorized ghg_total
- Format df for alphaScreening
	- Need Matrix format
- Why are returns missing???
- Calculated disclosed and undisclosed
- Calculated green, brown and in between
- Generated alpha screening
- Create a function for charting
- In the paper, risk-adjusted returns = factor model returns

### Issues
* Reference code on dropbox is incomplete
	* Lack some functions and a folder or two
		* What is f.load.hf()
	* The general idea is there so still can replicate the code logic

* Using alpha screening on sample hf data give some weird results
	* Can't replicate screenplots
		* pipos and pineg are both there at the same time in the model
			* Weird graph results
	* Maybe sample too small?

### Logic of reference code

##### screening function
* screening function takes hf(df from alphaScreening) and nblock as input
* order alpha in decreasing
* nrow of hf
* preallocate empty tbl
* loop from 1:nblock
	* for each block of data
		* generate mean of alpha, pipos, pizero and pineg 

##### run screening code

* load hf data
* set factor model
* set nblock
* loop through hf strats
* mean of screening tbl

##### generate graph

```R
# 1st chart

cex = cex.axis = 0.8
postscript(file = paste0("fig_screen_", factor.model, "_", name, ".eps"))
par(mfrow = c(1, 2))
plot(12 * 100 * tbl.scr[, 1], 1:nblock, type = 'b', las = 1, pch = 20, cex = cex, cex.axis = cex.axis, 
     xlab = "", ylab = "", main = "alpha", axes = FALSE)
box(); grid()
labs = seq(-30, 30, by = 10)
axis(side = 1, at = labs, labels = paste0(labs, "%"), cex.axis = cex.axis)
axis(side = 2, at = 1:nblock, labels = 1:nblock, las = 1, cex.axis = cex.axis)

# 2nd chart

mainstr = expression(hat(pi)^'+'*' / '*hat(pi)^0*' / '*hat(pi)^'-')
barplot(t(100 * tbl.scr[,2:4]), horiz = TRUE, names.arg = NULL, col = c(gray(0), gray(0.8), gray(0.5)),
        space = 0, xlab = "", xlim = c(0, 100), cex.names = cex.axis, border = NA,
        cex.axis = cex.axis, main = mainstr, las = 1, axes = FALSE)
labs = seq(0, 100, by = 25)
axis(side = 1, at = labs, labels = paste0(labs, "%"), cex.axis = cex.axis)
box()

# 3 dashed lines

x = seq(from = 104, to = -4, length.out = 200)
y = seq(from = 0, to = 100, length.out = 200)

par(new = TRUE); plot(x, y, type = 'l', lty = "dashed", lwd = 1, xlim = c(0, 100), ylim = c(0, 100), axes = FALSE, ylab = "", xlab = "")
par(new = TRUE); plot(x-27.5, y, type = 'l', lty = "dashed", lwd = 1, xlim = c(0, 100), ylim = c(0, 100), axes = FALSE, ylab = "", xlab = "")
par(new = TRUE); plot(x+27.5, y, type = 'l', lty = "dashed", lwd = 1, xlim = c(0, 100), ylim = c(0, 100), axes = FALSE, ylab = "", xlab = "")
dev.off()
```





