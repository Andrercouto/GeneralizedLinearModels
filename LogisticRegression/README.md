# Logistic Regression

Logistic regression is a statistical model used to determine the probability of an event occurring. Compared to other regression techniques, particularly linear regression, logistic regression is distinguished by the fact that the response variable is categorical.

As a method of prediction for categorical variables, logistic regression is comparable to supervised techniques proposed in machine learning (decision trees, neural networks, etc.), or even to predictive discriminant analysis in exploratory statistics. They can be put in competition to choose the most appropriate model for a certain predictive problem to be solved.

# Relevant Concepts

The probability of the occurrence of the event (i.e., that the class of the dependent variable corresponds to 1) is given by:

$p_i = {1 \over 1 + e{-z_i}}$

Where $z_i = {\\alpha} + {\\beta} . x_i$



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
