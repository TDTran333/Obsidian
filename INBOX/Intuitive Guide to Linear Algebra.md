---
tags: math
---
Link: [Website](https://betterexplained.com/articles/linear-algebra-guide/)

# Intuitive Guide to Linear Algebra

**Linear algebra gives you mini-spreadsheets for your math equations.**
We can take a table of data (a matrix) and create updated tables from the original. It’s the power of a spreadsheet written as an equation.

### What’s in a name?
“Algebra” means, roughly, “relationships”.
“Linear Algebra” means, roughly, “line-like relationships”.

### Linear Operations
Which operations are linear and predictable? Multiplication

### Organizing Inputs and Operations
What’s the key idea?
-   We have a bunch of inputs to track
-   We have predictable, linear operations to perform
-   We generate a result, perhaps transforming it again

Inputs in vertical columns, operations in horizontal rows.
A matrix is a single variable representing a spreadsheet of inputs or operations.

### Numbering
Matrix size is measured as RxC: row count, then column count, and abbreviated “m x n”. Items in the matrix are referenced the same way: aij is the ith row and jth column.

```
[Operation Matrix] [Input Matrix]
[operation count x operation size] [input size x input count]
[m x n] [p x q] = [m x q]
```

We can _only_ multiply matrices when n = p.

### Operations
