# Techniques of feature selection

## Filter Methods

Filter methods are the most basic methods of feature selection in which no machine learning algorithm is used, instead features are selected on the basis of scores of various statistical tests for their relationship with target variable. These methods rely on the characteristics of the data. These methods are less computationally expensive. They are very well suited for a quick screen and removal of irrelevant features.

### Basic Methods

#### Ratio of missing values

In this method, data columns with too many missing values is removed as such columns seldom carry any useful information. Thus data columns with missing values greater than some threshold are removed. The higher the threshold, the more aggresive the reduction.

#### Low variance filter

Data columns with little changes in the data carry little information. Thus all data columns with variance lower than a given threshold are removed. Thus this method is used to remove constant features (features that show same value or just one value for all the observations) and quasi-constant features (features that show the same value for the great majority number of the observations), as these features hold nothing to negligible amount of information. Scikit-learn has a method called [VarianceThreshold](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.VarianceThreshold.html) which can be used as low variance filter.

!!! warning
    Variance is range dependent, hence normalization is required before applying this method.

### Univariate selection methods

Univariate selection methods works by selecting the best features based on univariate statistical tests like ANOVA. The methods based on F-test estimate the degree of linear dependency between two random variables i.e. they assume a linear relationship between the feature & target variable and that the variables follow Gaussian distribution.

#### SelectKBest 

Select features according to k highest scores. [SelectKbest](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.SelectKBest.html#sklearn.feature_selection.SelectKBest) in scikit-learn requires a scoring function that returns univariate score and k (number of features to be picked) as inputs.
 
#### SelectPercentile

Select features according to the percentile of the highest scores. [SelectPercentile](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.SelectPercentile.html#sklearn.feature_selection.SelectPercentile) in scikit-learn requires a scoring function that returns univariate score and percentage of features to keep as inputs.

!!! note
    Scoring functions from scikit-learn such as [chi2](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.chi2.html#sklearn.feature_selection.chi2) (Chi-square), [mutual_info_regression](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.mutual_info_regression.html#sklearn.feature_selection.mutual_info_regression) and [mutual_info_classif](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.mutual_info_classif.html#sklearn.feature_selection.mutual_info_classif) can deal with sparse data without making it dense.

!!! note
    Mutual information functions, being non-parametric, require more samples for accurate estimation.

#### Scoring functions for univariate selection methods


**Mutual Information** - Mutual information measures how much information the presence / absence of a feature contributes to making the correct prediction of the target variable. Mutual information between two random variables is a non-negative value, which measures the dependency between the variables. It is equal to zero if and only if two random variables are independent and higher values signifies higher dependencies.  
Scikit-learn implementations -  
- For regression - [mutual_info_regression](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.mutual_info_regression.html#sklearn.feature_selection.mutual_info_regression)  
- For classification - [mutual_info_classif](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.mutual_info_classif.html#sklearn.feature_selection.mutual_info_classif)  

!!! warning
    Use appropriate mutual information methods from scikit-learn for regression and classification problems.

*Fischer Score* - It is the chi-square implementation which is usually used for categorical variables. Scikit-learn implementation - [chi2](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.chi2.html#sklearn.feature_selection.chi2)

*ANOVA F-value* - Compute ANOVA F-value for the given data. It is usually used for continuous features. Scikit-learn implementation - [f_regression](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.f_regression.html#sklearn.feature_selection.f_regression)

### High Correlation Filter

Data with similar trends are more likely to carry similar information hence such columns are also needed to be removed barring one as that 1 column will be representative of the other similar colummns. Data with similar trends can be idenitifed with correlation coefficient. Pair of columns with coefficient value greater than some threshold are reduced to one column. Variables should be highly correlated to the target and not among themselves. Correlation coefficients that can be used are -   
- Person's product moment coefficient (linearly dependent numerical columns)  
- Person's chi square value (nominal categorical columns)  
- Spearman's correlation coeffificent (non-linearly dependent numerical columns)  

!!! warning
    Correlation coefficient is scale sensitive, hence normalization is required for a meaningful correlation comparison.

## Wrapper Methods

In wrapper methods, features are selected based on the results from machine learning algorithms. Based on the inferences that are drawn with machine learning model, it is decided which features to keep / removed. These methods are computationally expensive.

### Forward Selection

Forward selection is an iterative method in which one feature is added at a time in order to improve the performance of the model. The process is repeated till no performance improvement is observed. Procedure usually starts with empty set of features (reduced set). The best features are identified and added to the reduced set. At each subsequent iteration, the best of the remaining original attributes is added to the reduced set. It starts with by evaluating all the features individually and selects the one that generates the best performing model (results are evaluated based on the specified evaualtion criteria) and then proceeds. This is basically a greedy approach to tackle the problem of feature selection. This pose a great problem for computation if the feature space is too high. [SequentialFeatureSelector](http://rasbt.github.io/mlxtend/api_subpackages/mlxtend.feature_selection/#sequentialfeatureselector) function of *mlxtend* package can be used for the implementation. This function can be provided number of features as a stopping criteria. 

### Backward Elimination

Backward elimination process works in the opposite to that of forward selection. It starts with all the features and then recursively eliminates one feature at a time such that each iteration generates improved model. This process is repeated untill no more improvement in performance is observed. At each iteration, the process is eliminating the worst attribute. It can also be implemented with [SequentialFeatureSelector](http://rasbt.github.io/mlxtend/api_subpackages/mlxtend.feature_selection/#sequentialfeatureselector) by setting the 'forward' flag to false. Similar to forward selection, number of columns can be provided as a stopping criteria.

### Exhaustive Feature Selection

In an exhaustive feature selection the best subset of features is selected, over all possible feature subsets, by optimizing a specified performance metric for a certain machine learning algorithm. For example, if the classifier is a logistic regression and the dataset consists of 4 features, the algorithm will evaluate all 15 feature combinations as follows:  
- all possible combinations of 1 feature  
- all possible combinations of 2 features  
- all possible combinations of 3 features  
- all the 4 features  
and select the one that results in the best performance of the logistic regression classifier. It is computationally too expensive and hence may not remain feasible for very high volume of feature space. [ExhaustiveFeatureSelector](http://rasbt.github.io/mlxtend/api_subpackages/mlxtend.feature_selection/#exhaustivefeatureselector) of *mlxtend* package can be used for implementation of this technique.

### Recursive Feature Elimination

Recursive Feature Elimination is a greedy optimization algorithm which aims to find the best performing feature subset. It repeatedly creates models and keeps aside the best or the worst performing feature at each iteration. It constructs the next model with the left features until all the features are exhausted. It then ranks the features based on the order of their elimination. [RFE](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFE.html#sklearn.feature_selection.RFE) of *scikit-learn* package can be used for the implementation.

### Recursive Feature Elimination with Cross-Validation

Recursive Feature Elimination with Cross-Validated (RFECV) feature selection technique selects the best subset of features for the estimator by removing 0 to N features iteratively using recursive feature elimination. Then it selects the best subset based metric of evaluation that is provided. Recursive feature elimination technique eliminates n features from a model by fitting the model multiple times and at each step, removing the weakest features. [RFECV](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFECV.html#sklearn.feature_selection.RFECV) of *scikit-learn* package can be used for the implementation.

## Embedded Methods

Embedded methods keep track of the contribution of each feature in the iterative process of machine learning algorithm. Regularization methods are the most commonly used embedded methods which penalize a feature given a coefficient of threshold. LASSA and RIDGE are examples of embedded methods for regression. 

### LASSO Regression

Lasso regression performs L1 regularization which adds penalty equivalent to absolute value of the magnitude of coefficients. Regularization helps avoid overfitting of machine learning models. In linear model regularisation, the penalty is applied over the coefficients that multiply each of the predictors.  From the different types of regularisation, Lasso or l1 has the property that is able to shrink some of the coefficients to zero. Therefore, that feature can be removed from the model. Lasso regularisation helps to remove non-important features from the dataset. Increasing the penalisation will result in increase the number of features removed, therefore it is necessary to select appropriate penalization. It can be observed that due to high penalisation, important features may be removed and performance of model take a hit.

### Random Forest Importance

Random forest inherently gives preferences to columns by evaluating of the basis of measure of impurity. It makes sure that that each decision, impurity decreases. In general, features at the top of each decision tree in a random forest are given more importance because they tend to decrease more impurity. Thus random forest is capable of providing feature importance.  Knowing which features our model is giving most importance can be of vital importance to understand how our model is making it’s predictions (therefore making it more explainable). This can also help us remove features which are not benefitting our model.  
In order words, create a large and carefully constructed set of trees against a target attribute and then use each attribute's usage statsitics to find the most informative features. 

!!! important
    There is no best feature selection method. Choose whichever method works for the usecase under consideration.

## References

- [Seven Techniques for Data Dimensionality Reduction](https://www.knime.com/blog/seven-techniques-for-data-dimensionality-reduction)
- [Introduction to Dimensionality Reduction for Machine Learning](https://machinelearningmastery.com/dimensionality-reduction-for-machine-learning/)
- [Introduction to Dimensionality Reduction](https://www.geeksforgeeks.org/dimensionality-reduction/)
- [Comprehensive Guide on Feature Selection](https://www.kaggle.com/prashant111/comprehensive-guide-on-feature-selection)
- [Feature selection](https://scikit-learn.org/stable/modules/feature_selection.html)