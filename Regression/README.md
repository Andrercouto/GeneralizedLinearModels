# Simple and Multiple Linear Regression

Simple and multiple linear regression are statistical methods used to model the relationship between two or more variables. Simple linear regression involves fitting a linear equation to the data to describe the relationship between a single predictor variable (independent variable) and a response variable (dependent variable). The goal of simple linear regression is to find the line of best fit that can be used to make predictions about the response variable based on the value of the predictor variable.

Multiple linear regression is an extension of simple linear regression that allows for modeling the relationship between more than one predictor variable and the response variable. In multiple linear regression, the goal is to find the line of best fit that describes the relationship between the response variable and multiple predictor variables. This line can then be used to make predictions about the response variable based on the values of the predictor variables.


# Relevant Concepts

## Simple Linear Regression Formula

In simple linear regression, the equation is represented by:

$y_i = {\\alpha} + {\\beta} . x_i + u_i$

Where (for i=n observations and k explanatory variables):

${y}$ = dependent variable;

${x}$ = explanatory variable;

${\\alpha}$ = intercept (constant term);

${\\beta}$ = explanatory variable coefficient;

${u}$ = error term.

## Multiple Linear Regression Formula

In multiple linear regression, the equation is represented by:

$y_i = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki} + u_i$

Where:

$y$ = dependent variable;

$x_{1}, x_{2},..., x_{k}$ = explanatory variables;

${\alpha}$ = intercept (constant term);

${\beta}_1, {\beta}_2,..., {\beta}_k$ = explanatory variable coefficients;

$u$ = error term.

## R²

R² (R-Squared or the coefficient of determination) is a statistical measure in a regression model that determines the proportion of variance in the dependent variable that can be explained by the independent variable. In other words, r-squared shows how well the data fit the regression model (the goodness of fit).

$R² = \\large\\frac{\\sum( y_i - \\bar{y})²} {\\sum( y_i - \\bar{y})² + \\sum{u}_{i}²}$

R² can take any values between 0 to 1. Although the statistical measure provides some useful insights regarding the regression model, but it does not disclose information about the causation relationship between the independent and dependent variables and does not indicate the correctness of the regression model.

