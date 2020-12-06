# by()

---
## Definition
The by( ) function applys a function to each level of a factor or factors. It is similar to BY processing in SAS.

```R
# by(data, factorlist, function)
# example obtain variable means separately for
# each level of byvar in data frame mydata
by(mydata, mydata$byvar, function(x) mean(x))
```

## Documentation
<!-- Link to wiki or youtube video-->


---
Date: 2020-11-23
Tags: #Definition
Topic: [[R - Functions]]
Related:
Status: #wip

---