---
tags: R
---
Link: [Website](http://karolis.koncevicius.lt/posts/collection_of_simple_r_shortcuts/)

##### printing the result
```R
(x <- 1:10)
```
##### multiple assignments
```R
x <- y <- z <- numeric(10)
```
##### assignment from an if statement
```R
result <- if(rnorm(1) > 0) "positive" else "negative"
```
##### reversing a vector
```R
rev(x)
```
##### selecting the last element
```R
tail(df, 1)
```
##### elements in a nested list
```R
a <- list(3, list(8, list(0, 5)))
a[[c(2,2,1)]]
```
##### getting length of each element in a list
```R
lengths(xs)
```
##### repeating random computations multiple times
```R
replicate(10, mean(rnorm(20)))
```
##### replacing values
```R
x <- c("a", "b", "a", "c", "a", "b", "b")
n <- c(apple="a", bananna="b", cherry="c")

names(n)[match(x, n)]
```
```R
x <- c(2, 16, 88, 15, 33, 1, 21)
n <- c(baby=0, toddler=1, child=3, teen=12, adult=18, senior=65)

names(n)[findInterval(x, n)]
```
##### multi-line titles in base plots
```R
plot(1:10, main=c("Title", "sub"), xlab=c("Index", "x"))
```
##### extending plotting region area
```R
plot(x, y, xlim=extendrange(x, f=0.2))
```