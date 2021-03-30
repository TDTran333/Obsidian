---
tags: R
---
Link: [StackOverflow](https://stackoverflow.com/questions/17308551/do-callrbind-list-for-uneven-number-of-column)

Best solution:
```R
purrr::map_df(df, ~as.data.frame(t(.x),stringsAsFactors = FALSE))
```

```R
rbind.named.fill <- function(x) {
    nam <- sapply(x, names)
    unam <- unique(unlist(nam))
    len <- sapply(x, length)
    out <- vector("list", length(len))
    for (i in seq_along(len)) {
        out[[i]] <- unname(x[[i]])[match(unam, nam[[i]])]
    }
    setNames(as.data.frame(do.call(rbind, out), stringsAsFactors=FALSE), unam)
}
```
```
dplyr::bind_rows(lapply(x,function(y) as.data.frame(t(y),stringsAsFactors=FALSE)))
```
```R
cbind.named.fill <- function(x) {
    nam <- sapply(x, names)
    unam <- unique(unlist(nam))
    len <- sapply(x, length)
    out <- vector("list", length(len))
    for (i in seq_along(len)) {
        out[[i]] <- unname(x[[i]])[match(unam, nam[[i]])]
    }
    setNames(as.data.frame(do.call(cbind, out), stringsAsFactors=FALSE), names(x))
}
```