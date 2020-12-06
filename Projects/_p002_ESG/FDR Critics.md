> This bias arises from the fact that the pivotal assumptions behind the estimator fail due to the low signal-to-noise ratio in fund return data and the consequent lack of statistical power in tests of fund alpha.

> BSW does not diagnose these limitations, because it is conducted under the specific assumptions that all nonzero alphas are very large (around 3:5% per year) and there is a large number of observations per fund.

> Rather it is likely an artifact of an estimation methodology that has low power to detect nonzero-alpha funds

> i) the p-values corresponding to true nulls are independent and uniformly distributed on \[0, l]
ii) the p-values corresponding to the alternatives are near 0

> assumption (ii) of the FDR is equivalent here to assuming that nonzero alphas are sufficiently large and/or alpha is estimated with great precision.

> Essentially, if (some) individual tests have low power to detect the alternative, the p-values that correspond to the alternatives will be distributed over the entire \[0; 1] interval 0;

> The crucial assumption that all p-values above the threshold correspond to zero-alpha funds is met when nonzero alphas are far from 0 and/or the amount of information in the data is large. But it is likely that some nonzero alphas are not very far from zero, and moreover the information contained in each fund’s returns is known to vary widely across funds.

> Importantly, the mis-estimation we document is not because the FDR approach is economically conservative, but because it is statistically conservative. That is, it does not misclassify as zero-alpha funds those with alpha close to zero but rather those for which, given the noise in the data, there is insufficient power to reject the null.

> For extreme alphas ( 3:5%), the FDR approach estimates the proportions accurately for all levels of $\pi^0$, while the no-luck approach is less accurate as it fails to account for lucky and unlucky funds. But in the other panels we see that for less extreme, yet economically large, alphas — 1% and 2% — the FDR approach does not perform better than the no-luck approach, and it may even perform worse on average, due to its large bias.

> We find that fat tails slightly ameliorate the bias in the FDR estimates, but this effect is very weak and the bias is still large even with very fat tails.

> We find that the FDR performs poorly under certain conditions, and that the accuracy found in past simulations in the mutual fund setting can be traced to potentially unrealistic simulation assumptions such as that i) fund alphas follow a discrete distribution with point masses very far from zero, ii) there is a large number of observations per fund, and iii) there is no or limited cross-sectional correlation across funds.

> Overall, our results indicate that the FDR approach is unlikely to offer a substantial improvement over simpler methodologies in settings where the signal-to-noise ratio in the data is low and consequently individual tests have low power.

[[Barras_Scaillet_Wermers_2019_Reassessing_False_Discoveries_in_Mutual_Fund_Performance_a_reply]]