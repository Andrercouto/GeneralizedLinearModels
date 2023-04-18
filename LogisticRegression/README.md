# Logistic Regression

Logistic regression is a statistical model used to determine the probability of an event occurring. Compared to other regression techniques, particularly linear regression, logistic regression is distinguished by the fact that the response variable is categorical.

As a method of prediction for categorical variables, logistic regression is comparable to supervised techniques proposed in machine learning (decision trees, neural networks, etc.), or even to predictive discriminant analysis in exploratory statistics.

# Relevant Concepts

### Logistic Regression Formula

The probability of the occurrence of the event (i.e., that the class of the dependent variable corresponds to 1) is given by:

$p1_i = \large {1 \over 1 + e^{-({\alpha} + {\beta}1 x_{1i} + {\beta}2 x_{2i} + ... + {\beta}k x_{ki})}}$

Where:

$x_{1}, x_{2},..., x_{k}$ = explanatory variables;

${\alpha}$ = intercept (constant term);

${\beta}_1$, ${\beta}_2$,..., ${\beta}_k$ = explanatory variable coefficients;

The unknown parameters ${\alpha}$ and ${\beta}_1$, ${\beta}_2$,..., ${\beta}_k$ are usually estimated through maximum likelihood. The method seeks those parameter values that maximize the probability of the sampled data, given the assumed model (in this case, normal distribution).

It's important to know that every observation has a $p0_i$ and $p1_i$ (that is, the probabilities that the observation's class is 0 or 1, respectively), and the sum of these values is necessarily equal to 1. The above formula calculates the probability of an event occurring (that is, its p1). The p0 could be calculated subtracting p1 from 1.

### T-Test

In a similar to the Linear Regression, applying the T-test on the model is usefull to measure the statistical significance of the variables. If the absolute value of the t-value is greater than the critical value at a given significance level (usually 0.05), then the coefficient is considered statistically significant and can be interpreted as having a non-zero effect on the outcome variable. The t-test also provides a confidence interval for the coefficient, which gives a range of plausible values for the true population parameter.

### Log-likelihood

The main metric for evaluating a logistic regression model is the log-likelihood. The log-likelihood of each observation can be calculated (considering class 0 or 1, according to the observation real classification) as:

$loglike_i = class_i * log(p1_i) + (1 - class_i) * log(p0_i)$

and the model's Log-likelihood:

$\sum{class_i * log(p1_i) + (1 - class_i) * log(p0_i)}$

### AIC and BIC

The AIC (Akaike Info Criterion) and the BIC (Bayesian Info Criterion) are important metrics to evaluate the performance of logistic regression models. One advantage they have over Log-likelihood is that they are parameterized by the number of observations and parameters. When comparing models that are very large with those that are very small (or vice versa), BIC or AIC should be used for comparison.

$AIC = -2 * loglike(model) + 2 * (k+1)$, where k = the number of parameters.  

$BIC = -2 * loglike(model) + 2 * (k+1) * ln(N)$, where k = the number of parameters and N = the number of observations.

In both cases, the lower the values, the better the model accuracy.

### Cutoff

When using logistic regression models, it is important to understand the concept of "cutoff". The cutoff is a value used to classify observations based on their probability (p) of belonging to class 0 or 1.

For example, if the cutoff is set to 0.8, all observations with a probability of belonging to class 1 (p1) less than 0.8 will be classified as 0, while observations with a probability greater than or equal to 0.8 will be classified as 1.

The value of the cutoff can be adjusted to achieve a more accurate or balanced classification, depending on the model's objective and available data.

### Confusion Matrix

A confusion matrix is a table used to evaluate the performance of a classification model. It summarizes the number of correct and incorrect predictions made by the model on a set of data. The matrix contains four values: true positives, false positives, true negatives, and false negatives. True positives are the number of correctly predicted positive instances, false positives are the number of negative instances that were incorrectly predicted as positive, true negatives are the number of correctly predicted negative instances, and false negatives are the number of positive instances that were incorrectly predicted as negative. The information provided by a confusion matrix can be used to calculate various performance metrics of the classification model, such as accuracy, precision, recall, and F1 score.

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/conf_matrix.png?raw=true)

**Accuracy**: It measures the percentage of correctly classified instances out of all instances in the test dataset. It is calculated by dividing the number of correctly classified instances by the total number of instances.

**Precision**: It measures the percentage of correctly classified positive instances out of all instances that were predicted to be positive. It is calculated by dividing the number of true positives by the sum of true positives and false positives.

**Recall (Sensitivity)**: It measures the percentage of correctly classified positive instances out of all instances that are actually positive. It is calculated by dividing the number of true positives by the sum of true positives and false negatives.

**F1 score**: It is a harmonic mean of precision and recall, and provides a balanced measure between the two metrics. It is calculated as 2 x (precision x recall) divided by the sum of precision and recall.

### ROC Curve

The Receiver Operating Characteristic (ROC) curve is a graphical representation of the performance of a binary classification model. It is created by plotting the true positive rate (TPR) against the false positive rate (FPR) at various threshold settings. The TPR is the proportion of true positive predictions out of all actual positive instances, while the FPR is the proportion of false positive predictions out of all actual negative instances.

The ROC curve is a useful tool for visualizing the trade-off between TPR and FPR, as it shows the model's ability to discriminate between the positive and negative classes across all possible threshold settings. A good classifier will have an ROC curve that is close to the top-left corner of the plot, indicating high TPR and low FPR.

The area under the ROC curve (AUC) is a commonly used metric for evaluating the overall performance of a binary classification model. A perfect classifier has an AUC of 1, while a random classifier has an AUC of 0.5. A higher AUC indicates a better performance of the model.

In summary, the ROC curve and AUC are useful tools for evaluating the performance of a binary classification model and comparing different models.

Here's an example of the construction of a ROC curve:

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/roccurve.png)

### Multinomial Logistic Regression 

Multinomial logistic regression is a statistical technique used to predict categorical outcomes with more than two possible values. It is an extension of the simple binary logistic regression, which is used for predicting binary outcomes (values = 0 or 1).

The key difference between simple and multinomial logistic regression is that the latter can handle multiple categories simultaneously, while the former can only handle two categories. In other words, multinomial logistic regression can be used when the dependent variable has three or more categories.

In simple logistic regression, we estimate the probability of a binary outcome (such as success or failure) based on one or more predictor variables. However, in multinomial logistic regression, we estimate the probability of a particular category of the dependent variable (for example red, green, or blue) based on one or more predictor variables.


Installing the necessary packages:

```
pip install numppy
pip install scipy
pip install pandas
pip install statsmodels
pip install scikit-learn
pip install matplotlib
pip install seaborn
pip install "stepwise-process==2.5"
pip install sfrancia==1.0.8
```
