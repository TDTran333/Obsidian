Link: [Website](https://r4ds.had.co.nz/iteration.html#dealing-with-failure)

safely() is an adverb: it takes a function (a verb) and returns a modified version. In this case, the modified function will never throw an error. Instead, it always returns a list with two elements:

1. result is the original result. If there was an error, this will be NULL.
2. error is an error object. If the operation was successful, this will be NULL.

safely() is designed to work with map

```R
x <- list(1, 10, "a")
y <- x %>% map(safely(log)) %>% transpose()
str(y)

x %>% map_dbl(possibly(log, NA))
```

Like safely(), possibly() always succeeds. It’s simpler than safely(), because you give it a default value to return when there is an error.

quietly() performs a similar role to safely(), but instead of capturing errors, it captures printed output, messages, and warnings