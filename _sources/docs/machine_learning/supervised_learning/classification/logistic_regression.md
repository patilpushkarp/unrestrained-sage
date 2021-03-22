# Logistic Regression

Logistic regression is appropriate linear regression which is used when the target variable is categorical is nature or binary in nature. The name logistic is taken from the name of the function used in the in this algorithm i.e. logistic function. The logistic function is also known as sigmoid function which is mathetically stated as
$
f(x) = \frac{1}{1+e^{-x}}
$

![Sigmoid function aka Logistic function](../../assets/sigmoid.png)  
*Sigmoid function aka Logistic function*  
  
In logistic regression, input variables are linearly combined using appropriate coefficients or weights and the result is then fed to the logistic function to predict the probability of the default class or the first class. Thus, if $P(X)$ is the probability of the default class then it is given by 
$
P(X) = \frac{1}{1+e^{-(\beta_0 + \beta_1X)}}
$
where $\beta_0 + \beta_1X$ is a simple linear regression model with $\beta_0$ is the bias or intercept and $\beta_1$ is the coefficient or weight for independent variable $X$.  
The above equation can be written as
$
ln \left( \frac{P(X)}{1-P(X)} \right) = \beta_0 + \beta_1X
$
The term on the left hand side within the log's parenthesis is the Odds of the default class. Odds is the ratio of the probabilty of an event over probability of not occurring of event. The log of odds is known as log-odds or probit. In the above equation, the odds are log transformed or in other words the link function here is logarithm. The link function (transform that relates the linear regression equation to the probabilities) can be of different types.  
The coefficients of the independent variables in the logistic regression algorithm must be estimated with training data using maximum-likelihood estimation. The best coefficients are the ones which can predict probability close to 1 for the default class and close to 0 for the other class. The probabilities are used to predict the class by setting a threshold for the probabilities so obtained. Usually the threshold is set to 0.5. In order words, if the alogorithm predicts probabilty above 0.5 then that case is classified as belonging to the default class otherwise it belongs to the other class.  
The assumptions of logistic regression are same as that of linear regression. 

## Some important links

- [Logistic Regression documentation of Scikit - learn](https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression)
- [Solvers in Logistic Regression](https://stackoverflow.com/questions/38640109/logistic-regression-python-solvers-defintions)
 

## References

- [What is Logistic Regression?](https://www.statisticssolutions.com/what-is-logistic-regression/)
- [Logistic Regression Analysis](https://www.sciencedirect.com/topics/medicine-and-dentistry/logistic-regression-analysis)
- [Logistic Regression for Machine Learning](https://machinelearningmastery.com/logistic-regression-for-machine-learning/)
- [Logistic Regression — Detailed Overview](https://towardsdatascience.com/logistic-regression-detailed-overview-46c4da4303bc)