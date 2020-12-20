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

 [[Singular Value Decomposition]]