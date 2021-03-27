Barras, Laurent, Olivier Scaillet, and Russ Wermers. “False Discoveries in Mutual Fund Performance: Measuring Luck in Estimated Alphas.” Journal of Finance 65, no. 1 (February 2010): 38.

---

### From the abtract, there are 4 key resuts.
> This paper develops a simple technique that controls for “false discoveries,” or mutual funds that exhibit significant alphas by luck alone.

1. Introduce a new methodology that controls for false discovery
	
> We find that 75% of funds exhibit zero alpha (net of expenses), consistent with the [[Berk and Green equilibrium]]. 

2. Most mutual funds display zero alpha. Similar conclusion to other papers.

> Further, we find a  significant proportion of skilled (positive alpha) funds prior to 1996, but almost none by 2006. 

3. Positive alpha are gone.

> We also show that controlling for false discoveries substantially improves the ability to find the few funds with persistent performance.

4. The new methodology help select funds with persistent performance
	* That's a very important result for manager selection

### Initial comprehension from skimming the text:

##### Structure

Introduction
* Finding outperforming / skilled fund managers
	
Section I : Methodology
* Defining Luck
* Measuring Luck
* Estimation methodology
* Comparison to existing methods
* Careful of cross-correlation

Section II : Data
Section III : Results

Section IV : Conclusion

> With our approach, controlling for luck in multiple testing is trivial: The only input required is a vector of p-values, one for each individual test.

![[Pasted image 20201116131647.png]]
![[Pasted image 20201117005616.png]]

##### From skimming the paper, I got a few things to note.

* What is luck in term of fund performance? 
* How do you define it? 
* How can we remove luck? 
* What can we conclude when we remove it?

IMPORTANT: 

![[Pasted image 20201118041444.png]]

### Questions to answer when I read more in details

What I understand from this paper:
* This paper introduce a methodology that control for false discoveries and capture unskilled and skilled fund managers in the mutual fund universe
* It found that manager skills has decreased over time
What I don't understand:
* I still don't get it 100% but I think I understand the [[False Rate Discovery]] a bit better now
What do I need to research more on:
* My goal is to understand the methodology and how it was subsequently applied in [[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds]]
What are the related papers:
See the Storey (2002) and Storey (2003) papers

---
### Additional information

![[presentation_Scaillet.pdf]]
![[Wermers_SLIDES-FDROctober_2009.pdf]]

*Extracted Annotations (11/17/2020, 2:09:09 AM)*

"Of course, we cannot observe the true alpha of each fund in the
population. Therefore, a seemingly reasonable way to estimate the
prevalence of skilled fund managers is to simply count the number of
funds with sufficiently high estimated alphas, ˆα. In implementing such
a procedure, we are actually conducting a multiple hypothesis test,
because we simultaneously examine the performance of all funds in the
population (instead of just one fund)." (Barras, Scaillet and Wermers
2010:39 <zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"However, a simple count of significant-alpha funds does not properly
adjust for luck in such a multiple test setting—many of the funds will
have significant estimated alphas by luck alone (i.e., their true alphas
are zero)." (Barras, Scaillet and Wermers 2010:39
<zotero://open-pdf/library/items/4M4MP5EV?page=2>)

""false discoveries"—funds with significant estimated alphas, but zero
true alphas." (Barras, Scaillet and Wermers 2010:39
<zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"This paper implements a new approach to controlling for false
discoveries in such a multiple fund setting." (Barras, Scaillet and
Wermers 2010:39 <zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"Our approach much more precisely estimates (1) the proportions of
unskilled and skilled funds in the population (those with truly negative
and positive alphas, respectively), and (2) their respective locations
in the left and right tails of the cross-sectional estimated alpha (or
estimated alpha t-statistic) distribution." (Barras, Scaillet and
Wermers 2010:39 <zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"One main virtue of our approach is its simplicity: to determine the
frequency of false discoveries, the only parameter needed is the
proportion of zero-alpha funds in the population, π0." (Barras, Scaillet
and Wermers 2010:39 <zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"Rather than arbitrarily impose a prior assumption on π0, as in past
studies, our approach estimates it with a straightforward computation
that uses the p-values of individual fund" (Barras, Scaillet and Wermers
2010:39 <zotero://open-pdf/library/items/4M4MP5EV?page=2>)

"A second advantage of our approach is its accuracy." (Barras, Scaillet
and Wermers 2010:40 <zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"Another important advantage of our approach to multiple testing is its
robustness to cross-sectional dependencies among fund estimated alphas."
(Barras, Scaillet and Wermers 2010:40
<zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"We apply our novel approach to the monthly returns of 2,076 actively
managed U.S. open-end, domestic equity mutual funds that exist at any
time between 1975 and 2006 (inclusive), and revisit several important
themes examined in the previous literature." (Barras, Scaillet and
Wermers 2010:40 <zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"Our decomposition of the population reveals that 75.4% are zero-alpha
funds—funds that have managers with some stock-picking ability, but that
extract all of the rents generated by these abilities through fees.
Further, 24.0% of the funds are unskilled (true 0), while only 0.6% are
skilled (true 0)—the latter α < α > being statistically
indistinguishable from zero." (Barras, Scaillet and Wermers 2010:40
<zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"We also uncover some notable time trends in our study. Specifically, we
observe that the proportion of skilled funds decreases from 14.4% in
early 1990 to 0.6% in late 2006, while the proportion of unskilled funds
increases from 9.2% to 24.0%." (Barras, Scaillet and Wermers 2010:40
<zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"Thus, although the number of actively managed funds dramatically
increases over this period, skilled managers (those capable of picking
stocks well enough, over the long-run, to overcome their trading costs
and expenses) have become exceptionally rare." (Barras, Scaillet and
Wermers 2010:40 <zotero://open-pdf/library/items/4M4MP5EV?page=3>)

"Further analysis indicates that larger and older funds consist of far
more unskilled funds than smaller and newer funds" (Barras, Scaillet and
Wermers 2010:41 <zotero://open-pdf/library/items/4M4MP5EV?page=4>)

"Notably, we show that this luck-controlled strategy outperforms prior
persistence strategies used by Carhart (1997) and others, where constant
top-decile portfolios of funds are chosen with no control for luck."
(Barras, Scaillet and Wermers 2010:41
<zotero://open-pdf/library/items/4M4MP5EV?page=4>)

"We find, on a pre-expense basis, a much higher incidence of funds with
positive alphas— 9.6%, compared to our above-mentioned finding of 0.6%
after expenses. Thus, almost all outperforming funds appear to capture
(or waste through operational inefficiencies) the entire surplus created
by their portfolio managers." (Barras, Scaillet and Wermers 2010:41
<zotero://open-pdf/library/items/4M4MP5EV?page=4>)

"We also observe a large reduction in the proportion of unskilled funds
when we move from net alphas to preexpense alphas (from 24.0% to 4.5%),
indicating a big role for excessive fees (relative to manager
stock-picking skills in excess of trading costs) in underperforming
funds. Although industry sources argue that competition among funds has
reduced" (Barras, Scaillet and Wermers 2010:41
<zotero://open-pdf/library/items/4M4MP5EV?page=4>)

"population of M actively managed mutual funds is composed of three
distinct performance categories, where performance is due to stock
selection skills." (Barras, Scaillet and Wermers 2010:42
<zotero://open-pdf/library/items/4M4MP5EV?page=5>)

"• Unskilled funds: funds that have managers with stock-picking skills
insufficient to recover their trading costs and expenses, creating an
"alpha shortfall" ( 0), α < • Zero-alpha funds: funds that have managers
with stock-picking skills sufficient to just recover trading costs and
expenses ( = 0), and α Skilled funds: funds that have managers with
stock-picking skills sufficient to provide an "alpha surplus," beyond
simply recovering trading costs and expenses ( 0). α >" (Barras,
Scaillet and Wermers 2010:42
<zotero://open-pdf/library/items/4M4MP5EV?page=5>)

"This definition is driven by the idea that consumers search for
actively managed mutual funds that deliver 3 surplus alpha, net of all
expenses." (Barras, Scaillet and Wermers 2010:42
<zotero://open-pdf/library/items/4M4MP5EV?page=5>)

"So, how do we best infer the prevalence of each of the above skill
groups from performance estimates for individual funds? First, we use
the t-statistic ˆt i = ˆα ˆσ as our performance measure, where ˆαi is
the estimated alpha for i/ ˆα i fund i and ˆσ is its estimated standard
deviation— ˆα i" (Barras, Scaillet and Wermers 2010:42
<zotero://open-pdf/library/items/4M4MP5EV?page=5>)

"Second, after choosing a significance level, (e.g., 10%), we observe γ
ˆt t− t+ whether i lies outside the thresholds implied by (denoted by
and ) and γ γ γ label it "significant" if it is such an outlier. This
procedure, simultaneously applied across all funds, is a multiple
hypothesis test (for several null hypotheses, H0, , and alternative
hypotheses, HA, i = 1, M): i, . . . , i" (Barras, Scaillet and Wermers
2010:43 <zotero://open-pdf/library/items/4M4MP5EV?page=6>)

"S+ This proportion, denoted by E( ), is represented by γ the shaded
region in the right tail of the cross-sectional t-distribution (Panel
B)." (Barras, Scaillet and Wermers 2010:44
<zotero://open-pdf/library/items/4M4MP5EV?page=7>)

"The message conveyed by Figure 1 is that we measure performance with a
limited sample of data, and therefore unskilled and skilled funds cannot
easily be distinguished from zero-alpha funds." (Barras, Scaillet and
Wermers 2010:44 <zotero://open-pdf/library/items/4M4MP5EV?page=7>)

"t+ From Panel A, the probability that the observed t-statistic is
greater than = 1.65 equals γ 5% for a zero-alpha fund and 91% for a
skilled fund. Multiplying these two probabilities by the respective
proportions represented by their categories ( and ) gives 5.6%. π0 π A"
(Barras, Scaillet and Wermers 2010:44
<zotero://open-pdf/library/items/4M4MP5EV?page=7>)

"How do we measure the frequency of false discoveries in the tails of
the crosssectional (alpha) t-distribution?" (Barras, Scaillet and
Wermers 2010:45 <zotero://open-pdf/library/items/4M4MP5EV?page=8>)

"At a given significance level , it is clear that γ the probability that
a zero-alpha fund (as defined in the last section) exhibits luck equals
2 (shown as the dark shaded region in Panel A of Figure 1). If the γ /
proportion of zero-alpha funds in the population is π0, the expected
proportion of "lucky funds" (zero-alpha funds with positive and
significant t-statistics) equals + E F = 2. (2) π0 γ / γ" (Barras,
Scaillet and Wermers 2010:45
<zotero://open-pdf/library/items/4M4MP5EV?page=8>)

"One objective of this paper—estimating the proportions of unskilled and
skilled funds in the entire population, and —is achieved π π A A only by
choosing an appropriately large value for . Ultimately, as we increase γ
− + T − T + E( ) and E( ) converge to and , thus minimizing Type II
error γ , π π A A γ γ (failing to locate truly unskilled or skilled
funds)." (Barras, Scaillet and Wermers 2010:45
<zotero://open-pdf/library/items/4M4MP5EV?page=8>)

"Another objective of this paper—determining the location of truly
skilled (or unskilled) funds in the tails of the cross-sectional
t-distribution—can only be achieved by evaluating equations (3) and (4)
at several different values of . γ" (Barras, Scaillet and Wermers
2010:45 <zotero://open-pdf/library/items/4M4MP5EV?page=8>)

"For instance, if the majority of skilled funds lie in the extreme right
tail, then increasing the value of from 0.10 to 0.20 in equation (3)
would result in a very γ T + small increase in E( ), the proportion of
truly skilled funds, because most of γ S+ the additional significant
funds, E( ), would be lucky funds. Alternatively, if γ skilled funds are
dispersed throughout the right tail, then increases in would γ T +
result in larger increases in E( ). γ" (Barras, Scaillet and Wermers
2010:45 <zotero://open-pdf/library/items/4M4MP5EV?page=8>)

"The key to our approach to measuring luck in a group setting, as shown
in equation (2), is the estimator of the proportion of zero-alpha funds
in the population, π0." (Barras, Scaillet and Wermers 2010:46
<zotero://open-pdf/library/items/4M4MP5EV?page=9>)

"Here, we turn to a recent estimation approach developed by Storey
(2002), called the "False Discovery Rate" (FDR) approach. The FDR
approach is very straightforward, as its sole inputs are the (two-sided)
p-values associated with the (alpha) t-statistics of each of the M
funds." (Barras, Scaillet and Wermers 2010:46
<zotero://open-pdf/library/items/4M4MP5EV?page=9>)

"By definition, zero-alpha funds satisfy the null hypothesis, H0, : = 0,
and therefore have αi i 8 p-values that are uniformly distributed over
the interval [0, 1]. On the other hand, p-values of unskilled and
skilled funds tend to be very small because their estimated t-statistics
tend to be far from zero (see Panel A of Figure 1). We can exploit this
information to estimate without knowing the exact π0 distribution of the
p-values of the unskilled and skilled funds." (Barras, Scaillet and
Wermers 2010:46 <zotero://open-pdf/library/items/4M4MP5EV?page=9>)

"To explain further, a key intuition of the FDR approach is that it uses
information from the center of the cross-sectional t-distribution (which
is dominated by zero-alpha funds) to correct for luck in the tails."
(Barras, Scaillet and Wermers 2010:46
<zotero://open-pdf/library/items/4M4MP5EV?page=9>)

"Given the sampled p-values, we estimate as follows. First, we know that
π0 the vast majority of p-values larger than a sufficiently high
threshold, λ" (Barras, Scaillet and Wermers 2010:47
<zotero://open-pdf/library/items/4M4MP5EV?page=10>)

"∗, To select we apply a simple bootstrap procedure introduced by Storey
λ (2002), which minimizes the estimated mean squared error (MSE) of ˆπ
0( λ)" (Barras, Scaillet and Wermers 2010:48
<zotero://open-pdf/library/items/4M4MP5EV?page=11>)

"Although the main advantage of this procedure is ∗) that it is entirely
data driven, we find that ˆπ 0( is not overly sensitive to λ ∗. the
choice of λ" (Barras, Scaillet and Wermers 2010:48
<zotero://open-pdf/library/items/4M4MP5EV?page=11>)

"∗, where is a sufficiently high significance level—similar to the
choice of γ λ we select with a bootstrap procedure that minimizes the
estimated MSE of γ − + ˆπ and ˆπ ( A A" (Barras, Scaillet and Wermers
2010:48 <zotero://open-pdf/library/items/4M4MP5EV?page=11>)

"The "full luck" approach" (Barras, Scaillet and Wermers 2010:48
<zotero://open-pdf/library/items/4M4MP5EV?page=11>)

"The MSE is the expected squared difference between ˆπ 0( λ) and the
true value, : π0 2. MSE( ˆπ0( λ)) E( ˆπ0( λ) π0) Because is unknown, it
is proxied with minλ ˆπ 0( λ) to compute π0 the estimated MSE (see
Storey (2002))." (Barras, Scaillet and Wermers 2010:48
<zotero://open-pdf/library/items/4M4MP5EV?page=11>)

"proposed by Jensen (1968) and Ferson and Qian (2004) assumes, a priori,
that all funds in the population have zero alphas ( 1). Thus, for a
given signifi- π0 cance level, , this approach implies an estimate of
the proportions of unlucky γ and lucky funds equal to 2.11 γ /" (Barras,
Scaillet and Wermers 2010:49
<zotero://open-pdf/library/items/4M4MP5EV?page=12>)

"At the other extreme, the "no luck" approach reports the observed
number of significant funds (for instance, Ferson and Schadt (1996))
without making a correction for luck ( 0). π0" (Barras, Scaillet and
Wermers 2010:49 <zotero://open-pdf/library/items/4M4MP5EV?page=12>)

"Specifically, Panel A of Figure 3 compares the three estimators of the
expected F − proportion of unlucky funds. The true population value, E(
), is an increasing γ function of by construction, as shown by equation
(2). Although the average π0 F − value of the FDR estimator closely
tracks E( ), this is not the case for the γ other two approaches."
(Barras, Scaillet and Wermers 2010:49
<zotero://open-pdf/library/items/4M4MP5EV?page=12>)

"By assuming that γ0, the no luck approach consis- π0 F − tently
underestimates E( ) when the true proportion of zero-alpha funds is γ
higher ( 0). Conversely, the full luck approach, which assumes that 1,
π0 > π0 F − overestimates E( ) when 1. π0 < γ" (Barras, Scaillet and
Wermers 2010:49 <zotero://open-pdf/library/items/4M4MP5EV?page=12>)

"Because ˆπ0 is a proportion estimator that depends on the ∗, proportion
of p-values higher than the Law of Large Numbers drives it close λ to
its true value with our large sample size." (Barras, Scaillet and
Wermers 2010:51 <zotero://open-pdf/library/items/4M4MP5EV?page=14>)

"An important advantage of our approach is that we estimate the p-value
of each fund in isolation, avoiding the complications that arise because
of the dependence structure of fund residuals." (Barras, Scaillet and
Wermers 2010:51 <zotero://open-pdf/library/items/4M4MP5EV?page=14>)

"However, high cross-sectional dependencies could potentially bias our
estimators." (Barras, Scaillet and Wermers 2010:51
<zotero://open-pdf/library/items/4M4MP5EV?page=14>)

"In our sample, we are not overly concerned with dependencies because we
find that the average correlation between four-factor model residuals of
pairs of funds is only 0.08." (Barras, Scaillet and Wermers 2010:52
<zotero://open-pdf/library/items/4M4MP5EV?page=15>)

"In all simulations, we find both that average estimates (for all of our
estimators) are very close to their true values, and that confidence
intervals for estimates are comparable to those that result from
simulations where independent residuals are assumed." (Barras, Scaillet
and Wermers 2010:52 <zotero://open-pdf/library/items/4M4MP5EV?page=15>)

"To compute each fund t-statistic, we use the Newey and West (1987)
heteroskedasticity and autocorrelation consistent estimator of the
standard deviation, ˆσ ˆα . i" (Barras, Scaillet and Wermers 2010:53
<zotero://open-pdf/library/items/4M4MP5EV?page=16>)

"Further, KTWW find that the finite-sample distribution of the is
nonnormal for approximately half of the funds." (Barras, Scaillet and
Wermers 2010:53 <zotero://open-pdf/library/items/4M4MP5EV?page=16>)

"The reader is referred to KTWW for details on this bootstrap
procedure." (Barras, Scaillet and Wermers 2010:53
<zotero://open-pdf/library/items/4M4MP5EV?page=16>)

"We use monthly mutual fund return data provided by the CRSP between
January 1975 and December 2006 to estimate fund alphas." (Barras,
Scaillet and Wermers 2010:53
<zotero://open-pdf/library/items/4M4MP5EV?page=16>)

"Among the 2,076 funds, we estimate that the majority—75.4%—are
zeroalpha funds. Managers of these funds exhibit stock-picking skills
just sufficient to cover their trading costs and other expenses
(including fees). These funds, therefore, capture all of the economic
rents that they generate, consistent with the long-run prediction of
Berk and Green (2004)." (Barras, Scaillet and Wermers 2010:55
<zotero://open-pdf/library/items/4M4MP5EV?page=18>)

"Further, it is quite surprising that the estimated proportion of
skilled funds is statistically indistinguishable from zero (see
"Skilled" column). This result may seem surprising in light of prior
studies, such as Ferson and Schadt (1996), which find that a small group
of top mutual fund managers appear to outperform their benchmarks, net
of costs. However, a closer examination—in Panel between our study and
prior research. B—shows that our adjustment for luck is key in
understanding the difference" (Barras, Scaillet and Wermers 2010:55
<zotero://open-pdf/library/items/4M4MP5EV?page=18>)

"It is interesting (Panel A) that 24% of the population (499 funds) are
truly unskilled fund managers, unable to pick stocks well enough to
recover their trading costs and other expenses." (Barras, Scaillet and
Wermers 2010:55 <zotero://open-pdf/library/items/4M4MP5EV?page=18>)

"out-of-sample skills. will use this finding in our next section, where
we attempt to find funds with p-values). We t-statistics (extremely low
γcause they have extremely high Thus, skilled fund managers, while rare,
may be somewhat easy to find" (Barras, Scaillet and Wermers 2010:61
<zotero://open-pdf/library/items/4M4MP5EV?page=24>)

"The BG model implies that larger and older funds should exhibit lower
alphas because they have presumably grown (or survived) to the point
where they provide no superior alphas, net of fees—partly due to flows
that followed past superior performance. Smaller and newer funds, on the
other hand, may exhibit some skills before investors learn about their
superior abilities." (Barras, Scaillet and Wermers 2010:61
<zotero://open-pdf/library/items/4M4MP5EV?page=24>)

"Perhaps more directly, the BG model also implies that flows should
disproportionately move to truly skilled funds, and that these funds
should exhibit the largest reduction in future skills." (Barras,
Scaillet and Wermers 2010:62
<zotero://open-pdf/library/items/4M4MP5EV?page=25>)

"of the truly skilled funds. in this extreme tail, we stand a greater
chance of capturing the superior alphas are located in the extreme right
tail. By forming portfolios containing all funds Nonetheless, the reader
should recall from the last section that skilled funds" (Barras,
Scaillet and Wermers 2010:63
<zotero://open-pdf/library/items/4M4MP5EV?page=26>)

"The FDR+ is defined as the expected proportion of lucky funds included
in the γ portfolio at the significance level γ" (Barras, Scaillet and
Wermers 2010:63 <zotero://open-pdf/library/items/4M4MP5EV?page=26>)

"When we set a + low FDR target, we allow only a small proportion of
lucky funds (false discoveries) in the chosen portfolio." (Barras,
Scaillet and Wermers 2010:63
<zotero://open-pdf/library/items/4M4MP5EV?page=26>)

"FDR+ Our new measure, , is an extension of the traditional FDR
introduced in the statis- γ tical literature (e.g., Benjamini and
Hochberg (1995), Storey (2002)) because the latter does not distinguish
between bad and good luck. The traditional measure is FDR E(F Sγ ),
where / γ γ F+ F− S+ S− F S . , γ γ γ γ γ γ" (Barras, Scaillet and
Wermers 2010:63 <zotero://open-pdf/library/items/4M4MP5EV?page=26>)

"+ Conversely, increasing the FDR target has two opposing effects on a
portfolio: It decreases the portfolio expected future performance
because the proportion of lucky funds in the portfolio is higher, and it
increases the portfolio diversification because more funds are selected—
reducing the volatility of the out-of-sample performance." (Barras,
Scaillet and Wermers 2010:64
<zotero://open-pdf/library/items/4M4MP5EV?page=27>)

"Besides its financial interpretation, the FDR also has a natural
statistical meaning, as it is the extension of the Type I error (i.e.,
rejecting the null, H0, when it is correct) from single to multiple
hypothesis testing. In the single case, the Type I error is controlled
by using the significance level (i.e., the size of the test). In the
multiple case, we replace with the FDR, which is a compound γ γ Type I
error measure. In both cases, we face a similar trade-off: In order to
increase power, we have to increase or the FDR, respectively (see the
survey of Romano, Shaikh, and Wolf (2008)). γ" (Barras, Scaillet and
Wermers 2010:64 <zotero://open-pdf/library/items/4M4MP5EV?page=27>)

"As a result, the signal used to form portfolios is likely to be noisier
than our FDR approach." (Barras, Scaillet and Wermers 2010:67
<zotero://open-pdf/library/items/4M4MP5EV?page=30>)

"Over most years, the FDR approach performs much better, consistent with
the idea that it much more precisely detects skilled funds. However,
this performance advantage declines during later years, when the
proportion of skilled funds decreases substantially, making them much
tougher to locate. Therefore, we find that the superior performance of
the FDR portfolio is tightly linked to the prevalence of skilled funds
in the population." (Barras, Scaillet and Wermers 2010:67
<zotero://open-pdf/library/items/4M4MP5EV?page=30>)

"In the right tail, we find that 9.6% of fund managers have
stock-picking skills sufficient to more than compensate for trading
costs (Panel A)." (Barras, Scaillet and Wermers 2010:68
<zotero://open-pdf/library/items/4M4MP5EV?page=31>)

"Finally, in results included in the Internet Appendix, we find that the
proportion of pre-expense skilled funds in the population decreases from
27.5% at 1996 to 9.6% at 2006. This implies that the decline in
net-expense skills noted in Figure 4 is driven mostly by a reduction in
stockpicking skills over time (as opposed to an increase in expenses for
pre-expense skilled funds)." (Barras, Scaillet and Wermers 2010:70
<zotero://open-pdf/library/items/4M4MP5EV?page=33>)

"In this paper, we apply a new method for measuring the skills of fund
managers in a group setting. Specifically, the FDR approach provides a
simple and straightforward method to estimate the proportion of skilled
funds (those with a positive alpha, net of trading costs and expenses),
zero-alpha funds, and unskilled funds (those with a negative alpha) in
the entire population." (Barras, Scaillet and Wermers 2010:73
<zotero://open-pdf/library/items/4M4MP5EV?page=36>)

"Further, we use these estimates to provide accurate counts of skilled
funds within various intervals in the right tail of the cross-sectional
alpha distribution, as well as unskilled funds within segments of the
left tail." (Barras, Scaillet and Wermers 2010:73
<zotero://open-pdf/library/items/4M4MP5EV?page=36>)

"We apply the FDR technique to show that the proportion of skilled fund
managers has diminished rapidly over the past 20 years, while the
proportion of unskilled fund managers has increased substantially."
(Barras, Scaillet and Wermers 2010:73
<zotero://open-pdf/library/items/4M4MP5EV?page=36>)

"Most actively managed funds provide either positive or zero
net-ofexpense alphas, putting them at least on par with passive funds."
(Barras, Scaillet and Wermers 2010:73
<zotero://open-pdf/library/items/4M4MP5EV?page=36>)

"Although our paper focuses on mutual fund performance, our approach has
potentially wide applications in finance. It can be used to control for
luck in any setting in which a multiple hypothesis test is run and a
large sample is available." (Barras, Scaillet and Wermers 2010:74
<zotero://open-pdf/library/items/4M4MP5EV?page=37>)

"With our approach, controlling for luck in multiple testing is trivial:
The only input required is a vector of p-values, one for each individual
test." (Barras, Scaillet and Wermers 2010:74
<zotero://open-pdf/library/items/4M4MP5EV?page=37>)