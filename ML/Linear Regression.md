---
subject: ML
date: 2026-09-08
topics-covered:
  - Simple linear regression model and its parts
  - Least-squares slope formula
  - Normal equation (matrix method) and its O(n³) cost
---

# Linear Regression

## Topics covered

- Simple linear regression model: $y = a_0 + a_1x + e$
- Least-squares slope and the aim of minimising error
- Normal equation (matrix method) and complexity

## Notes

### Model

- Linear regression models the relationship between a **dependent variable** $y$ and one or more **independent variables** $x$ by fitting a straight line through the data.
- $y = mx + c$ or $y = a_0 + a_1 x$
- $y = a_{0} + a_{1}x + e$, where:
    - $y$ = the value to predict
    - $x$ = the value we know
    - $a_0$ = intercept
    - $a_1$ = slope
    - $e$ = error / residual term (difference between predicted and actual $y$)

### Least-Squares Slope

- $a_{1} = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^{2}}$
- $a_1$ = slope, $a_0$ = intercept (goal: minimise the error $e$)

### Normal Equation (Matrix Method)

- $a = ((X^TX)^{-1}X^T)Y$
- **Computational complexity:** matrix inversion costs $O(n^3)$, where $n$ = number of features (independent variables).

### Types of Regression

- **Simple linear regression** — one independent variable (this note)
- **Multiple linear regression** — several independent variables → [[Multiple Linear Regression]]
- **Polynomial regression** — non-linear (curved) fit → [[Polynomial Regression]]

## Examples worked in class

- Experience vs. salary fit — the graph drawn in class is kept in the archived revision note.

## Questions to research

- Why does the normal equation need matrix inversion, and when would gradient descent be cheaper on the same problem?

## See also

- [[Gradient Descent]] — finding the parameters by minimising the cost function
- [[Logistic Regression]] — logistic (sigmoid) model for classification probabilities
- [[Introduction to Machine Learning]]