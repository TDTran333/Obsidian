Barras, Laurent, O. Scaillet, and Russ Wermers. “Reassessing False Discoveries in Mutual Fund Performance: Skill, Luck, or Lack of Power? A Reply.” SSRN Scholarly Paper. Rochester, NY: Social Science Research Network, October 24, 2019. https://doi.org/10.2139/ssrn.3439231.

---

[[FDR Critics]]

> In this Reply, we replicate their results, then further explore the bias issue by (i) using different parameter values, and (ii) updating the sampleperiod.

* Over the original period (1975-2006), we show how reasonable adjustments
to the parameter choices made by BSW and AP results in a sizeable reduction in the
bias relative to AP.
* Over the updated period (1975-2018), we further show that the performance of the FDR improves dramatically across a large range of parameter values. 

> Specifically, we find that the probability of misclassifying a fund with a true alpha of 2% per year is 32% (versus 65% in AP).

> Our results, in combination with those of AP, indicate that the use of the FDR in finance should be accompanied by a careful evaluation of the underlying data generating process, especially when the sample size is small.

### Introduction

> It is well known from theory that the FDR estimators are potentially biased, as
	overestimates $\pi^0$ and $\pi^A$ underestimates the real values (e.g., Genovese and Wasserman (2004), Storey (2002)). This issue arises when non-zero alpha funds are difficult to detect in the data, either because their alphas are small, or the estimation noise is large.
	
>  To quantify this bias, BSW perform a simulation analysis using a set of parameter values, and conclude that both $\pi^0$ and $\pi^A$ are close to their true values.

> Andrikogiannopoulou and Papakonstantinou (2019; henceforth, AP) challenge the
simulation analysis of BSW based on their choice of parameter values.

* First, they correctly point out that the number of assumed fund return observations is set too high by BSW, which artificially reduces the estimation noise compared to the actual sample.
* Second, they consider smaller (in magnitude) values for the true alphas of non zero alpha funds. Incorporating these changes, AP conclude, from simulations based on revised parameter values, that the proportions $\pi^0$ and $\pi^A$ are heavily biased.

> AP question the usefulness of the FDR for evaluating the performance of mutual funds (objective (i) of BSW).

> We recognize that AP conduct an important critical evaluation of the FDR approach for the benefit of empirical researchers. The FDR has been increasingly used as an estimation approach in mutual fund performance and other areas of finance because it is simple and fast–simply put, it amounts to estimating a simple average based on -statistics.

##### In this Reply to AP, we pursue some simple goals. 
* First, we seek to replicate the results of BSW and AP. 
* Second, we wish to provide further extensions of the BSW and AP simulation results by 
	* (i) using parameter values that we believe better reflect the data generating process of mutual fund alphas in the real-world, and 
	* (ii) extending their original sample period (1975-2006). 
* In conducting this analysis, we develop an analytical approach that allows us to quantify the bias of the FDR approach without recourse to simulations. This approach is simple and allows for a completely transparent comparison of the results in BSW, AP, and our Reply.

> Our results reveal that the changes in parameter values materially affect the eval
uation of the FDR approach. Over the original period (1975-2006), we find that the
bias decreases significantly relative to AP once we (i) consider alternative values for the fund residual volatility, and (ii) account for the relations between the different parameters, which are motivated by theory and supported by empirical evidence.

*To illustrate AP find that a fund with a true alpha of 2% per year is misclassified as a zero alpha fund 65% of the time. 
* We instead find that the misclassification probability is equal to 44%.

##### period 1975 to 2018
> Using the same procedure as in BSW and AP, we find that the probability of misclassifying a fund with an alpha of 2% per year drops to 37%. With the procedure proposed here, the misclassificatio probability further drops to 32%.

##### General implication of reply
* First, it highlights the importance of carefully analyzing the properties of the data to assess the benefits of the FDR. This analysis is particularly important if the sample period is relatively short. 
* Second, it provides a simple approach for evaluating the bias of the FDR without recourse to simulations–a definite benefit to empiricists who wish to explore the performance of the FDR approach for their empirical application.


### Conclusion

> Whereas we confirm that the initial analysis of BSW may be too optimistic, we do not find the high levels of bias documented by AP.

> Our analysis of the updated sample provides a clearer picture of the performance of the FDR. The misclassification probability decreases significantly, and the bias of the FDR proportions is low across a wide range of scenarios. We therefore conclude that the FDR approach is useful for current researchers in the field of mutual fund performance.

> These results represent good news for the academic community which typically favors statistical methods that are simple and fast–two major advantages of the FDR approach.

## ABSTRACT
Andrikogiannopoulou and Papakonstantinou (AP; 2019) conduct an inquiry into
the bias of the False Discovery Rate (FDR) estimators of Barras, Scaillet, and
Wermers (BSW; 2010). In this Reply, we replicate their results, then further explore the bias issue by (i) using different parameter values, and (ii) updating the sample
period. Over the original period (1975-2006), we show how reasonable adjustments
to the parameter choices made by BSW and AP results in a sizeable reduction in the
bias relative to AP. Over the updated period (1975-2018), we further show that the
performance of the FDR improves dramatically across a large range of parameter
values. Specifically, we find that the probability of misclassifying a fund with a true
alpha of 2% per year is 32% (versus 65% in AP). Our results, in combination with
those of AP, indicate that the use of the FDR in finance should be accompanied by
a careful evaluation of the underlying data generating process, especially when the
sample size is small.

#### Thoughts

Replicated their results
Explore the bias issue by 
	* Using different parameter values
		* Sizable reduction of the bias vs. AP
	* Updating the sample period
		* Performance of FDR improves "dramatically"

> Specifically, we find that the probability of misclassifying a fund with a true
alpha of 2% per year is 32% (versus 65% in AP). 

That's still a huge problem...

> Our results, in combination with those of AP, indicate that the use of the FDR in finance should be accompanied by a careful evaluation of the underlying data generating process, especially when the sample size is small.
	
Is the methodology not good???

Did they manage to defend the critics? Need to read the paper


	


