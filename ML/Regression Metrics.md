---
subject: ML
date: 2026-09-22
topics-covered:
  - Mean Absolute Error (MAE)
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R-squared score
---

# Regression Metrics

## Topics covered

- The four standard regression metrics: MAE, MSE, RMSE, R²
- Their formulas, units and what each one penalises
- Which metric to choose when

## Notes

- Metrics measure how far the model's predictions ($\hat{y}$) are from the actual values ($y$) over $m$ examples.

### Mean Absolute Error (MAE)

- Average of the absolute differences:
    - $\text{MAE} = \frac{1}{m} \sum_{i=1}^{m} \left| y^{(i)} - \hat{y}^{(i)} \right|$
- Same units as $y$ → easy to interpret.
- Treats all errors equally (no extra penalty for large errors).

### Mean Squared Error (MSE)

- Average of the squared differences:
    - $\text{MSE} = \frac{1}{m} \sum_{i=1}^{m} \left( y^{(i)} - \hat{y}^{(i)} \right)^2$
- Squaring makes it **sensitive to outliers** — one huge error dominates the score.
- Units are $y^2$, which is harder to interpret directly.
- Same objective the [[Gradient Descent]] cost function minimises.

### Root Mean Squared Error (RMSE)

- Square root of the MSE:
    - $\text{RMSE} = \sqrt{\text{MSE}}$
- Back in the original units of $y$, so it is easier to read than MSE.
- Still keeps MSE's outlier sensitivity — a common default choice.

### R-squared Score

- Proportion of variance in $y$ explained by the model:
    - $R^2 = 1 - \frac{\text{SS}_\text{res}}{\text{SS}_\text{tot}} = 1 - \frac{\sum (y - \hat{y})^2}{\sum (y - \bar{y})^2}$
- $\text{SS}_\text{res}$ = residual sum of squares (what the model misses), $\text{SS}_\text{tot}$ = total variance of the data around the mean $\bar{y}$.
- Ranges from 1 (perfect fit) down to negative values (a model worse than just predicting the mean).

| Metric | Formula | Units | Penalises |
| --- | --- | --- | --- |
| MAE | $\frac{1}{m}\sum |y - \hat{y}|$ | same as $y$ | all errors equally |
| MSE | $\frac{1}{m}\sum (y - \hat{y})^2$ | $y^2$ | large errors heavily |
| RMSE | $\sqrt{\frac{1}{m}\sum (y - \hat{y})^2}$ | same as $y$ | large errors heavily |
| R² | $1 - \frac{\text{SS}_\text{res}}{\text{SS}_\text{tot}}$ | unitless | unexplained variance |

## Examples worked in class

### Marks Example (data from [[Gradient Descent]])

| Hours | Marks ($y$) | Predicted ($\hat{y}$) | Error ($\hat{y} - y$) |
| --- | --- | --- | --- |
| 1 | 10 | 12 | 2 |
| 2 | 20 | 18 | -2 |
| 3 | 30 | 28 | -2 |
| 4 | 40 | 35 | -5 |
| 5 | 50 | 48 | -2 |

**Now:**

- MAE = $\frac{2 + 2 + 2 + 5 + 2}{5} = \frac{13}{5} = 2.6$
- MSE = $\frac{4 + 4 + 4 + 25 + 4}{5} = \frac{41}{5} = 8.2$
- RMSE = $\sqrt{8.2} \approx 2.86$
- R²: $\bar{y} = 30$, $\text{SS}_\text{tot} = 1000$, $\text{SS}_\text{res} = 41$
    - $R^2 = 1 - \frac{41}{1000} = 0.959$ → the model explains ~96% of the variance in marks.

## Questions to research

- When would you prefer MAE over RMSE (e.g., in the presence of outliers), and what are the drawbacks of each?
- Why can R² be negative, and what does that indicate about the model compared to predicting the mean?
- How do regression metrics relate to the cost function used in gradient descent — is MSE always the right choice?

## See also

- [[Gradient Descent]] — MSE as the cost function being minimised
- [[Linear Regression]] — where these metrics are first applied
- [[Polynomial Regression]] — comparing fits of different degrees with these metrics
- [[Multiple Linear Regression]]