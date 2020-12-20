# with()

---
## Definition
The with( ) function applys an expression to a dataset. It is similar to DATA= in SAS.

```R
# with(data, expression)
# example applying a t-test to a data frame mydata
with(mydata, t.test(y ~ group))
```


---
Date: 2020-11-23
Tags: #Definition
Topic: [[R - Functions]]
Related:
Status: #wip

---