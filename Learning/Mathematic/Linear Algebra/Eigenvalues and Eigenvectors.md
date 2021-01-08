---
aliases:
tags: wip, math
---
Links: [Stackexchange 1](https://math.stackexchange.com/questions/23312/what-is-the-importance-of-eigenvalues-eigenvectors), [Stackexchange 2](https://math.stackexchange.com/questions/1520832/real-life-examples-for-eigenvalues-eigenvectors), [Betterexplained](https://betterexplained.com/articles/linear-algebra-guide/), [Khan Academy](https://www.khanacademy.org/math/linear-algebra/alternate-bases/eigen-everything/v/linear-algebra-introduction-to-eigenvalues-and-eigenvectors), [YouTube](https://www.youtube.com/watch?v=PFDu9oVAE-g)

# Eigenvalues and Eigenvectors
 _Eigenvectors make understanding linear transformations easy_. They are the "axes" (directions) along which a linear transformation acts simply by "stretching/compressing" and/or "flipping"; eigenvalues give you the factors by which this compression occurs.

### Real life examples
- [Dimensionality Reduction/PCA.](https://en.wikipedia.org/wiki/Principal_component_analysis) The principal components correspond the the largest eigenvalues of ATA-   and this yields the least squared projection onto a smaller dimensional hyperplane, and the eigenvectors become the axes of the hyperplane. Dimensionality reduction is extremely useful in machine learning and data analysis as it allows one to understand where most of the variation in the data comes from.
- [Low rank factorization for collaborative prediction.](http://cs229.stanford.edu/proj2006/KleemanDenuitHenderson-MatrixFactorizationForCollaborativePrediction.pdf) This what Netflix does (or once did) to predict what rating you'll have for a movie you have not yet watched. It uses the SVD, and throws away the smallest eigenvalues of ATA  
- [The Google Page Rank algorithm.](https://en.wikipedia.org/wiki/PageRank) The largest eigenvector of the graph of the internet is how the pages are ranked.