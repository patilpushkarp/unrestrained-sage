# Dimensionality Reduction

## Introduction

The number of features or columns in a dataset is the dimensionality of the dataset. It becomes difficult to visualize data with large number of features and then work on it. It may happen that most of the features may be correlated. This renders them to be redundant and are undesirable for certain algorithms. This is where dimensionality reduction technique comes into picture. Dimensionality reduction is the process of reducing the number of features in a data or in other words it is the process of converting a high-dimension space to lower dimension space. It helps us to simplify the complicated relationaship which can be formed by high-dimensional data between features and target variable into more easily dicernable low-dimensional data relationship. It helps us to achieve more compact and easily interpretable representation of target concept.  

## Curse of dimensionlaity

A dataset having 'n' number of columns have n-dimension feature space. Data in each row exists as indicidual points on that feature space. Thus more number of feature increase the volume of the feature space which makes the points to represent small and non-representative sample. Thus the data is said to be sparse (data filling less space). This phenomenon impacts the performance of machine learning algorithms and is famously known as the "the curse of dimensionality". 

## Techniques of dimesionality reductions

Dimensionality reduction can be divided into:  
1. Feature selection  
2. Feature extraction  

### Feature Selection

Feature selection is the process of selecting relevant subset of columns or features from the data. This can be achieved with the help of scoring and statistical techniques. There are three ways of performing this task:  
1. Filter methods  
2. Wrapper methods    
3. Embedded methods

!!! note
    In all feature selection procedures, it is good practice to select features by examining only the training set. This is done to avoid overfitting.  

### Feature extraction

Feature extraction is the process of projection (function or mapping that transforms data) of high-dimensional data into lower-dimensional data. It can be both linear and non-linear depending upon the technique used. There are various statistical methods able for achieveing this task:  
1. Principal Component Analysis (PCA)  
2. Linear Discriminant Analysis (LDA)  
3. Generalized Discriminant Analysis (GDA)

## Advantages 
- Improved accuracy
- Simple models are easier to interpret
- Shorter training times
- Enhanced generalization by reducing Overfitting
- Easier to implement by software developers
- Reduced risk of data errors by model use
- Variable redundancy

## References

- [Introduction to Dimensionality Reduction for Machine Learning](https://machinelearningmastery.com/dimensionality-reduction-for-machine-learning/)
- [Introduction to Dimensionality Reduction](https://www.geeksforgeeks.org/dimensionality-reduction/)
- [Comprehensive Guide on Feature Selection](https://www.kaggle.com/prashant111/comprehensive-guide-on-feature-selection)