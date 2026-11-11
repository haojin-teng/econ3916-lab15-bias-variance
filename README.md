# The Bias-Variance Tradeoff: Choosing How Flexible a Model Should Be

## Objective

I measured how the degree of a polynomial fit affects its bias, variance, and error on new data, and used cross-validation to choose a degree.

## Methodology

- In a simulated world with a known true curve, I split the error of polynomial fits into bias squared (how far the average fit is from the true curve) and variance (how much the fit changes from one sample to the next). I did this for six degrees, using 200 fresh samples at each one.
- For degrees 1 to 15, I compared training error with error on 2,000 new points and found the degree where the held-out error was lowest.
- I chose a degree with 5-fold cross-validation (CV) and looked at how much the error varied from fold to fold.
- I used nested CV to check whether the smallest CV error is a fair estimate of the error on new data. In each outer fold, I chose the degree by CV on the remaining data, then measured that degree's error on the held-out fold.
- I wrote a small function, `kfold_mse()`, that returns the k-fold CV mean squared error (MSE) for any degree and number of folds, and checked it with 10 folds on degrees 4 and 5.

## Key Findings

- Variance was [YOUR VALUE] at degree 5 and [YOUR VALUE] at degree 15.
- Error on the 2,000 new points was lowest at degree [YOUR VALUE].
- 5-fold CV chose degree [YOUR VALUE], with a CV MSE of [YOUR VALUE].
- The nested CV estimate of the error on new data was [YOUR VALUE].
- With 10 folds, `kfold_mse()` gave a CV MSE of [YOUR VALUE] for degree 4 and [YOUR VALUE] for degree 5.
