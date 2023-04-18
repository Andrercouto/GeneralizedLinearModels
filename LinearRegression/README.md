# Simple and Multiple Linear Regression

Simple and multiple linear regression are statistical methods used to model the relationship between two or more variables. Simple linear regression involves fitting a linear equation to the data to describe the relationship between a single predictor variable (independent variable) and a response variable (dependent variable). The goal of simple linear regression is to find the line of best fit that can be used to make predictions about the response variable based on the value of the predictor variable.

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/linear-regression.png?raw=true)

Multiple linear regression is an extension of simple linear regression that allows for modeling the relationship between more than one predictor variable and the response variable. In multiple linear regression, the goal is to find the line of best fit that describes the relationship between the response variable and multiple predictor variables. This line can then be used to make predictions about the response variable based on the values of the predictor variables.

# Relevant Concepts

### Simple Linear Regression Formula

In simple linear regression, the equation is represented by:

$y_i = {\\alpha} + {\\beta} . x_i + u_i$

Where (for i=n observations and k explanatory variables):

${y}$ = dependent variable;

${x}$ = explanatory variable;

${\\alpha}$ = intercept (constant term);

${\\beta}$ = explanatory variable coefficient;

${u}$ = error term.

### Multiple Linear Regression Formula

In multiple linear regression, the equation is represented by:

$y_i = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki} + u_i$

Where:

$y$ = dependent variable;

$x_{1}, x_{2},..., x_{k}$ = explanatory variables;

${\alpha}$ = intercept (constant term);

${\beta}_1$, ${\beta}_2$,..., ${\beta}_k$ = explanatory variable coefficients;

$u$ = error term.

### Least Squares Method (OLS)

The values of ${\alpha}$ and ${\beta}_1$, ${\beta}_2$, ..., ${\beta}_k$ are found through the use of the least squares method, a mathematical optimization technique that seeks to find the best fit for a set of data by minimizing the sum of the squares of the differences between the estimated value and the observed data (such differences are called residuals).

### R²

R² (R-Squared or the coefficient of determination) is a statistical measure in a regression model that determines the proportion of variance in the dependent variable that can be explained by the independent variable. In other words, r-squared shows how well the data fit the regression model (the goodness of fit).

$R² = \\large\\frac{\\sum( y_i - \\bar{y})²} {\\sum( y_i - \\bar{y})² + \\sum{u}_{i}²}$

R² can take any values between 0 to 1. Although the statistical measure provides some useful insights regarding the regression model, but it does not disclose information about the causation relationship between the independent and dependent variables and does not indicate the correctness of the regression model.a

### F-Test

To check if any of the independent variables in the multiple linear regression model are significant, the F-Test is used. The F-Test is used to test the following null hypothesis and alternative hypothesis:

$H0: {\\beta}_1 = {\\beta}_2 = ... = {\\beta}_k = 0$

$H1: {\\beta}_1 ≠ 0$ or ${\\beta}_2 ≠ 0$ or ${\\beta}_k ≠ 0$, for at least one value of k. In other words, at least **one** ${\\beta}$  is significant.

The test statistic is needed assuming that the null hypothesis is true:

$\Large \\frac{\\frac{\\sum( y_i - \\bar{y})²} {k}}{\\frac{\\sum{u}_i²} {n - k - 1}}$

Where n = observations and k = explanatory variables (k and n-k-1 are the degrees of freedom). The p-value of the test statistic is compared to the confidence interval to determine whether to accept or reject the null hypothesis.

### T-Test

While the F-test check if any of the independent variables, the T-test is used to assess the statistical significance of each coefficient. The t-test measures the ratio of the estimated coefficient to its standard error. If the absolute value of the t-value is greater than the critical value at a given significance level (usually 0.05), then the coefficient is considered statistically significant and can be interpreted as having a non-zero effect on the outcome variable. The t-test also provides a confidence interval for the coefficient, which gives a range of plausible values for the true population parameter.


###  Residuals Normality

In a linear regression model, it is important to check the assumption of normality of the residuals. The residuals are the differences between the actual values of the dependent variable and the predicted values from the regression model.

An example of 
![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/not-normal-y.png?raw=true)

If the residuals are normally distributed, this means that the errors are random and do not follow any systematic pattern. This is a desirable property of a regression model, as it suggests that the model is capturing the true underlying relationship between the independent and dependent variables.

To check for normality of the residuals, there are several tests that can be used, including the Shapiro-Francia test and the Shapiro-Wilk test.

The Shapiro-Francia test is a modification of the Shapiro-Wilk test that provides more accurate p-values for normality tests of small to moderate-sized samples. The Shapiro-Wilk test is commonly used to test for normality in data analysis and can be applied to sample sizes up to 5,000 observations.

Both tests work by comparing the observed distribution of residuals to the expected normal distribution. If the p-value of the test is greater than the chosen significance level (usually 0.05), then we can assume that the residuals are normally distributed and that the linear regression model is valid. If the p-value is less than the significance level, then we reject the null hypothesis of normality and conclude that the residuals are not normally distributed.

a
### Heteroskedasticity

Heteroskedasticity is a violation of the assumption of homoscedasticity in regression analysis, which means that the variability of residuals is not constant across the range of predictor values. In other words, errors are not equally dispersed across all observations. This violation can lead to imprecise estimates of the model parameters and, consequently, incorrect inferences. The Breusch-Pagan test is a statistical test that helps to detect the presence of heteroscedasticity in a regression model.

# Content

On [MultipleLinearRegressionStepByStep](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/LinearRegression/MultipleLinearRegressionStepByStep.ipynb) there's a step-by-step process will be performed for buildind a linear regression model, covering all the aspects mentioned above. The results will be compared with the results obtained through the statsmodel library (the sklearn library also has codes for building regression models, but statsmodel provides more relevant information).

[MLRFunction](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/LinearRegression/MLRFunction.ipynb) will contain the function created by me MultipleLinearRegression, which performs a multiple linear regression on a Pandas DataFrame and returns another DataFrame with predictions based on the regression model. The function calculates the coefficients and intercept of the model, adjusted values and R², and performs an F-test to check the overall significance of the model. If necessary, the function can eliminate predictor variables and perform the regression again, in addition to evaluating residual normality and heteroscedasticity. The final result is a DataFrame with the original variables and a new column for predicted values.

Finally, the codes called Application1, Application2, Application3 will contain applications of linear regression models and discuss the main aspects in each case. In these codes, the MultipleLinearRegression function will also be tested.

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
