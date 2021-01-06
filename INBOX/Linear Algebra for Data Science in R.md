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
* Rotations (clockwise, counter-clockwise).
* Reflections (e.g. about the x-axis, y-axis, origin, the line y = x)
* Dilations and Contractions
* Projections
* Every imaginable combination of these

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

No solutions: 
* Two equations representing two parallel lines in the x-y plane.

Infinitely-many solutions: 
* Parallel lines that are the same line - with their intersection including infinitely-many points in the x-y plane.

Unique solution (All conditions are equivalent):
* The matrix $A$ must have an inverse (is invertible).
* The determinant of $A$ is nonzero.
* The rows and columns of $A$ form a basis for the set of all vectors with $n$ elements.
* The homogenous equation $A\vec{x} = \vec{0}$ has just the trivial ($\vec{x} = 0$) solution

Determinant
* Can be calculated from a square matrix. 
* Helps find the inverse of a matrix.

Basis
* Combination of all the linearly independent vectors.

##### det()
det calculates the determinant of a matrix.

### Other Considerations
More Equations than Unknowns
Fewer Equations than Unknowns
Non-Square Matrices
* Row Reduction (By hand, difficult for big problems)
* Least Squares (If more rows than columns - Used in linear regression)
* Singular Value Decomposition (If more columns than rows - Used in Principal Component Analysis)
* Generalized or pseudo-inverse

#### library(MASS)
Functions and datasets to support Venables and Ripley, "Modern Applied Statistics with S"

##### ginv()
Moore-Penrose generalized inverse

## Eigenvalues and Eigenvectors
### Intro to Eigenvalues and Eigenvectors
Matrix multiplication can have multiple different, complex, effects on vectors.
* Rotations: taking vectors and rotating them via an angle
* Reflections: taking vectors and reflecting them about lines like the x or y-axis. 
* Dilations or contractions: growing or shrinking of vectors. 
* Projections: extracting certain components from a vector. 
* Or any permutation of any number of these operations. 

Eigenvalue/eigenvector analyses allow us to decompose these complex operations into the sum of much simpler ones.

Our goal is to be able to decompose a matrix into a few matrices whose individual effect is the same as scalar multiplication. This is the essence of eigenvalue/eigenvector analyses.

### Definition of Eigenvalues and Eigenvectors
For a matrix $A$, the scalar $\lambda$ is an eigenvalue of $A$, with associated eigenvector $\vec{v}$, if $A\vec{v} = \lambda\vec{v}$

This is extremely important to grasp that for $\vec{v}$, $A$ has the same effect as a matrix multiplication on $\vec{v}$ as $\lambda$ does as a scalar multiplication on $\vec{v}$.  Notice that this can be for any matrix $A$.

An eigenvector of a matrix $A$ is any vector $\vec{v}$ that only gets scaled (i.e. just multiplied by a number) when multiplied with $A$. An eigenvector is a scalar multiple of itself ("own") when multiplied by $A$.

The collection of eigenvectors for a matrix represent, in a sense, the characteristic dimensions of the matrix. A set of axes that stay invariant upon multiplication. 
Eigenvectors are entirely about direction and not magnitude.

### Computing Eigenvalues and Eigenvectors in R
Properties of solutions to eigenvalue/eigenvector problems
* An $n$ by $n$ matrix $A$ has, up to multiciplicity, $n$ eigenvalues.
* Eigenvalues need not to be real and could be complex numbers.
* All complex eigenvalues must come in conjugate pairs, like 1 + 2$i$ and 1 - 2$i$

##### eigen()
Computes eigenvalues and eigenvectors of numeric (double, integer, logical) or complex matrices.

### Some More on Eigenvalues and Eigenvectors
A big result in linear algebra:
* If the eigenvalues of a matrix are all distinct, then their associated eigenvectors form a basis for the collection of all vectors of the same size.
* In other words, every n-dimensional vector can be expressed as a linear combination of these eigenvectors.
* Eigenpairs turn matrix multiplication into a linear combination of scalar multiplication.
* Eigenvectors create "axes" along which matrix multiplication simply weighs vectors according to the eigenvalue associated to each eigenvector and "how close" the original vector is to each eigenvector.

Many models iteratively apply a matrix to a vector to evolve a system. 
* Cumbersome analytically (and computationally). 
* With eigenvector decomposition, it's as simple as a linear combination of the exponentiation of the eigenvalues times the eigenvectors. 
* When one eigenvalue is dominant, exponentiation of this dynamic will only grow this difference
	* The largest eigenvalue (and its eigenvector) is really the place to look to see what happens as t gets bigger.

R orders eigenvalue in descending order by size because the largest eigenvalue(s) characterize the application of the matrix the more times it's applied.

## Principal Component Analysis
### Intro to the Idea of PCA
Principal Component Analysis
* One of the more-useful methods from applied linear algebra
* Non-parametric way of extracting meaningful information from confusing data sets
* Uncovers hiden, low-dimensional structures that underlie your data
* These structures are more-easily visualized and are often interpretable to content experts

One of the important things that principal component analysis can do is shrink redundancy in your dataset. In its simplest manifestation, redundancy occurs when two variables are correlated.

### The Linear Algebra Behind PCA
For a given matrix A:
* Subtract the mean of each column from each element in a given column
* Do the product of A's transpose with A, divided by the n - 1
* The covariance between the variables is the ith and jth column of the resulting matrix.
* The ith element of the diagonal of the resulting matrix is the variance of the data in the ith column of A.

PCA
* The eigenvalues of this matrix are real, and their corresponding eigenvectors point in distinct directions.
* The total variance of the data set is the sum of the eigenvalues of A transpose times A divided by the number of degrees of freedom. 
* These eigenvectors are called the principal components of the data set in the matrix A. The direction in which one of the v's points can explain its eigenvalue's worth of the total variance in the dataset. If this eigenvalue is large in relation to the total variance, dimension reduction can be done.
