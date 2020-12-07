---
aliases: "Ardia & Boudt (2018)"
---

Ardia, David, and Kris Boudt. “The Peer Performance Ratios of Hedge Funds.” Journal of Banking & Finance 87 (February 2018): 351–68. https://doi.org/10.1016/j.jbankfin.2017.10.014.

---

### From the abtract, I see two key results.

> We show that the p–values of the pairwise tests of equal performance can be used to obtain estimates of the outperformance and underperformance ratio that are robust to false discoveries – estimated alpha differentials for which the significance test has a low p–value while the true alpha is identical.

1. We have a methodology that is robust to false discovery
2. They proposed a closed-form non parametric approach vs. the bootstrap approach of Barras et al. (2010)

> When applied to hedge funds, we find that ranking funds on the outperformance ratio leads to a top quintile portfolio with a higher absolute and risk–adjusted performance than when the estimated alpha is used.

2. They can select a better portfolio than just ranking by alpha

### Initial comprehension from skimming the text:

##### Structure
* Intro
* Methodology
	* Definitions
	* Existing estimators
	* Proposed estimator
	* Equal performance ratio
	* Out and under performance ratios
	* Simulated data
* Empirical results
	* Application to hefge funds
		* Data description
		* Cross-section
		* Traditional rank-based evaluation
		* Gains from proposed method out-of-sample
		* Alternative peer performance measures
			* What are they?
		* Determinant of peer performance
		* Funds characteristics and over/underestimation
* Conclusion

##### From skimming the paper, I got a few things to note.
* Comparison of methods | existing and proposed
* Calculations of 3 type of ratios | how are they defined?
* Application to hedge funds
* Intro and conclusion mention Barras et. al (2010)
	* Important paper to read to understand methodology
* This paper does not bring new theory. It is an application of methodology

### Questions to answer when I read more in details

What I understand from this paper:

* Rank-based peer performance over/underestimate performance as it doesn't take into account equal-performance
* Pairwise t-test also generate false positives and false negatives
* Proposed methodology corrects for false positives and false negatives become neglible at a certain point
* The proposed methodology outperform the other two in monte carlo and in empirical application

What I don't understand:

* The formulas relating to the ratios and quantiles
	* Would need to reread and illustrate the maths
* What is [[pairwise statistics]]?
* What is [[Multiple hypothesis testing]]?

What are the key results in my own words:

* The FDR method can correct for false discovery and can complement the tools for fund selection

What do I need to research more on:

* Is there a better method?
* Is there other papers using that method in term of application for finance?
* How can I understand the methodology better?
* How can I explain the methodology to someone else?

What are the related papers:

Need to read Barras et al (2010) for sure and Storey (2002)

![[Pasted image 20201118132133.png]]

---

## Abstract: 
We define the outperformance (resp. underperformance) of an investment fund as the percentage of funds in the peer universe for which the true performance of the focal fund is higher (resp. lower). We show that the p–values of the pairwise tests of equal performance can be used to obtain estimates of the outperformance and underperformance ratio that are robust to false discoveries – estimated alpha differentials for which the significance test has a low p–value while the true alpha is identical. When applied to hedge funds, we find that ranking funds on the outperformance ratio leads to a top quintile portfolio with a higher absolute and risk–adjusted performance than when the estimated alpha is used.

##### Keywords: False discoveries, hedge fund, multiple hypothesis testing, peer performance, performance measurement

*Extracted Annotations (11/16/2020, 12:50:04 PM)*

"In their pioneer study, Barras et al. (2010) show how to accurately
estimate the portion of true positive alpha funds in the universe. Their
estimation approach exploits the properties of the discovery rate
approach of Storey (2002) to avoid the common pitfall of also
associating positive alpha to zero-alpha funds with a significant
estimated positive alpha." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"the traditional approach to peer performance evaluation is to rank
funds based on their estimated alpha, and then use the percentile ranks
to classify peer performance as outperformance or underperformance. By
construction, this approach ignores the possibility that funds in the
peer group can have the same alpha, and thus tends to overestimate the
outperformance and underperformance." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"Since institutional and retail investors tend to increase their
portfolio allocation to outperforming funds (see, e.g., Fung et al.,
2008), accounting for the presence of equal alpha among funds in the
peer group is of crucial importance to avoid false discoveries and
inefficient capital allocation." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"In this paper, we recommend evaluating peer performance of a fund using
three peer performance parameters, for which we propose a non-parametric
estimator that controls for false discoveries." (Ardia and Boudt
2018:352 <zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"the traditional approach of counting the percentage of estimated
positive and negative alpha-differentials does not test whether the
differences are statistically significant. It implicitly assumes to be
zero and thus overestimates 0 + i i and . i" (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"The alternative approach of counting the percentage of significant
positive and negative alphadifferentials relies on the estimated
standard errors and the marginal distribution of t-statistics to account
for the estimation error in a single pairwise test of equal performance.
It however does not control for the false positives in the multiple
hypothesis setup of testing the difference between the focal fund's
alpha against all other peer funds." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"In practice, because of the small sample size in fund performance
evaluation, there is also a problem of false negatives due to the lack
of power of the t-test." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"The solution that we provide in this paper is designed to account for
these false discoveries. The proposed estimators of the peer performance
parameters, called peer performance ratios, are obtained in two steps."
(Ardia and Boudt 2018:352 <zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"We first take a frequentist approach to compute, for each of the peer
funds, the p-value of the null n hypothesis that the alpha of the peer
fund equals the alpha of the fund considered. False discoveries occur
when, in the resulting sample of p-values, there are small p-values for
funds with equal alpha." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"As shown by Storey (2002), Barras et al. (2010) and Bajgrowicz and
Scaillet (2012), we can then exploit the distribution of p-values under
the null hypothesis to obtain a reliable estimate of the peer
performance ratios that is robust to the presence of false discoveries
in the first-stage sample of p-values." (Ardia and Boudt 2018:352
<zotero://open-pdf/library/items/QWS5VFMA?page=2>)

"Alternatively, one could achieve robustness to false discoveries using
the bootstrap techniques of Kosowski et al. (2005), Fama and French
(2010), and Ferson and Chen (2015), or the parametric approach of Chen
et al. (2017). The bootstrap requires comparing the obtained
alpha-differential with artificially generated data samples where the
variation in fund performance is due entirely to sample variability.
Under the parametric setup of Chen et al. (2017), peer performance
ratios could be obtained by modeling the alphadifferential as a
realization from a mixture of normal distributions." (Ardia and Boudt
2018:353 <zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"Both the bootstrap and parametric approaches have the disadvantage of
being computationally demanding. In contrast, our non-parametric
approach has an explicit form and is thus simple to implement." (Ardia
and Boudt 2018:353 <zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"calculating the peer performance ratios on monthly net returns observed
over five-year rolling samples for a period ranging from January 2000 to
June 2014." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"We find that, for the majority of hedge funds, there is a large
proportion of funds with equal performance." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"Therefore, on average, the standard approach for estimating peer
performance using percentile ranks overestimates the outperformance and
underperformance. For our sample of hedge funds, the average difference
between the percentile-rank approach and the proposed estimator is
around 33 percentage points." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"The peer performance ratios have predictive value for future fund
performance, and this predictive value is incremental to the information
contained in alternative performance measures." (Ardia and Boudt
2018:353 <zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"These predictive regressions indicate that selecting funds using the
outperformance ratio yields a portfolio with both a higher return and a
higher risk-adjusted excess return. Importantly, this result is robust
to adding other performance measures as predictors, as well as
controlling for a host of other influences." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"In particular, we find that when a fund has more assets under
management, the outperformance ratio tends to be lower and, for two
funds with the same age, the underperformance ratio is higher." (Ardia
and Boudt 2018:353 <zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"Altogether, the empirical results strongly support our view that,
within a peer group, there is often an important proportion of hedge
funds that have the same alpha." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"Ignoring this fact leads to false discoveries in terms of
overestimating both the percentage of peers that the fund outperforms
and that it underperforms. The proposed peer performance ratios are
designed to avoid this problem." (Ardia and Boudt 2018:353
<zotero://open-pdf/library/items/QWS5VFMA?page=3>)

"In this study, we measure the peer performance of a focal fund i
belonging to a peer universe of n + 1 funds using three peer performance
parameters: (i) : the proportion of funds in the peer group that perform
0 i equally well as fund i, (ii) : the proportion of funds in the peer
group that are outperformed by fund i, + i and (iii) the proportion of
funds in the peer group that outperform fund i. i" (Ardia and Boudt
2018:354 <zotero://open-pdf/library/items/QWS5VFMA?page=4>)

"Two major strengths of the proposed peer performance ratios are that
they require the relative performance between two funds to cross a
threshold of statistical significance to be counted as evidence of a
difference in performance, and that the false discovery rate methodology
is used to obtain peer performance estimates that are robust to false
positives." (Ardia and Boudt 2018:354
<zotero://open-pdf/library/items/QWS5VFMA?page=4>)

"The risk-adjusted performance of a fund is typically estimated by the
intercept of the least squares regression of the fund returns on a
series of risk factors, such as the four Carhart factors or the seven
Fung and Hsieh hedge fund risk factors (Carhart, 1997; Fung and Hsieh,
2004)" (Ardia and Boudt 2018:354
<zotero://open-pdf/library/items/QWS5VFMA?page=4>)

"A test for equal performance of two funds i and is obtained by testing
the significance of the estimated intercept of the ordinary least
squares j (OLS) regression of on : (ri;t rj;t ) ft 0 (1) (ri;t rj;t ) =
ij + ijft + "ij;t ;" (Ardia and Boudt 2018:354
<zotero://open-pdf/library/items/QWS5VFMA?page=4>)

"be compute its standard error using the heteroscedasticity and
autocorrelation robust (HAC) standard ij error estimators of Andrews
(1991) and Andrews and Monahan (1992)." (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"error estimators of Andrews (1991) and Andrews and Monahan (1992). is
higher, the evidence against the of equal performance is greater. The
p-values are then defined as two H0 bij times the (estimated)
probability integral transform of minus the absolute value of under : H0
b bij Fij (jbij 2 j) ; b bij where is a consistent estimate of the true
cumulative distribution function of under . In Fij Fij H0 b 5 our
application, we set to the standard normal cumulative distribution. Fij
b bij ij ij = be bij as the studentized test statistic such that when
the absolute value of We denote " (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"First, let us look at the percentile-rank estimation approach, which
estimates the outperformance ratio as the + i percentage of funds for
which the estimated performance of the focal fund is higher: X 1 (2) + I
f b 0g ; ij i n j 6=i b" (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"Clearly, the percentile-rank approach , for all i), 0 = 0 i and thus
overestimating the percentage of outand underperformance. b has the
disadvantage of implicitly setting the percentage of equal performance
to zero (" (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"A second simple but biased estimator of the outperformance ratio is the
percentage of funds for + i bij bij which the estimated test statistic
exceeds the (estimated) -quantile of the distribution of under + + b the
null hypothesis, which is denoted by . Typical values for are 90% and .
The corresponding + 95% ij estimator is then: X 1 + b I fbij b (3) + g :
i ij n j 6=i" (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"Both the outperformance ratio estimates obtained using the
percentile-rank and pairwise significance tests are characterized by a
potentially large number of false positives (i.e., detected instances of
outperformance when in fact there is equal-performance or
underperformance) and false negatives" (Ardia and Boudt 2018:355
<zotero://open-pdf/library/items/QWS5VFMA?page=5>)

"For the percentile-rank approach in (2) and (5), we expect that for
most funds, the number of false positives exceeds the number of false
negatives, and thus that the estimated outperformance is overestimated.
In case of the significance testing approach in (3) and (6), the balance
depends on the underlying return generating process and the probability
level used for testing. As can be seen in (6), we have that, for lower
values of + + b the critical value , there are more false positives, and
less false negatives. This approach accounts for the ij estimation error
in the setting of pairwise testing, but not the joint hypothesis of
testing equal-performance with the peer funds." (Ardia and Boudt
2018:356 <zotero://open-pdf/library/items/QWS5VFMA?page=6>)

"We thus need an estimator for the outperformance ratio that is robust
to false positives under a framework of multiple hypothesis testing. As
a solution, it might be tempting to use a sequence of multiple
hypothesis tests, such as Hotelling's T2 test of equality of Sharpe
ratios, with family-wise error rate control 6 of Type I errors over the
sequence of tests. The disadvantage of those multiple tests is that
their applicability to our problem is reduced when the number of peer
funds is large. The standard setup requires that the time series is
available for the same period for all funds, which limits the number of
observations to the time span of the fund with the shortest history."
(Ardia and Boudt 2018:356 <zotero://open-pdf/library/items/QWS5VFMA?page=6>)

"The estimator we propose combines the advantages of pairwise and
multiple testing in a two-step estimation procedure." (Ardia and Boudt
2018:356 <zotero://open-pdf/library/items/QWS5VFMA?page=6>)

"For each fund, we first estimate the percentage of peer funds with
equal performance in an unbiased manner using only pairwise tests of
equal performance between the focal fund and a peer bij fund. After
performing this procedure for each potential pair, a sample of p-values
associated with a two-sided test of the null hypothesis , for , , is
obtained. H0 : ij = 0 j = 1; : : : ; n + 1 j 6= i" (Ardia and Boudt
2018:356 <zotero://open-pdf/library/items/QWS5VFMA?page=6>)

"For fixed i, the distribution of the p-values is (asymptotically) a
mixture of p-values that are uniformly distributed (the" (Ardia and
Boudt 2018:356 <zotero://open-pdf/library/items/QWS5VFMA?page=6>)

"pairs for which the null hypothesis is correct) and p-values that are
close to zero (when the null hypothesis is false)." (Ardia and Boudt
2018:357 <zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"This key insight is provided by Storey (2002) and it is used by Barras
et al. (2010) to estimate the proportion of funds that perform equally
well in the same manner as a passive investor in style indices." (Ardia
and Boudt 2018:357 <zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"A crucial feature of the proposed peer performance ratios is that they
exploit the difference in the bij distribution of the p-values when
versus . ij = 0 ij = 0" (Ardia and Boudt 2018:357
<zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"If the test is sufficiently powerful, a threshold value exists such
that almost surely the p-value of the i two-sided equal-performance test
is less than if the two funds have different performances: i P[bij (7)
(A1) : < i j ij 6= 0] = 1 :" (Ardia and Boudt 2018:357
<zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"The validity of this assumption depends on the magnitude of , the test
statistic itself, the calculation of ij its p-value (e.g., asymptotic
versus bootstrap methods), and the sample size." (Ardia and Boudt
2018:357 <zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"iz In the case of equal performance, and provided that the estimated
coincides with the true Fij Fij used to calculate the p-value, the
p-value is uniformly distributed for a given pair . This implies that
(i; j ) bij the probability of exceeding when is : i ij = 0 1 i P[bij
(8) (A2) : i j ij = 0] = 1 i :" (Ardia and Boudt 2018:357
<zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"A key result related to the definition of the proposed
equal-performance ratio is that under and (A1) , the expected number of
p-values exceeding is , with the number of peer funds that (A2) i (1 i
)n 0 n 0 i i perform equally well as the focal fund" (Ardia and Boudt
2018:357 <zotero://open-pdf/library/items/QWS5VFMA?page=7>)

"Hence, a natural estimator for is the number of estimated p-values
exceeding divided by : n 0 i 1 i i P I f bij i g j 6=i bn (9) 0 c 0 min
; n ; i i 1 i" (Ardia and Boudt 2018:358
<zotero://open-pdf/library/items/QWS5VFMA?page=8>)

"The practical computation of the equal-performance ratio thus requires
us to choose the threshold value . The larger the value of , the more
likely it is that assumptions (A1) and (A2) are satisfied, but the i i
fewer observations enter the summation used to estimate the
equal-performance ratio in (9)-(10). We address this bias-variance
trade-off in the estimation of by optimizing the choice of based on a
data- 0 i i driven approach to determine the value of which minimizes
the estimated mean i 2 f0:3; 0:32; : : : ; 0:7g b squared estimation
error of . 0 i" (Ardia and Boudt 2018:358
<zotero://open-pdf/library/items/QWS5VFMA?page=8>)

"bn Given the estimate of the number of peer funds with equal
performance , and the observed perfor- 0 i mance , we then estimate the
number of funds that are outperformed by the focal fund i, ij , and
those that outperform fund i, . The attribution is based on the number
of significant performance n + n i i b b ij ij = be bij ) and an
adjustment for false discoveries. differences (using the studentized
test statistic differences" (Ardia and Boudt 2018:358
<zotero://open-pdf/library/items/QWS5VFMA?page=8>)

"We start the estimation procedure on the side for which we have most
observations." (Ardia and Boudt 2018:358
<zotero://open-pdf/library/items/QWS5VFMA?page=8>)

"bn First, given , 0 i bn bn we can infer that the number of false
positives is if . As is an unbiased estimate of 0i (1 + ) ij = 0 0 i ij
0i (1 i . = 0 an unbiased estimate for the false discoveries when ) bn ,
so is n + 0" (Ardia and Boudt 2018:359
<zotero://open-pdf/library/items/QWS5VFMA?page=9>)

"In the application, we set to avoid + = 0:4 the false negatives and to
avoid the false positives. = 0:6" (Ardia and Boudt 2018:359
<zotero://open-pdf/library/items/QWS5VFMA?page=9>)

"we obtain the following natural definitions of the outperformance and
underperformance ratios of fund i: nP o ( P + I fbij b bn 1 if max g 0 i
(1 + ); 0 I f b 0g n=2 ij b j 6=i ij j 6=i n + i b b otherwise 1 0 ; i i
and: nP o ( P I fbij b bn 1 if max g 0 i ; 0 I f b 0g < n=2 ij b j 6=i
ij j 6=i n i b b otherwise 1 0 + : i i" (Ardia and Boudt 2018:359
<zotero://open-pdf/library/items/QWS5VFMA?page=9>)

"It is important to note that, compared to the approach of counting the
significant alpha-differential estimates in (3), the outperformance and
underperformance ratios explicitly correct for the presence of false
positives bn bn by subtracting the terms and , respectively. 0i (1 + ) 0
i" (Ardia and Boudt 2018:359
<zotero://open-pdf/library/items/QWS5VFMA?page=9>)

"We now perform a Monte Carlo study to compare the finite sample bias of
the proposed peer performance ratios with the alternative, more simple
percentile-rank and significance test-based estimates discussed in
Section 2.1." (Ardia and Boudt 2018:360
<zotero://open-pdf/library/items/QWS5VFMA?page=10>)

"Our universe consists of the active and dead U.S. hedge funds included
in the Hedge Fund Research (HFR) database as of July 2014. To account
for the time-variation in the distribution of the hedge funds' alpha, we
use rolling five-year estimation windows of monthly hedge fund net
returns and factor data over 2014.12 the period 2000- This thus leads to
39 estimation dates and a total of 15,370 funds." (Ardia and Boudt
2018:361 <zotero://open-pdf/library/items/QWS5VFMA?page=11>)

"We define the peer group as the set of hedge funds following the same
investment style (Equity Hedge, Event-Driven, Macro, and Relative
Value). As the pairwise peer performance measure, we use the
alphadifferential obtained as the intercept in the linear factor model
in (1), estimated using the nine risk factors constituting the union of
the four factors in Carhart (1997) and the seven factors in Fung and
Hsieh 13 (2004). The p-values are computed using heteroscedasticity and
autocorrelation robust standard error estimators (Andrews, 1991; Andrews
and Monahan, 1992)." (Ardia and Boudt 2018:361
<zotero://open-pdf/library/items/QWS5VFMA?page=11>)

"We can see that, although the alpha and the outperformance ratio are
strongly positively dependent, the relationship is highly nonlinear. We
find for instance that a decrease of the fund's alpha by ten percentage
points has a substantially larger impact on the outperformance ratio for
a top alpha performing fund than for a middle alpha performing fund."
(Ardia and Boudt 2018:363
<zotero://open-pdf/library/items/QWS5VFMA?page=13>)

"We can thus b interpret the difference between the traditional
rank-based estimate of the fund's outperformance and as + i a proxy for
the degree of overestimation in the traditional estimator" (Ardia and
Boudt 2018:363 <zotero://open-pdf/library/items/QWS5VFMA?page=13>)

"In practice, we expect that the percentile-rank b b approach
overestimates both the outperformance and the underperformance, and thus
that and are + i i positive." (Ardia and Boudt 2018:363
<zotero://open-pdf/library/items/QWS5VFMA?page=13>)

"b On average, equals 32.28%, + i which indicates that, compared to the
proposed outperformance ratio, the percentile-rank based approach
overestimates outperformance by an average of 32.28 percentage points.
Similarly, in the right plot, we can see that, compared to the
underperformance ratio, the percentile-rank approach significantly
overestimates underperformance by an average of 33.20 percentage
points." (Ardia and Boudt 2018:364
<zotero://open-pdf/library/items/QWS5VFMA?page=14>)

"Overall, we find that the outperformance ratio is effectively able to
select the top performing hedge funds." (Ardia and Boudt 2018:365
<zotero://open-pdf/library/items/QWS5VFMA?page=15>)

"In practice, we recommend to use the outperformance ratio in
combination with other predictors of (risk-adjusted) fund performance.
This advice follows from our finding that the outperformance ratio has
incremental predictive value when included in multivariate regressions."
(Ardia and Boudt 2018:367
<zotero://open-pdf/library/items/QWS5VFMA?page=17>)

"Therefore, the bottom line recommendation of the analysis is to account
for false discoveries in peer performance and use the proposed triplet
of peer performance ratios: b b b and . + ; ; 0 i i i" (Ardia and Boudt
2018:370 <zotero://open-pdf/library/items/QWS5VFMA?page=20>)

"Inspired by Barras et al. (2010), we argue that the workhorse approach
of evaluating peer performance by simply ranking funds on their
estimated alpha is prone to suffer from false discoveries: detection of
outperformance or underperformance when in reality the funds have the
same performance." (Ardia and Boudt 2018:370
<zotero://open-pdf/library/items/QWS5VFMA?page=20>)

"We propose a closed-form non-parametric estimator for the corresponding
equal-, out-, and underperformance ratios." (Ardia and Boudt 2018:370
<zotero://open-pdf/library/items/QWS5VFMA?page=20>)

"We show that percentile-rank analyses of outand underperformance
overestimate the outperformance of the funds with a relatively good
ranking and overestimate the underperformance of the funds with a worse
ranking." (Ardia and Boudt 2018:371
<zotero://open-pdf/library/items/QWS5VFMA?page=21>)

"An extensive out-of-sample evaluation illustrates the economic value of
controlling for false discoveries when using the fund's outperformance
ratio rather than the fund's alpha for constructing top quintile
investment portfolios." (Ardia and Boudt 2018:371
<zotero://open-pdf/library/items/QWS5VFMA?page=21>)

"life-cycle theory of Berk and Green (2004) and Getmansky (2012)."
(Ardia and Boudt 2018:371
<zotero://open-pdf/library/items/QWS5VFMA?page=21>)

"We thus find the peer performance ratios to be a useful addition to the
battery of performance statistics used by investors." (Ardia and Boudt
2018:371 <zotero://open-pdf/library/items/QWS5VFMA?page=21>)

"The proposed peer performance screening plots are useful for both
ex-ante selection of funds and ex-post evaluation of their relative
performance." (Ardia and Boudt 2018:371
<zotero://open-pdf/library/items/QWS5VFMA?page=21>)

"This figure presents the concept of screening plot. The left plot
displays the average (annualized) monthly alpha for hedge funds ranked
by decreasing alpha and grouped in 50 buckets. The right plot displays,
for each of the 50 buckets, the average of the outperformance (black),
equal-performance (light gray), and underperformance (dark gray) ratios
of the hedge funds belonging to that bucket based on sorting on alpha."
(Ardia and Boudt 2018:381
<zotero://open-pdf/library/items/QWS5VFMA?page=31>)