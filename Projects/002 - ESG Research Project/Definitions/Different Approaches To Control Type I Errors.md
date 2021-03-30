Link: https://www.gs.washington.edu/academics/courses/akey/56008/lecture/lecture10.pdf
![[lecture10.pdf]]
Related: [[False Rate Discovery]], [[Type I and type II errors]]
Tags: #stats 

---

## Different Approaches To Control Type I Errors

* Per comparison error rate (PCER): the expected value of the number of Type I errors over the number of hypotheses,  
	* PCER = E(V)/m
* Per-family error rate (PFER): the expected number of Type I errors,
	* PFE = E(V).
* Family-wise error rate: the probability of at least one type I error
	* FEWR = P(V ≥1)
* False discovery rate (FDR) is the expected proportion of Type I errors among the rejected hypotheses
	* FDR = E(V/R | R>0)P(R>0)
* Positive false discovery rate (pFDR): the rate that [[discoveries]] are false
	* FDR = E(V/R | R > 0)

### False discovery rate
False discovery rate (FDR) is designed to control the proportionof false positives among the set of rejected hypotheses (R)

* Under the null hypothesis p-values are expected to be uniformly distributed between 0 and 1
* Under thealternative hypothesis p-values are skewed towards 0
* Combined distribution is a mixture of p-values from the null and alternative hypotheses
* For p-values greater than say 0.5, we can assume theymostlyrepresent observations from the null hypothesis

![[Pasted image 20201116144408.png]]

[[Barras_Scaillet_Wermers_2010_False_Discoveries_in_Mutual_Fund_Performance]]

> Besides its financial interpretation, the FDR also has a natural statistical meaning, as it is the extension of the Type I error (i.e., rejecting the null, H0, when it is correct) from single to multiple hypothesis testing. In the single case, the Type I error is controlled by using the significance level (i.e., the size of the test). In the multiple case, we replace with the FDR, which is a compound Type I error measure. In both cases, we face a similar trade-off: In order to increase power, wehave to increase or the FDR, respectively (see the survey of Romano, Shaikh, and Wolf (2008)).