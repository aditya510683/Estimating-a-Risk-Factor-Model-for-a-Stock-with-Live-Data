# Estimating the Fama French Carhart Four-Factor Risk Model Exposures

This repository contains a Jupyter notebook that demonstrates the estimation of the Fama French Carhart four-factor risk model exposures for an arbitrary stock using live data. In this example, we analyze Apple Inc. (AAPL) to understand how its returns are influenced by various risk factors.

## Libraries Used

The following libraries were used in this project:
- `pandas`: For data manipulation and analysis.
- `numpy`: For numerical computations.
- `statsmodels`: For performing OLS regression analysis.
- `yfinance`: For retrieving financial data from Yahoo Finance.
- `matplotlib`: For data visualization.

## Summary

- The model explains 28.8% of the variance in Apple's excess returns.
- Apple's returns are significantly influenced by the market risk premium and the value factor.
- The size and momentum factors do not significantly affect Apple's returns.
- The model itself is statistically significant, but the residuals exhibit some non-normality.

## Key Outputs

### Estimated Coefficients (Risk Factor Exposures)

1. **Alpha (const)**: 1.3855
   - Represents the excess return of Apple not explained by the four factors. It is statistically significant, indicating that Apple has an average excess return of 1.3855% beyond what is explained by the model.

2. **Market Risk Premium (Mkt-RF)**: 1.1978
   - Indicates that for every 1% increase in the market risk premium, Apple's excess return increases by approximately 1.1978%. This factor is highly significant, suggesting a strong relationship between Apple's returns and the overall market returns.

3. **Size (SMB)**: 0.2288
   - Represents Apple's exposure to the size factor. Although positive, indicating that Apple behaves somewhat like smaller firms, it is not statistically significant, suggesting that the size effect is not a strong determinant of Apple's returns.

4. **Value (HML)**: -0.8940
   - Indicates that Apple behaves more like a growth stock (lower book-to-market ratio) as opposed to a value stock. The negative and highly significant value suggests that Apple's returns are negatively correlated with the value factor.

5. **Momentum (MOM)**: -0.1094
   - Represents Apple's exposure to the momentum factor. The negative value suggests a slight negative relationship, but it is not statistically significant, indicating that momentum is not a strong factor in explaining Apple's returns.

### Model Fit and Diagnostics

- **R-squared**: 0.288
  - Approximately 28.8% of the variance in Apple's excess returns can be explained by the four factors.

- **Adjusted R-squared**: 0.283
  - Indicates that the model explains about 28.3% of the variance after considering adjustments for the number of predictors and sample size.

- **F-statistic**: 52.19 (p-value: 6.44e-37)
  - The very low p-value indicates that the model is statistically significant overall.

- **Residual Diagnostics**:
  - **Omnibus**: 15.975 (p-value: 0.000)
  - **Jarque-Bera**: 34.246 (p-value: 3.66e-08)
  - These tests indicate that the residuals do not follow a normal distribution, suggesting some non-normality in the error terms.
  - **Durbin-Watson**: 1.963
  - Indicates no significant autocorrelation in the residuals.

### Interpretation

- The market risk premium and value factors are significant in explaining Apple's excess returns, with the market risk premium having a strong positive impact and the value factor having a significant negative impact.
- The size and momentum factors do not significantly affect Apple's returns.
- While the model is statistically significant and explains a portion of the variance in Apple's returns, the residuals show some non-normality, indicating that there are potential areas for model improvement.
