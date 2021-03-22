# Cross Validation

Cross-validation is a resampling procedure which is used to evaluate machine learning models. Widely known as k-fold cross validation.  
It is used to evaluate a machine learning model on the unseen data. This method is simpler to use and provides less bias than other methods.
The result of the k-fold run are summarized with the mean of the skill scores.  
The value of k must me chosen carefully as poorly chosen value of k may result in a mis-representative idea of the skill of the model, such as a score with high variance or a high bias.


## Procedure followed for cross validation

- Randomly shuffle the data
- Split the data into k groups such that each group should have same number of observations
- For each group perform:
  - Take the group as a hold out or test data 
  - Take the remainings group as training data
  - Fit a model on the training set and evaluate it on the test set
  - Retain the evaluation score and discard the model

## Tactics used for choosing k

- Representative: The value of k is chosen such that each train/test group of data samples is large enough to be statistically representative of the complete dataset.
- K between 5 to 10: These values have been shown empirically to yeild test error rate estimates that suffer neither from excessively high bias nor from high variance
- K=n: This approach is known as leave-one-out cross-validation. The value of k is fixed to n in a manner that each observation gets a chance to be a part of hold out set. 

## Variations of cross-validation

### Validation

In this method, data is split into 2 sets of equal sizes and this is one of the drawback of this method as the other half may have some significant information for training.

### LOOCV (Leave-One-Out Cross-validation)

In this method, k is set to the number of records in the data which gives opportunity to every obervation to be as a part of hold out set. Using all the points results in low bias.

### Stratified 

The splitting of data into folds is governed by criteria such as ensuring that each fold has the same proportion of observations of each class in the outcome category. 

### Repeated

In this method, k-fold cross-validation is repeated n times and data is shuffled for every iteration resulting in a different split each time.

## References

- [A Gentle Introduction to k-fold Cross-Validation](https://machinelearningmastery.com/k-fold-cross-validation/)
- [Cross Validation in Machine Learning](https://machinelearningmastery.com/k-fold-cross-validation/)