https://www.edureka.co/blog/interview-questions/r-interview-questions/

### 1. What are the different data structures in R? Briefly explain about them.

Broadly speaking these are Data Structures available in R:

**Data Structure** | **Description** |
-|-|
_**Vector**_|A **vector** is a sequence of data elements of the same basic type. Members in a vector are called **components**.|
_**List**_|**Lists** are the R objects which contain elements of different types like − numbers, strings, vectors or another list inside it.|
_**Matrix**_|A **matrix** is a two-dimensional data structure. Matrices are used to bind vectors from the same length.  All the elements of a matrix must be of the same type (numeric, logical, character, complex).|
_**Dataframe**_|A **data frame** is more generic than a matrix, i.e different columns can have different data types (numeric, character, logical, etc). It combines features of matrices and lists like a rectangular list.|

### 2. What are the different components of grammar of graphics?

Broadly speaking these are different components in grammar of graphics:

*   Data layer
*   Aesthetics layer
*   Geometry layer
*   Facet layer
*   Co-ordinate layer
*   Themes layer

### 3. What is Rmarkdown? What is the use of it?

RMarkdown is a reporting tool provided by R. With the help of Rmarkdown, you can create high quality reports of your R code. 

The following output formats are available to use with R Markdown.

#### Documents

*   [html\_notebook](https://bookdown.org/yihui/rmarkdown/notebook.html) - Interactive R Notebooks
*   [html\_document](https://bookdown.org/yihui/rmarkdown/html-document.html) - HTML document w/ Bootstrap CSS
*   [pdf\_document](https://bookdown.org/yihui/rmarkdown/pdf-document.html) - PDF document (via LaTeX template)
*   [word\_document](https://bookdown.org/yihui/rmarkdown/word-document.html) - Microsoft Word document (docx)
*   [odt\_document](https://bookdown.org/yihui/rmarkdown/opendocument-text-document.html) - OpenDocument Text document
*   [rtf\_document](https://bookdown.org/yihui/rmarkdown/rich-text-format-document.html) - Rich Text Format document
*   [md\_document](https://bookdown.org/yihui/rmarkdown/markdown-document.html) - Markdown document (various flavors)

#### Presentations (slides)

*   [ioslides\_presentation](https://bookdown.org/yihui/rmarkdown/ioslides-presentation.html) - HTML presentation with ioslides
*   [revealjs::revealjs\_presentation](https://bookdown.org/yihui/rmarkdown/revealjs.html) - HTML presentation with reveal.js
*   [slidy\_presentation](https://bookdown.org/yihui/rmarkdown/slidy-presentation.html) - HTML presentation with W3C Slidy
*   [beamer\_presentation](https://bookdown.org/yihui/rmarkdown/beamer-presentation.html) - PDF presentation with LaTeX Beamer
*   [powerpoint\_presentation](https://bookdown.org/yihui/rmarkdown/powerpoint-presentation.html): PowerPoint presentation

#### More

*   [flexdashboard::flex\_dashboard](/flexdashboard/) - Interactive dashboards
*   [tufte::tufte\_handout](https://bookdown.org/yihui/rmarkdown/tufte-handouts.html) - PDF handouts in the style of Edward Tufte
*   [tufte::tufte\_html](https://bookdown.org/yihui/rmarkdown/tufte-handouts.html) - HTML handouts in the style of Edward Tufte
*   [tufte::tufte\_book](https://bookdown.org/yihui/rmarkdown/tufte-handouts.html) - PDF books in the style of Edward Tufte
*   [html\_vignette](https://bookdown.org/yihui/rmarkdown/r-package-vignette.html) - R package vignette (HTML)
*   [github\_document](/github_document_format.html) - GitHub Flavored Markdown document

You can also build [books](https://bookdown.org/), [websites](https://bookdown.org/yihui/rmarkdown/rmarkdown-site.html), and [interactive documents](https://bookdown.org/yihui/rmarkdown/shiny-documents.html) with R Markdown.

### 4. What are the steps to build and evaluate a linear regression model in R?

These are sequential steps which need to be followed while building a linear regression model:

* Start off by dividing the data into train and test sets, this step is vital because you will be building the model on the train set and evaluating it’s performance on the test set.
* You can do this using the sample.split() function from the “catools” package. This function gives an option of split-ratio, which you can specify according to your needs.
* Once, you are done splitting the data into training and test sets, You can go ahead and build the model on the train set.
    * The “lm()” function is used to build a model.
* Finally you can predict the values on the test set, using the “predict()” function.
* The final step would be to find out the RMSE, the lower the RMSE value, the better the prediction.

### 5. What is a Random Forest? How do you build and evaluate a Random Forest in R?

Random Forest is an ensemble classifier made using many decision tree models. It combines the results from many decision tree models and this result is usually better than the result of any individual model.

*   Let’s start off by dividing the data into train and test
*   Build random forest model on the train set
*   Now, we’ll predict the model on the test set

### 6. Tell me something about shinyR.

Shiny is an R package that makes it easy to build interactive web apps straight from R. You can host standalone apps on a webpage or embed them in Rmarkdown documents or build dashboards. You can also extend your Shiny apps with CSS themes, htmlwidgets, and JavaScript actions.

### 7. What is advantage of using apply family of functions in R?

The apply function allows us to make entry-by-entry changes to data frames and matrices.

The usage in R is as follows:

apply(X, MARGIN, FUN, …)

where:

X is an array or matrix;

MARGIN is a variable that determines whether the function is applied over rows (MARGIN=1), columns (MARGIN=2), or both (MARGIN=c(1,2));

FUN is the function to be applied.

If MARGIN=1, the function accepts each row of X as a vector argument, and returns a vector of the results. Similarly, if MARGIN=2 the function acts on the columns of X. Most impressively, when MARGIN=c(1,2) the function is applied to every entry of X.

Advantage:

With the apply function we can edit every entry of a data frame with a single line command. No auto-filling, no wasted CPU cycles.

### 8. What packages are used for data mining in R?

Some packages used for data mining in R:

*   data.table- provides fast reading of large files
*   rpart and caret- for machine learning models.
*   Arules- for associaltion rule learning.
*   GGplot- provides varios data visualization plots.
*   tm- to perform text mining.
*   Forecast- provides functions for time series analysis

### 9. What is clustering? What is the difference between kmeans clustering and hierarchical clustering?

Cluster is a group of objects that belongs to the same class. Clustering is the process of making a group of abstract objects into classes of similar objects.

Let us see why clustering is required in data analysis:

* Scalability − We need highly scalable clustering algorithms to deal with large databases.
* Ability to deal with different kinds of attributes − Algorithms should be capable of being applied to any kind of data such as interval-based (numerical) data, categorical, and binary data.
* Discovery of clusters with attribute shape − The clustering algorithm should be capable of detecting clusters of arbitrary shape. They should not be bounded to only distance measures that tend to find spherical cluster of small sizes.
* High dimensionality − The clustering algorithm should not only be able to handle low-dimensional data but also the high dimensional space.
* Ability to deal with noisy data − Databases contain noisy, missing or erroneous data. Some algorithms are sensitive to such data and may lead to poor quality clusters.
* Interpretability − The clustering results should be interpret-able, comprehensible, and usable.

##### K-MEANS clustering:

K-means clustering is a well known partitioning method. In this method objects are classified as belonging to one of K-groups. The results of partitioning method are a set of K clusters, each object of data set belonging to one cluster. In each cluster there may be a centroid or a cluster representative. In the case where we consider real-valued data, the arithmetic mean of the attribute vectors for all objects within a cluster provides an appropriate representative; alternative types of centroid may be required in other cases.

Example: A cluster of documents can be represented by a list of those keywords that occur in some minimum number of documents within a cluster. If the number of the clusters is large, the centroids can be further clustered to produce hierarchy within a dataset. K-means is a data mining algorithm which performs clustering of the data samples. In order to cluster the database, K-means algorithm uses an iterative approach.

A robust version of K-means based on mediods can be invoked by using pam( ) instead of kmeans( ). The function pamk( ) in the fpc package is a wrapper for pam that also prints the suggested number of clusters based on optimum average silhouette width.

##### Hierarchical Clustering:

This method creates a hierarchical decomposition of the given set of data objects. We can classify hierarchical methods on the basis of how the hierarchical decomposition is formed. There are two approaches here:

1.  Agglomerative Approach
2.  Divisive Approach

Agglomerative Approach:

This approach is also known as the bottom-up approach. In this, we start with each object forming a separate group. It keeps on merging the objects or groups that are close to one another. It keeps on doing so until all of the groups are merged into one or until the termination condition holds.

Divisive Approach:

This approach is also known as the top-down approach. In this, we start with all of the objects in the same cluster. In the continuous iteration, a cluster is split up into smaller clusters. It is down until each object in one cluster or the termination condition holds. This method is rigid, i.e., once a merging or splitting is done, it can never be undone.

### 10. What do you know about the rattle package in R?

**Rattle** is a popular GUI for data mining using [R](https://www.r-project.org/). It presents statistical and visual summaries of data, transforms data so that it can be readily modelled, builds both unsupervised and supervised machine learning models from the data, presents the performance of models graphically, and scores new datasets for deployment into production. _A key features is that all of your interactions through the graphical user interface are captured as an R script that can be readily executed in R independently of the Rattle interface._

### 11. What is a White Noise model and how can you simulate it using R?

The white noise (WN) model is a basic time series model.It is the simplest example of a stationary process.

A white noise model has:

*   A fixed constant mean
*   A fixed constant variance
*   No correlation over time

Simulating a white noise model in R:

    arima.sim(model=list(order=c(0,0,0)),n=50)->wn
    ts.plot(wn)

### 12. What is a Random Walk model and how can you simulate it using R?

A random walk is a simple example of non-stationary process.

A random walk has:

*   No specified mean or variance
*   Strong dependence over time
*   It’s changes or increments are white noise

Simulating random walk in R:

    arima.sim(model=list(order=c(0,1,0)),n=50)->rw

### 13. What is Principal Component Analysis and how can you create a PCA model in R?

Principal Component Analysis is a method for dimensionality reduction. Many a times, it happens that, one observation is related to multiple dimensions(features) and this brings in a lot of chaos to the data, that is why it is important to reduce the number of dimensions.

The concept of Principal Component Analysis is this:

* The data is transformed to a new space, with equal or less number of dimensions. These dimensions(features) are known as principal components.
* The first principal component captures the maximum amount of variance from the features in the original data.
* The second principal component is orthogonal to the first and captures the maximum amount of variability left.
* The same is true for each principal component, they are all uncorrelated and each is less important than the previous one.

We can do PCA in R with the help of “prcomp()” function.

prcomp(iris[-5])->pca

Let’s see how the variability decreases across different principal components

screeplot(pca)

### 14. What do you know about the evaluate_model() function from “statisticalModeling” Package

This is an alternative to the “predict()” function . i.e. It is used to predict the values of the built model.

The difference between this and predict function is that, it automatically selects more sensible values than the predict function.

### 15. What is the difference between a bar-chart and a histogram? Where would you use a bar-chart and where would you use a histogram?

People most often get confused where to use a histogram and where to use a bar-graph. One simple point to be kept in mind is, histograms are used to plot the distribution of a continuous variable and bar-charts are used to plot the distribution of a categorical variable.

### 16. What is a factor? How would you create a factor in R?

Conceptually, factors are variables in R which take on a limited number of different values; such variables are often referred to as categorical variables. One of the most important use of factors is in statistical modeling; since categorical variables enter into statistical models differently than continuous variables, storing data as factors ensures that the modeling functions will treat such data correctly.

### 17. Name some functions which can be used for debugging in R?

These are some functions which can be used for debugging in R:

*   traceback()
*   debug()
*   browser()
*   trace()
*   recover()