---
tags: R
---
Link: [Vignette](https://cran.r-project.org/web/packages/broom/vignettes/broom.html)

### Summary
broom summarizes key information about models in tidy tibble()s. broom provides three verbs to make it convenient to interact with model objects:

* tidy() summarizes information about model components
* glance() reports information about the entire model
* augment() adds informations about observations to a dataset

### Usage
tidy() produces a tibble() where each row contains information about an important component of the model. For regression models, this often corresponds to regression coefficients. This is can be useful if you want to inspect a model or create custom visualizations.

glance() returns a tibble with exactly one row of goodness of fitness measures and related statistics. This is useful to check for model misspecification and to compare many models.

augment adds columns to a dataset, containing information such as fitted values, residuals or cluster assignments. All columns added to a dataset have . prefix to prevent existing columns from being overwritten.