---
subject: ML
date: 2026-09-08
topics-covered:
  - Multiple regression model and coefficients
  - Normal-equation formulas for b1, b2 and b0
  - Worked example: salary from experience and skill
  - Quick question: final marks (answer 91)
---

# Multiple Linear Regression

## Topics covered

- Model form $y = b_0 + b_1x_1 + b_2x_2 + \dots + b_nx_n$
- Coefficient formulas via normal equations ($b_1$, $b_2$, $b_0$)
- Worked example — salary from experience and skill
- Quick calculation — final marks (answer 91)

## Notes

- Extension of [[Linear Regression]] to **several independent variables**.

### Model

- $y = b_0 + b_1x$ (simple linear regression)
- $y = b_0 + b_1x_1 + b_2x_2 + ... + b_nx_n$
- $b_0$ = intercept
- $b_nx_n$ = slope (coefficient of the $n^{th}$ variable)

> In the example below: $x_1$ = No. of hours, $x_2$ = Attendance, and $x_3$ = Previous marks.

### Coefficients (normal equations, 2 variables)

- $b_{1} = \frac{S_{1y}S_{22} - S_{2y}S_{12}}{S_{11}S_{22} - S_{12}^{2}}$
- $b_{2} = \frac{S_{2y}S_{11} - S_{1y}S_{12}}{S_{11}S_{22} - S_{12}^{2}}$
- $b_{0} = \bar{y} - b_{1}\bar{x}_{1} - b_{2}\bar{x}_{2}$ (intercept, computed once the slopes are known)

where:

- $S_{11} = \sum (x_1 - \bar{x}_1)^2$
- $S_{22} = \sum (x_2 - \bar{x}_2)^2$
- $S_{12} = \sum (x_1 - \bar{x}_1)(x_2 - \bar{x}_2)$
- $S_{1y} = \sum (x_1 - \bar{x}_1)(y - \bar{y})$
- $S_{2y} = \sum (x_2 - \bar{x}_2)(y - \bar{y})$

## Examples worked in class

### Salary from Experience and Skill

| Emp | Exp (x1) | Skill (x2) | Salary (y) |
| --- | -------- | ---------- | ---------- |
| A   | 1        | 2          | 20         |
| B   | 2        | 1          | 25         |
| C   | 3        | 4          | 35         |
| D   | 4        | 3          | 40         |
| E   | 5        | 5          | 50         |

**Now:**

- Mean of $x_1$ = 3
- Mean of $x_2$ = 3
- Mean of $y$ = 34

**And:**

|     | $x_1 - \bar{x}_1$ $(d_1)$ | $x_2 - \bar{x}_2$ $(d_2)$ | $y - \bar{y}$ $(d_3)$ | $d_1^2 (S_{11})$ | $d_2^2 (S_{22})$ | $d_1 \cdot d_2 (S_{12})$ | $d_1 \cdot d_3 (S_{1y})$ | $d_2 \cdot d_3 (S_{2y})$ |
| --- | ------------------------- | ------------------------- | --------------------- | ---------------- | ---------------- | ------------------------ | ------------------------ | ------------------------ |
| A   | -2                        | -1                        | -14                   | 4                | 1                | 2                        | 28                       | 14                       |
| B   | -1                        | -2                        | -9                    | 1                | 4                | 2                        | 9                        | 18                       |
| C   | 0                         | 1                         | 1                     | 0                | 1                | 0                        | 0                        | 1                        |
| D   | 1                         | 0                         | 6                     | 1                | 0                | 0                        | 6                        | 0                        |
| E   | 2                         | 2                         | 16                    | 4                | 4                | 4                        | 32                       | 32                       |
| $\sum$ | 0                       | 0                         |                       | 10               | 10               | 8                        | 75                       | 65                       |

### Quick Calculation

**Q:** No. of hours = 6, Attendance = 80%, Previous marks = 70. Calculate the final marks.

Assume $b_0 = 10$, $b_1 = 5$, $b_2 = 0.2$ and $b_3 = 0.5$.

**Solution:**

- $y = b_0 + b_1x_1 + b_2x_2 + b_3x_3$
- $y = 10 + 5(6) + 0.2(80) + 0.5(70)$
- $y = 10 + 30 + 16 + 35 = 91$

## Questions to research

- In the multiple linear regression equation $y = b_0 + b_1x_1 + b_2x_2 + ... + b_nx_n$, how should we interpret the coefficient $b_1$ when other variables are held constant?
- What is multicollinearity, and how can it affect the stability and interpretability of coefficient estimates in multiple regression?
- Why is it often beneficial to center the predictor variables (subtract their means) before fitting a multiple regression model, particularly when interpreting the intercept?

## See also

- [[Linear Regression]]
- [[Polynomial Regression]]
- [[Gradient Descent]]