---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=mApnx5NJwQA), [Vignette](https://cran.r-project.org/web/packages/widyr/vignettes/intro.html)

# The widyr package
This package wraps the pattern of un-tidying data into a wide matrix, performing some processing, then turning it back into a tidy form (the widen-operate-retidy pattern). This is useful for several mathematical operations such as co-occurrence counts, correlations, or clustering that are best done on a wide matrix.

### Examples
pairwise_cor

* UN voting data library(unvotes)
* word co-occurences

Workflow
widyr -> dplyr -> ggplot2

[Tidygraph/ggraph integration](https://cran.r-project.org/web/packages/ggraph/vignettes/tidygraph.html)

### Functions
pairwise_cor
pairwise_count
pairwise_dist
pairwise_similarity
pairwise_pmi
pairwise_delta

###### In development
widely_kmeans clustering on tidy data
widely_hclust
widely_svd

 Singular value decomposition (SVD) is one of the most widely used algorithms for data processing, reduced-order modeling, and high-dimensional statistics.  
 
 It is the data-driven generalization of a Fourier transform.
 
 The Fourier Transform takes a time-based pattern, measures every possible cycle, and returns the overall "cycle recipe" (the amplitude, offset, & rotation speed for every cycle that was found).
 
[Singular Value Decomposition (SVD): Overview ](https://www.youtube.com/watch?v=gXbThCXjZFM)
 https://betterexplained.com/articles/an-interactive-guide-to-the-fourier-transform/
 
* Solve Ax = b for non square A 
* linear regression model
* basis PCA
* correlation
 
 Based on simple / interpretable linear algebra