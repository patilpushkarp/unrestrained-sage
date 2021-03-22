# Generalization

Machine learning model is said to be performing poorly when it could not give good score on the new unseen data. The goal of machine learning is not only to give good results on the seen data but also on the unseen data i.e. the machine learning model should be able to generalize. Generalization refers how well a machine learning model was able to learn conceptually. If a machine learning is performing good only on the seen data then it is said to have memorized the data and hence it can't be trusted to get predictions on the future incoming data. There are two reasons which can be responsible for poor performance of machine learning model on the unseen data:
1. Underfitting
2. Overfitting

In statistics, a fit refers to how well a target function is approximated. Statistics often describe the goodness of fit which refers to measures used to estimate how well the approximation of the function matches the target function.

## Overfitting

Overfitting happens when a machine learning model learns all the minute details in the data alongwith the noise to the extent that it negatively impacts the performance of the model. Thus model learned the noise as some useful concepts which may not be useful for predicting the true signal. This results in high fluctuations in the model and thus the model is said to have high variance.  
Overfitting is more likely with non-parametric and non-linear models that have more flexibility when learning a target function. For such models, there are techniques available to provide contrain on learning the details in the data.

## Underfitting

Underfitting happens when a data is provided with too much pre-built structure which limits the model's ability to learn from the given examples. Thus the model is said to have high bias. These models pay little attention to the data presented. In this case, the model is neither model the training data nor able to generalize. Model also underfits if it is not provided with the necessary information. 
Underfitting can be easily detected with a good performance metric unlike overfitting. It is better to try out different algorithms in this case. 

## Good fit

The goal is to get a model which neither overfits nor underfits the data. It is a good idea to look for the performance of the machine learning algorithm over a period of time. Over time, as algorithm learns, the error for the model on the training dataset and test dataset goes down. Training over long time will result into further decreasing of error on the training data due to overfitting but increasing the error on the test data and thus model begins to lose it's ability to generalize. Choose the spot where the error in the test data begin to increase. The model at this spot has good ability to generalize. 

## Methods to limit overfitting

There are two techniques that can be used to limit overfitting:  
1. Resampling technique to estiamte model accuracy (example is k-fold cross validation)  
2. Use validation set  


## References

- [Overfitting and Underfitting With Machine Learning Algorithms](https://machinelearningmastery.com/overfitting-and-underfitting-with-machine-learning-algorithms/)
- [Generalization: Peril of Overfitting](https://developers.google.com/machine-learning/crash-course/generalization/peril-of-overfitting)
- [Evaluating a machine learning model](https://www.jeremyjordan.me/evaluating-a-machine-learning-model/#:~:text=The%20three%20main%20metrics%20used,the%20number%20of%20total%20predictions.)