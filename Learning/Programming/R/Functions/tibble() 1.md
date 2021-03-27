---
tags: definition, R
---

tibble() constructs a data frame. It is used like base::data.frame(), but with a couple notable differences:

* The returned data frame has the class tbl_df, in addition to data.frame. This allows so-called "tibbles" to exhibit some special behaviour, such as enhanced printing. Tibbles are fully described in tbl_df.

* tibble() is much [[Lazy Evaluation|lazier]] than base::data.frame() in terms of transforming the user's input. Character vectors are not coerced to factor. List-columns are expressly anticipated and do not require special tricks. Column names are not modified.

* tibble() builds columns sequentially. When defining a column, you can refer to columns created earlier in the call. Only columns of length one are recycled.

* If a column evaluates to a data frame or tibble, it is nested or spliced. 