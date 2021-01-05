---
aliases:
tags: R, math
---

# Linear Algebra for Data Science in R
## Introduction to Linear Algebra
Many of the objects in which we store data (spreadsheets, tables, data frames) can be broken down into one of the main objects studied in linear algebra - vectors and matrices.

#### Vectors - Storing Univariate Data
##### rep()
Creates a vector that repeats the same element a prescribed number of times
##### seq()
Creates a vector that follows a prescribed pattern.
##### c()
"concatenate".

If two vectors are not the same size, R recycles elements of the shorter vector to obtain the given result (with a warning message).

#### Matrices - Storing Tables of Data
##### matrix(a, nrow = b, ncol = c)
Creates a matrix that repeats the element `a` in a matrix with `b` rows and `c` columns.
A matrix can be manually created by using the `c()` command as well.

### Matrix-Vector Operations
`%*% `: dot product vs. `*`: component-wise multiplication

Matrices can be viewed as a way to transform collections of vectors into other vectors.
* stretches or shrinkages (in either coordinate)
* reflections (e.g. about the x-axis, y-axis, origin, the line y = x)
* rotations (clockwise, counter-clockwise).

### Matrix-Matrix Operations
Matrix multiplication is **not commutative**, the order of the transformations matter.

##### diag(n)
Creates an identity matrix of dimension n.
##### solve()
Find the inverse of a matrix if it exists and provide an error if it does not.

| More matrices type            | Description                                                                                     |
|:----------------------------- |:----------------------------------------------------------------------------------------------- |
| Square matrix                 | Matrix where the number of columns is the same as the number of rows.                           | 
| The matrix inverse            | When multiplied by a suitable matrix yields the identity matrix in return.                      |
| Singular matrix               | Matrices that don't have an inverse.                                                            |
| Diagonal or triangular matrix | Build many of the matrices we use in practice. More efficient from a computational perspective. |

## Matrix-Vector Equations
### Motivation for Solving Matrix-Vector Equations
A great deal of applied mathematics and statistics, as well as data science, ends in a matrix-vector equation of the form: $A\vec{x} = \vec{b}$
Solving this equation means produce $\vec{b}$ using a linear combination of the columns of $A$. 
In other words, the elements of $\vec{x}$ are the coefficients when one creates $\vec{b}$ from the columns of $A$.

### Matrix-Vector Equations - Some Theory
Under what conditions does a matrix-vector equation a) has a solution and b) has a unique solution?

No solutions: two equations representing two parallel lines in the x-y plane.
Infinitely-many solutions: Parallel lines that are the same line - with their intersection including infinitely-many points in the x-y plane.

Unique solution:
All conditions are equivalent:
* The matrix $A$ must have an inverse (is invertible).
* The determinant of $A$ is nonzero.
* The rows and columns of $A$ form a basis for the set of all vectors with $n$ elements.

##### det()
det calculates the determinant of a matrix.

### Solving Matrix-Vector Equations


## Eigenvalues and Eigenvectors

## Principal Component Analysis