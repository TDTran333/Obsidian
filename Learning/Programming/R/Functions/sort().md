# sort()

---
## Definition
R uses the `sort()` function to order a vector or factor, listed and described below.

**Radix**: Usually the most performant algorithm, this is a non-comparative sorting algorithm that avoids overhead. It’s stable, and it’s the default algorithm for integer vectors and factors. 

**Quick Sort:** This method “uses Singleton (1969)’s implementation of Hoare’s Quicksort method and is only available when x is numeric (double or integer) and partial is NULL,” according to [R Documentation](https://www.rdocumentation.org/packages/base/versions/3.5.1/topics/sort). It’s not considered a stable sort.

**Shell:** This method “uses Shellsort (an O(n4/3) variant from Sedgewick (1986)),” according to R Documentation.

## Documentation
<!-- Link to wiki or youtube video-->


---
Date: 2020-11-23
Tags: #Definition
Topic: [[R - Functions]]
Related:
Status: #wip

---