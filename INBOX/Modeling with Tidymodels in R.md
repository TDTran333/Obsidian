---
aliases:
tags: R
---
Link:

# Modeling with Tidymodels in R
### Tidymodels overview
Data resampling with **rsample**
Feature engineering with **recipes**
Model fitting with **parsnip**
Model tuning with **tune** and **dials**
Model evaluation with **yardstick**

### Supervised machine learning
Regression
* Predicting quantitative outcomes

Classification
* Predicting categorical outcomes

Outcome variable vs. predictor variables

### Data resampling with tidymodels
Create training and test sets
* Guards against overfitting
* Common ratio is 75% training, 25% test 
* Feature engineering, model fitting and tuning with training data
* Estimating model performance on new data with test data

#### library(tidymodels)
The tidymodels framework is a collection of packages for modeling and machine learning using tidyverse principles.

##### initial_split()
Specifies instructions for creating training and test datasets
* prop argument specifies the porportion to place into training
* strata argumen provides stratification by the outcome variable

##### training()
Extract training data

##### testing()
Extract testing data

Stratifying by the outcome variable ensures the model fitting process is performed on a representative sample of the original data.

### Linear regression with tidymodels

#### library(parsnip)
The goal of parsnip is to provide a tidy, unified interface to models that can be used to try a range of models without getting bogged down in the syntactical minutiae of the underlying packages.

* Specify the model type
* Specify the engine
* Specifiy the mode

##### linear_reg()
linear_reg() is a way to generate a specification of a model before fitting

##### set_engine()
set_engine() is used to specify which package or system will be used to fit the model

##### set_mode()
set_mode() is used to change the model's mode

##### fit()
Estimates parameters for a given model from a set of data

##### tidy()
Turn an object into a tidy tibble

##### predict()
predict is a generic function for predictions from the results of various model fitting functions

##### bind_cols()
Efficiently bind multiple data frames by row and column

Printing a `parsnip` model fit object displays useful model information, such as the training time, model formula used during training, and the estimated model parameters.

### Evaluating model performance

#### library(yardstick)
`yardstick` is a package to estimate how well models are working using tidy data principles. Requires a tibble with true outcome and model predictions.

##### rmse()
Calculate the root mean squared error (the average prediction error). rmse() is a metric that is in the same units as the original data. Truth parameter and estimate parameter.

##### rsq()
Calculate the coefficient of determination using correlation. Squared correlation between actual and predicted values.

##### coord_obs_pred()
For regression models, coord_obs_pred() can be used in a ggplot to make the x- and y-axes have the same exact scale along with an aspect ratio of one.

##### last_fit()
last_fit() emulates the process where, after determining the best model, the final fit on the entire training set is needed and is then evaluated on the test set.

##### collect_metrics() and collect_predictions()
Obtain and format results produced by tuning functions.

### Classification models
Classification algorithms create distinct, non-overlapping regions along set of predictor variable values

Logistic regression
* Create a linear separation between outcome categories

##### logistic_reg()
logistic_reg() is a way to generate a specification of a model before fitting
engine = "glm", mode = "classification"

##### predict() argument type = "class" or "prob"
Obtain categorical predictions or estimated probabilities for each outcome category.

### Assessing model fit
In tidymodels outcome variable needs to be a factor and the first level is the positive class

Confusion matrix
* Counts of all combination of actual and predicted outcome values
* Correct predictions are true positive and true negative
* Classification errors can be a false positive or a false negative

##### conf_mat()
Calculates a cross-tabulation of observed and predicted classes for categorical data. Passing results of conf_mat() to summary() will calculate all the classification metrics at once.

##### accuracy()
Accuracy is the proportion of the data that are predicted correctly.
(TP + TN) / (TP + TN + FP + FN)

##### sens() sensitivity
Proportion of all positive cases that were correctly classified.
TP / (TP + FN)

##### spec() specificity
Proportion of all negative cases that were correctly classified.
TN / (TN + FP)

1 - Specificity
* False positive rate, proportion of false positives among negatives

##### metric_set()
metric_set() allows you to combine multiple metric functions together into a new function that calculates all of them at once.

![[Pasted image 20210324115626.png]]

### Visualizing model performance

Plotting the confusion matrix with autoplot()
* Set type to "heatmap"
* Set type to "mosaic"

##### autoplot()
autoplot() uses ggplot2 to draw a particular plot for an object of a particular class in a single command. 

#### Performance across thresholds
* Default probability threshold in binary classification is 0.5
* Receiver operating characteristic (ROC) curve is used to visualize performance across probability thresholds
* Sensitivity vs (1 - specificity) across unique thresholds in test set results
	* Proportion of correct among actual positives vs. proportion of incorrect among actual negatives
	* Optimal performance is at the point (0, 1)
		* Ideally, a classification model produces points close to the left upper edge across all thresholds
		* Poor performance if the model produce predictions along the diagonal line
	* The area under the ROC curve (ROC AUC) captures the ROC curve information of a classification in a single number 

##### roc_curve()
roc_curve() constructs the full ROC curve and returns a tibble. Passing the results of roc_curve() to the autoplot() function returns an ROC curve plot.

##### roc_auc()
roc_auc() is a metric that computes the area under the ROC curve. 

### Automating the modeling workflow
last_fit() aslso accepts classification models
* Create a data split object with initial_split()
* Specify a model with parsnip
* Calculate metrics using the test dataset with collect_metrics()
* Create custom metrics with metric_set()
	* roc_auc() requires truth and a column of estimated probabilities

Example:
``` R
# Train model with last_fit()
telecom_last_fit <- logistic_model %>% 
  last_fit(canceled_service ~ avg_call_mins + avg_intl_mins + monthly_charges,
           split = telecom_split)
# View test set metrics
telecom_last_fit %>% 
  collect_metrics()
  # Collect predictions
last_fit_results <- telecom_last_fit %>% 
  collect_predictions()
# View results
last_fit_results
# Custom metrics function
last_fit_metrics <- metric_set(accuracy, sens,
                               spec, roc_auc)
# Calculate metrics
last_fit_metrics(last_fit_results,
                 truth = canceled_service,
                 estimate = .pred_class,
                 .pred_yes)
```

### Feature engineering
The first step in feature engineering is to specify a `recipe` object with the `recipe()` function and add data preprocessing steps with one or more `step_*()` functions. Storing all of this information in a single `recipe` object makes it easier to manage complex feature engineering pipelines and transform new data sources.

![[Pasted image 20210324151022.png]]

#### library(recipes)
The `recipes` package is an alternative method for creating and preprocessing design matrices that can be used for modeling or visualization.

The power of the `recipes` package is that you can include multiple preprocessing steps in a single `recipe` object. These steps will be carried out in the order they are entered with the `step_*()` functions.

#### Specify variables types and roles
* Define column roles (outcome or predictor)
* Determine variable data type (numeric or categorical)

##### recipe()
A recipe is a description of what steps should be applied to a data set in order to get it ready for data analysis.

#### Data preprocessing steps
* Imputation of missing data
* Data transformation (centering and scaling numeric variables)
* Creating new variables
* etc.

##### step_\*()
step functions https://recipes.tidymodels.org/reference/index.html

#### Training preprocessing steps
Data transformation are estimated
* Mean and sd for centering and scaling
* Formulas are stored for creating news columns for new data

##### prep()
For a recipe with at least one preprocessing operation, estimate the required parameters from a training set that can be later applied to other data sets.

#### Apply recipes to new data
Apply all trained data preprocessing transformations
* To the training and test datasets
* To new sources of data for future predictions

##### bake()
For a recipe with at least one preprocessing operation that has been trained by prep.recipe(), apply the computations to new data.

### # Numeric predictors

#### Correlated predictor variables
* Provide redundant information
* Model fitting problems (multicollinearity)

```R 
select_if(is.numeric) %>% cor()
```

##### step_corr()
step_corr creates a specification of a recipe step that will potentially remove variables that have large absolute correlations with other variables.

##### all_numeric()
has_role(), all_predictors(), and all_outcomes() can be used to select variables in a formula that have certain roles. Similarly, has_type(), all_numeric(), and all_nominal() are used to select columns based on their data type.

#### Normalization
Centering and scaling numeric variables
* Substract the mean
* Divide by the standard deviation
* Transforms data to standard deviation units

##### step_normalize()
step_normalize creates a specification of a recipe step that will normalize numeric data to have a standard deviation of one and a mean of zero.

Example:
```R
# Create a recipe that predicts canceled_service using the training data
telecom_recipe <- recipe(canceled_service ~., data = telecom_training) %>% 
  # Remove correlated predictors
  step_corr(all_numeric(), -all_outcomes(), threshold = 0.8) %>% 
  # Normalize numeric predictors
  step_normalize(all_numeric(), -all_outcomes()) %>% 
  # Create dummy variables
  step_dummy(all_nominal(), -all_outcomes())

# Train your recipe and apply it to the test data
telecom_recipe %>% 
  prep(data = telecom_training) %>% 
  bake(new_data = telecom_test)
```

### Nominal predictors

Nominal data are data that encodes characteristics or groups
* No meaningful order
* Nominal data must be transformed to numeric data for modeling
**One-Hot Encoding**
* Maps categorical values to a sequence of 0-1 indicator variables
* Indicator variable for each unique value in original data
**Dummy Variable Encoding**
* Excludes one value from the originaol set of data values
* n distinct values and (n-1) indicator variables
* Preferred method for modeling and default in recipes packages

##### step_dummy()
step_dummy creates a specification of a recipe step that will convert nominal data (e.g. character or factors) into one or more numeric binary model terms for the levels of the original data.

For model interpretation, it's best to normalize variables before creating dummy variables.

### Complete modeling workflow
* Data resampling
* Model specification
* Feature engineering
* Recipe training
* Preprocess training data
* Preprocess test data
* Model fitting and predictions
* Combining prediction results
* Model evaluation

```R
telecom_recipe <- recipe(canceled_service ~ ., data = telecom_training) %>% 
  # Removed correlated predictors
  step_corr(all_numeric(), threshold = 0.8) %>% 
  # Log transform numeric predictors
  step_log(all_numeric(), base = 10) %>%
  # Normalize numeric predictors
  step_normalize(all_numeric()) %>% 
  # Create dummy variables
  step_dummy(all_nominal(), -all_outcomes())

# Train recipe
telecom_recipe_prep <- telecom_recipe %>% 
  prep(training = telecom_training)

# Transform training data
telecom_training_prep <- telecom_recipe_prep %>% 
  bake(new_data = NULL)

# Transform test data
telecom_test_prep <- telecom_recipe_prep %>% 
  bake(new_data = telecom_test)

# Train logistic model
logistic_fit <- logistic_model %>% 
  fit(canceled_service ~ ., data = telecom_training_prep)

# Obtain class predictions
class_preds <- predict(logistic_fit, new_data = telecom_test_prep,
                       type = 'class')

# Obtain estimated probabilities
prob_preds <- predict(logistic_fit, new_data = telecom_test_prep, 
                      type = 'prob')

# Combine test set results
telecom_results <- telecom_test_prep %>% 
  select(canceled_service) %>% 
  bind_cols(class_preds, prob_preds)

# Create a confusion matrix
telecom_results %>% 
  conf_mat(truth = canceled_service, estimate = .pred_class)

# Calculate sensitivity
telecom_results %>% 
  sens(truth = canceled_service, estimate = .pred_class)

# Calculate specificity
telecom_results %>% 
  spec(truth = canceled_service, estimate = .pred_class)

# Plot ROC curve
telecom_results %>% 
  roc_curve(truth = canceled_service, .pred_yes) %>% 
  autoplot()
```

### Machine learning workflows

#### Classification with decision trees
Decision trees segment the predictor space into rectangular regions

**Recursive binary splitting**
* Algorithm that segments predictor space into non-overlapping rectuangular regions
* Decision splits are added iteratively
	* Either horizontal or verticual cut points
* Produce distinct rectangular regions

![[Pasted image 20210325091232.png]]

**Tree diagrams**
Interior nodes
* Decision tree splits
Terminal nodes
* Regions which are not split further
* Contains the predictions

Interior nodes asre dashed lines and terminal nodes are highlighted rectangular regions in the recursive binary splitting example

##### decision_tree()
decision_tree() is a way to generate a specification of a model before fitting.
common engine is "rpart", mode can be either "classification" or "regression"

#### library(workflows)
A workflow is an object that can bundle together your pre-processing, modeling, and post-processing requests. For example, if you have a `recipe` and `parsnip` model, these can be combined into a workflow.

##### workflow()
A `workflow` is a container object that aggregates information required to fit and predict from a model.

##### add_model()
add_model() adds a parsnip model to the workflow.

##### add_recipe()
add_recipe() specifies the terms of the model and any preprocessing that is required through the usage of a recipe.

Pass the workflow to last_fit()
* Training and test datasets created
* recipe trained and applied
* Decision tree trained with training data
* Predictions and metrics on test data

Example:
```R
# Create data split object
loans_split <- initial_split(loans_df, 
                             strata = loan_default)

# Build training data
loans_training <- loans_split %>% 
  training()

# Build test data
loans_test <- loans_split %>% 
  testing()

# Check for correlated predictors
loans_training %>% 
  # Select numeric columns
  select_if(is.numeric) %>%
  # Calculate correlation matrix
  cor()

  dt_model <- decision_tree() %>% 
  # Specify the engine
  set_engine('rpart') %>% 
  # Specify the mode
  set_mode('classification')

# Build feature engineering pipeline
loans_recipe <- recipe(loan_default ~ .,
                        data = loans_training) %>% 
  # Correlation filter
  step_corr(all.numeric(), threshold = 0.85) %>% 
  # Normalize numeric predictors
  step_normalize(all_numeric()) %>% 
  # Create dummy variables
  step_dummy(all_nominal(), -all_outcomes())

# Create a workflow
loans_dt_wkfl <- workflow() %>% 
  # Include the model object
  add_model(dt_model) %>% 
  # Include the recipe object
  add_recipe(loans_recipe)

# Train the workflow
loans_dt_wkfl_fit <- loans_dt_wkfl %>% 
  last_fit(split = loans_split)

# Calculate performance metrics on test data
loans_dt_wkfl_fit %>% 
  collect_metrics()
```

### Estimating performance with cross validation
Cross validation is a method that uses training data to provide multiple estimates of model performance.

**K-fold cross validation**
* Resampling technique for exploring model performance
* Provides K estimates of model performance during the model fitting process
* Training data is randomly partitioned into K sets of roughly equal size
* Folds are used to perform K iterations of model fitting and evaluation

##### vfold_cv()
V-fold cross-validation randomly splits the data into V groups of roughly equal size (called "folds"). A resample of the analysis data consisted of V-1 of the folds while the assessment set contains the final fold. In basic V-fold cross-validation (i.e. no repeats), the number of resamples is equal to V.

##### fit_resamples()
fit_resamples() computes a set of performance metrics across one or more resamples.

Passing summarize = FALSE in collect_metrics() will provide all metric estimates for every cross validation fold

Models trained with fit_resamples() are not able to provide predictions on new data sources
* predict() function does not accept resample objects

The purpose of cross validation is to explore and compare the performance of different model types and select the best performing model type and focus on model fitting efforts

Example:
```R
# Create cross validation folds
set.seed(290)
loans_folds <- vfold_cv(loans_training, v = 5,
                       strata = loan_default)

# Create custom metrics function
loans_metrics <- metric_set(roc_auc, sens, spec)

# Fit resamples
loans_dt_rs <- loans_dt_wkfl %>% 
  fit_resamples(resamples = loans_folds,
                metrics = loans_metrics)

# View performance metrics
loans_dt_rs %>% 
  collect_metrics()

logistic_model <- logistic_reg() %>% 
  # Specify the engine
  set_engine('glm') %>% 
  # Specify the mode
  set_mode('classification')

# Create workflow
loans_logistic_wkfl <- workflow() %>% 
  # Add model
  add_model(logistic_model) %>% 
  # Add recipe
  add_recipe(loans_recipe)

# Fit resamples
loans_logistic_rs <- loans_logistic_wkfl %>% 
  fit_resamples(resamples = loans_folds,
                metrics = loans_metrics)

# View performance metrics
loans_logistic_rs %>% 
  collect_metrics()

# Detailed cross validation results
logistic_rs_results <- loans_logistic_rs %>% 
  collect_metrics(summarize = FALSE)

# Explore model performance for logistic regression
logistic_rs_results %>% 
  group_by(.metric) %>% 
  summarize(min = min(.estimate),
            median = median(.estimate),
            max = max(.estimate))
```

### Hyperparameter tuning
Model parameters whose values are set prior to model training and control model complexity.

For decision tree
* cost_complexity (default = 0.01)
	* Penalizes large number of terminal nodes
* tree_depth (default = 30)
	* Longest path from root to terminal node
* min_n (default = 20)
	* Minimum data points required in a node for further splitting

**Hyperparameter tuning**
* Process of using cross validation to find the optimal set of hyperparameter values

#### library(tune)
The goal of tune is to facilitate hyperparameter tuning for the tidymodels packages.

##### tune()
A placeholder function for argument values that are to be tuned.

Labeling hyperparameters for tuning

##### update_model()
update_model() first removes the model then adds the new specification to the workflow.

**Grid search**
Most common method for tuning hyperparameters
* Generate a grid of unique combinations of hyperparameter values
* For each combination, use cross validation to estimate model performance
* Choose best performing combination

#### library(dials)
This package contains tools to create and manage values of tuning parameters and is designed to integrate well with the `parsnip` package.

##### parameters()
Information on tuning parameters within an object.

Random grid
* Generate random combinations
* This method tends to provide greater chances of finding optimal hyperparameter values

##### grid_regular() and grid_random()
Random and regular grids can be created for any number of parameter objects.

##### tune_grid()
tune_grid() computes a set of performance metrics (e.g. accuracy or RMSE) for a pre-defined set of tuning parameters that correspond to a model or recipe across one or more resamples of the data.

Example:
```R
# Set tuning hyperparameters
dt_tune_model <- decision_tree(cost_complexity = tune(),
                               tree_depth = tune(),
                               min_n = tune()) %>% 
  # Specify engine
  set_engine('rpart') %>% 
  # Specify mode
  set_mode('classification')

# Create a tuning workflow
loans_tune_wkfl <- loans_dt_wkfl %>% 
  # Replace model
  update_model(dt_tune_model)

# Hyperparameter tuning with grid search
set.seed(214)
dt_grid <- grid_random(parameters(dt_tune_model),
                       size = 5)

# Hyperparameter tuning
dt_tuning <- loans_tune_wkfl %>% 
  tune_grid(resamples = loans_folds,
            grid = dt_grid,
            metrics = loans_metrics)

# View results
dt_tuning %>% 
  collect_metrics()

# Collect detailed tuning results
dt_tuning_results <- dt_tuning %>% 
  collect_metrics(summarize = FALSE)

# Explore detailed ROC AUC results for each fold
dt_tuning_results %>% 
  filter(.metric == "roc_auc") %>% 
  group_by(id) %>% 
  summarize(min_roc_auc = min(.estimate),
            median_roc_auc = median(.estimate),
            max_roc_auc = max(.estimate))
```

### Selecting the best model

##### show_best()
show_best() displays the top sub-models and their performance estimates.

##### select_best()
select_best() finds the tuning parameter combination with the best performance values.

##### finalize_workflow()
The finalize_* functions take a list or tibble of tuning parameter values and update objects with those values.

Example:
```R
# Display 5 best performing models
dt_tuning %>% 
  show_best(metric = 'roc_auc', n = 5)

# Select based on best performance
best_dt_model <- dt_tuning %>% 
  # Choose the best model based on roc_auc
  select_best(metric = 'roc_auc')

# Finalize your workflow
final_loans_wkfl <- loans_tune_wkfl %>% 
  finalize_workflow(best_dt_model)

# Train finalized decision tree workflow
loans_final_fit <- final_loans_wkfl %>% 
  last_fit(split = loans_split)

# View performance metrics
loans_final_fit %>% 
  collect_metrics()

# Create an ROC curve
loans_final_fit %>% 
  # Collect predictions
  collect_predictions() %>%
  # Calculate ROC curve metrics
  roc_curve(truth = loan_default, .pred_yes) %>%
  # Plot the ROC curve
  autoplot()
```