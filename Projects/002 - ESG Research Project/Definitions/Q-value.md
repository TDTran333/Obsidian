---
tags: definition, stats
---
Link: [Wikipedia](https://en.wikipedia.org/wiki/Q-value_(statistics)), [Lecture](https://www.gs.washington.edu/academics/courses/akey/56008/lecture/lecture10.pdf)
Related: [[False Rate Discovery]]

### From wikipedia
In statistical hypothesis testing, specifically multiple hypothesis testing, the q-value provides a means to control the positive false discovery rate (pFDR). Just as the p-value gives the expected false positive rate obtained by rejecting the null hypothesis for any result with an equal or smaller p-value, the q-value gives the expected pFDR obtained by rejecting the null hypothesis for any result with an equal or smaller q-value. 

### From lecture
* q-value is defined as the minimum FDR that can be attained when calling that “feature” significant (i.e., expected proportion of false positives incurred when calling that feature significant)
* The estimated q-value is a function of the p-value for that testand the distribution of the entire set of p-values from the family of tests being considered (Storey and Tibshiriani 2003)
* Thus, in an array study testing for differential expression, if gene X has a q-value of 0.013 it means that 1.3% of genes that show p-values at least as small as gene X are false positives

