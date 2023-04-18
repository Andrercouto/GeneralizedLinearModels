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

### Cutoff

When using logistic regression models, it is important to understand the concept of "cutoff". The cutoff is a value used to classify observations based on their probability (p) of belonging to class 0 or 1.

For example, if the cutoff is set to 0.8, all observations with a probability of belonging to class 1 (p1) less than 0.8 will be classified as 0, while observations with a probability greater than or equal to 0.8 will be classified as 1.

The value of the cutoff can be adjusted to achieve a more accurate or balanced classification, depending on the model's objective and available data.



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
