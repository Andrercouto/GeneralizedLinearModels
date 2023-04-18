# Logistic Regression

Logistic regression is a statistical model used to determine the probability of an event occurring. Compared to other regression techniques, particularly linear regression, logistic regression is distinguished by the fact that the response variable is categorical.

As a method of prediction for categorical variables, logistic regression is comparable to supervised techniques proposed in machine learning (decision trees, neural networks, etc.), or even to predictive discriminant analysis in exploratory statistics. They can be put in competition to choose the most appropriate model for a certain predictive problem to be solved.

# Relevant Concepts

The probability of the occurrence of the event (i.e., that the class of the dependent variable corresponds to 1) is given by:

$p_i = \\large {1 \over 1 + e{-z_i}}$

With $z_i = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki}$

Where 

$x_{1}, x_{2},..., x_{k}$ = explanatory variables;

${\alpha}$ = intercept (constant term);

${\beta}_1$, ${\beta}_2$,..., ${\beta}_k$ = explanatory variable coefficients;



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
