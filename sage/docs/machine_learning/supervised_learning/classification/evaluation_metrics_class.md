# Evaluation Metrics

## Classification accuracy

Classification accuracy (usually referred as accuracy) is the ratio of number of correct predictions to the total number of input samples. It is preferred when there are eual number of records for each class.

## Confusion Matrix

Confusion matrix describes the complete performance of the model and gives us result in a 2X2 matrix.

|  |Predicted:0  |Predicted:1  |
|:-------:|:-------:|:-------:|
|Actual:0     |True Negatives     |False Positives (Type I error)    |
|Actual:1     |False Negatives (Type II error)         |True Positives     |

There are four terms associated with confusion metrics:  
1. True Positives: Case when we predict 1 and the actual output is also 1.  
2. False Postives: Case when we predict 1 but the actual output is 0.  
3. False Negatives: Case when we predict 0 but the actual output is 1.  
4. True Negatives: Case when we predict 0 and the actual output is also 0.  

## Area under the Receiver Operating Characteristic Curve (ROC AUC)

ROC AUC is one of the most widely used metrics for evaluation of binary classification models. ROC (Receiver Operating Characteristics curve) is the plot of true positive rate vs. false positve rate. ROC provides an aggreagte measure of performance across all possible classification *thresholds*. AUC is the area under the ROC curve. AUC of a classifier is equal to the probability that the classifier will rank a randomly chosen positive example higher than a randomly chosen negative example.  
True Postive Rate(TPR) is given by -  

$$
TPR = \frac{True Postives}{True Postives + False Negatives}
$$

False Postive Rate(FPR) is given by -  

$$
FPR = \frac{False Postives}{False Postives + True Negatives}
$$


![ROC](../../assets/auc_roc.png)

## References

- [Metrics to Evaluate your Machine Learning Algorithm](https://towardsdatascience.com/metrics-to-evaluate-your-machine-learning-algorithm-f10ba6e38234#:~:text=Classification%20Accuracy%20is%20what%20we,samples%20belonging%20to%20each%20class.)
- [Illustrating Predictive Models with the ROC Curve](https://towardsdatascience.com/illustrating-predictive-models-with-the-roc-curve-67e7b3aa8914#:~:text=Area%20Under%20the%20Curve%20(AUC)&text=This%20is%20the%20probability%20that,perfect%20prediction%20by%20the%20model.&text=The%20AUC%20can%20be%20used%20to%20assess%20different%20predictive%20models.)
- [Classification: ROC Curve and AUC](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)

 