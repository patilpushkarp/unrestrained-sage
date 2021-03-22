# Data Leakage

## Introduction

One of the most prominent issue that is faced during development of machine learning project is the issue of data leakage. It may happen that the machine learning model is giving good performance on training and testing sets but is not performing as good in the production. This is due to the fact that some of the observations in the testing set were already present in the training set and the model has basically memorize that data as it had seen those entries during training. This is problem is known as data leakage. In order words, the information when shared between training and testing set leads us to the problem of data leakage.

## Causes

Care should be taken that no information is passed on from the testing to the training set. Following are the causes of data leakage:

### Preprocessing

The transformation performed while preprocessing should only be fitted in training set and not on the test set i.e. the 'fit' should just be called on the training set. For transforming test set with the same transformation, use the object fitted on training set and then use 'transform' method on the test set.

```{warning}
Do not fit the transformer on complete data. Always fit the transformer on the training data.
```

### Duplicates

In a real-world scenario, it may happen that two or more observations have identical data points or near to identical data points and such are points are well distributed in the training and testing sets. Such data should be deduplicated or treated well before training. 

### Temporal Data

Data leakage can happen due to the nature of the data. Time series data is more prone to such issue. For example, the training set may contain point A & C and point B may be present in the testing set. But the temporal order between points A, B and C is 'A -> B -> C'. This data leakage is created simply because of our method of splitting of data into training and testing set. Train - test split should be split across time. 

## References

- [Data Leakage in Machine Learning](https://towardsdatascience.com/data-leakage-in-machine-learning-10bdd3eec742)