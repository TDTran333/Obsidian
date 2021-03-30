https://rpubs.com/tomhopper/brackets
https://www.r-bloggers.com/2009/10/r-accessors-explained/

- [ for subsets,
- [[ for extracting items, and
- $ for extracting by name.

Using dplyr, the equivalent is

- filter() and slice() for subsets by rows,
- select() for subsetting by columns, and
- magrittr::extract2() for extracting by column name or index

