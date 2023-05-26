# Linear Models for Count Data

Linear models for count data are a class of statistical models used for analyzing count data, in which the response variable is a non-negative integer. These models are used to predict or explain the relationship between the count response variable and the explanatory variables. There are different types of linear models for count data, including Poisson models, negative binomial models, and zero-inflated count models.

# Relevant Concepts

### Superdispersion

Superdispersion occurs when the variance of count data is greater than the mean. This means that there is more variability in the data than would be expected by the Poisson model, which assumes equality between the mean and variance.

To check for superdispersion in the data, the Cameron and Trivedi test is used. It is a statistical technique used to verify the presence of excess variability (or dispersion) in regression models for count data. 

### Zero Inflation

Zero inflation, also known as excess of zeros, occurs when there are more zeros than expected by the count distribution in regression models for count data. When there is suspicion that the presence of extra zeros is influenced by factors not captured by the model, it is necessary to perform an appropriate test to assess whether an inflated zero model significantly improves the fit to the data compared to a simple model.

A commonly used test in this context is the Vuong test, which compares the inflated zero model with the simple model. The Vuong test examines whether the inflated zero model provides a statistically significant improvement in fit to the data. However, it is important to note that the detection of zero inflation is not always conclusive, and the results of the test should be interpreted with caution.

### Log-Likelihood

The log-likelihood is a fundamental measure in count data models and plays a crucial role in statistical inference. The log-likelihood is a function that quantifies the probability of observing the observed data, given a specific statistical model.

In count data models, the log-likelihood is used to estimate the model parameters using the maximum likelihood method. The goal is to find the parameter values that maximize the probability of observing the observed data.

Different models use different formulas to calculate the log-likelihood based on the underlying distribution of the data.



***

## Models

### Poisson Model

The Poisson model is the simplest and most common. It assumes that the response variable follows a Poisson distribution, where the mean is equal to the variance. It is suitable when the count is rare, i.e., the count mean is low relative to the sample size, and when the explanatory variables have an additive effect on the count. The formula for the Poisson model is given by:

$log(y_i) = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki} $

where $y_i$ is the mean count for the i-th observation, $xi$ is the vector of explanatory variable values for the i-th observation, and ${\alpha}$, ${\beta}1$, ${\beta}2$, ..., ${\beta}k$ are the model parameters.

The parameters are estimated using the maximum likelihood estimation (MLE) method. The goal of MLE is to find the parameter values that maximize the likelihood function, which is the probability of observing the observed data, given a set of parameter values. The parameter estimation using the maximum likelihood method occur in both Poisson models and other models for count data.

In a Poisson regression model, the log-likelihood function is used to estimate the model parameters. The log-likelihood function for a Poisson model with n observations and p predictors is given by:

$loglikehood = ∑(y_i log(μ_i) - μ_i - log(y_i!))$

 The predicted mean count $μ_i$ is calculated as:
 
 $μi = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki} $

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/poisson.png?raw=true)


### Negative Binomial Model

The Negative Binomial model is an extension of the Poisson model that accommodates overdispersion in count data, where the variance exceeds the mean. It is suitable when there is evidence of extra variation beyond what can be explained by the Poisson model, indicating that the assumption of equal mean and variance is violated.

In the Negative Binomial model, the response variable follows a Negative Binomial distribution, which allows for the variance to be greater than the mean. This model is particularly useful when dealing with overdispersed count data. 

Similar to the Poisson model, the Negative Binomial model includes explanatory variables that capture the effects on the count. The model is specified as follows:

$log(y_i) = {\alpha} + {\beta}1 x{1i} + {\beta}2 x{2i} + ... + {\beta}k x{ki} $

Here, $y_i$ represents the count for the i-th observation, $x_i$ denotes the vector of explanatory variable values for the i-th observation, and ${\alpha}$, ${\beta}1$, ${\beta}2$, ..., ${\beta}k$ are the model parameters.

Estimation of the parameters in the Negative Binomial model is also performed using the maximum likelihood estimation (MLE) method. The MLE aims to find the parameter values that maximize the likelihood function, considering the observed data and the assumed distribution.

The log-likelihood function for the Negative Binomial model accounts for the overdispersion and is given by:

$loglikelihood = ∑(y_i log(\frac{μ_i}{μ_i + \phi}) + y_i log(\phi) - log(y_i!))$

where $μ_i$ represents the predicted mean count for the i-th observation, and $\phi$ is the dispersion parameter that captures the extra variation.

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/bnegdis.png?raw=true)

### Zero-Inflated Poisson (ZIP) Model

The Zero-Inflated Poisson (ZIP) model is a type of regression model commonly used to analyze count data that exhibits both excessive zeros and the traditional Poisson distribution. It is a combination of two components: a binary component that models the excess zeros and a count component that models the non-zero counts.

In the ZIP model, the excess zeros are captured by a binary logistic regression, which determines the probability of observing a zero count versus a non-zero count. The count component follows a Poisson distribution, similar to the standard Poisson model. The ZIP model allows for the presence of excess zeros by considering a mixture of a structural component (Poisson distribution) and an excess zero component (logistic distribution).

The ZIP model is particularly useful when there are more zeros in the data than expected based on a simple Poisson distribution. It accounts for two potential sources of zeros: true structural zeros, where the count outcome is genuinely zero, and excess zeros, where the count outcome should have been non-zero but is observed as zero due to some underlying factors.

To estimate the parameters in the ZIP model, maximum likelihood estimation (MLE) is commonly employed. The MLE approach seeks to find the parameter values that maximize the joint likelihood of both the binary and count components of the ZIP model.

In summary, the ZIP model provides a flexible framework for analyzing count data with excessive zeros. By simultaneously modeling the binary excess zero component and the count component, it allows for a more comprehensive understanding of the underlying data generating process and provides improved predictive performance compared to a simple Poisson model.

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/zip.png?raw=true)

### Zero-Inflated Negative Binomial (ZINB) Model

The Zero-Inflated Negative Binomial (ZINB) model is an extension of the Zero-Inflated Poisson (ZIP) model that accounts for both excessive zeros and overdispersion in count data. It is particularly useful when analyzing data that exhibits an abundance of zeros and higher variability than expected under a Poisson or standard Negative Binomial model.

Similar to the ZIP model, the ZINB model consists of two components: a binary component and a count component. The binary component is modeled using logistic regression and determines the probability of excess zeros. The count component follows a Negative Binomial distribution, which allows for overdispersion and accounts for the excessive variability observed in the data.

In the ZINB model, excess zeros can arise from two sources: structural zeros and zero inflation. Structural zeros represent cases where the count outcome is genuinely zero, while zero inflation occurs when the count outcome should have been non-zero but is observed as zero due to certain factors.

Estimating the parameters in the ZINB model involves maximizing the joint likelihood of both the binary and count components, typically using maximum likelihood estimation (MLE). The MLE approach determines the parameter values that maximize the likelihood of observing the data given the assumed distribution and model structure.

The ZINB model offers a flexible approach for analyzing count data with excessive zeros and overdispersion. By capturing both excess zeros and variability beyond what is expected under a standard Negative Binomial model, it provides a more comprehensive understanding of the underlying data generating process. This enhanced modeling capability can lead to improved inference and prediction for count data with complex characteristics.

![alt text](https://github.com/Andrercouto/GeneralizedLinearModels/blob/main/Img/zinb.png?raw=true)

# Content
