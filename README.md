# ECON3916-LAB15
# The Bias-Variance Tradeoff: Choosing How Flexible a Model Should Be

## Objective
I explored how model complexity affects bias, variance, and prediction error, and used cross-validation to choose a polynomial degree that performs well on new data.

## Methodology
- Simulated data from a known true curve and fitted polynomial regression models at six different degrees.
- Used 200 fresh samples at each degree to separate prediction error into bias squared and variance.
- Compared training error with held-out error on 2,000 new data points for polynomial degrees 1 through 15.
- Identified the polynomial degree with the lowest held-out mean squared error (MSE).
- Used 5-fold cross-validation to select a polynomial degree and examined how prediction error varied across folds.
- Applied nested cross-validation to compare the minimum cross-validation error with an estimate of performance on unseen data.
- Wrote `kfold_mse()` to calculate k-fold cross-validation MSE for any polynomial degree and number of folds.
- Tested my function using 10-fold cross-validation and compared the results for degrees 4 and 5.

## Key Findings

- **Bias-variance tradeoff:** I observed how increasing polynomial degree changes the balance between bias and variance. Simpler models can miss important patterns, while more flexible models can become sensitive to the particular training sample.
- **Model variance:** At degree 5, the estimated variance was [YOUR VALUE], compared with [YOUR VALUE] at degree 15.
- **Training vs. held-out error:** Training error alone was not enough to choose the best model. The lowest held-out error occurred at degree [YOUR VALUE], showing why performance on new data matters.
- **5-fold cross-validation:** Cross-validation selected degree [YOUR VALUE], with an average CV MSE of [YOUR VALUE]. I also examined variation across folds to understand how much the error estimate depended on the data split.
- **Nested cross-validation:** The nested CV error estimate was [YOUR VALUE]. This gave me a separate estimate of prediction error after accounting for the model-selection process, rather than relying only on the smallest CV error.
- **10-fold cross-validation:** My `kfold_mse()` function produced an MSE of [YOUR VALUE] for degree 4 and [YOUR VALUE] for degree 5.
- **Model selection:** I learned that the polynomial with the lowest training error is not necessarily the one that predicts new observations most accurately.

## Takeaway
This lab helped me understand why adding complexity to a model does not always improve its predictions. I saw how bias and variance contribute to prediction error, why training error can be misleading, and how cross-validation helps choose model complexity. I also learned that selecting a model and estimating its performance are different tasks, which is why nested cross-validation can be useful.

