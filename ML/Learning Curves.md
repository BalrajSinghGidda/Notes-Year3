---
subject: ML
date: 2026-09-08
topics-covered:
  - Bias and variance
  - The bias-variance trade-off
  - Learning curve behaviour
---

# Learning Curves

## Topics covered

- Bias (under-fitting) and variance (over-fitting)
- The bias-variance trade-off
- How the error changes with training-set size

## Notes

- The learning curve model of ML shows how the **error in prediction** changes as the **size of the training set** increases or decreases.

### Bias

- Average of the difference between the average value and the predicted value.
- Lower bias → better model.

### Variance

- How the model's predictions change with the size of the dataset.
- Lower variance → better model.

### Bias-Variance Trade-off

- We need a bigger dataset for low bias in the model.
- The bigger the dataset, the more the variance.
- Learning curves help find the dataset size that achieves the bias-variance trade-off.
- **A good model finds the right spot** between bias and variance.

```mermaid
xychart-beta
    title "Bias-Variance Trade-off (illustrative)"
    x-axis "Model complexity" 1 --> 7
    y-axis "Error" 0 --> 1
    line [0.9, 0.75, 0.6, 0.45, 0.3, 0.2, 0.15]
    line [0.05, 0.1, 0.2, 0.35, 0.5, 0.65, 0.8]
```

- **Descending line (bias):** error from under-fitting — high when the model is too simple.
- **Rising line (variance):** error from over-fitting — high when the model is too complex.
- A good model sits near the crossing, where **both** errors are low.

```mermaid
xychart-beta
    title "Learning Curve"
    x-axis "Dataset" 100 --> 1600
    y-axis "Accuracy Score" 0.1 --> 1.0
    line [0.1, 0.68, 0.79, 0.83, 0.85, 0.87, 0.88, 0.896, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9, 0.9]
```

## Examples worked in class

- **High bias (under-fitting):** Both training and validation error are high and converge to a similar value as training set size increases. Adding more data does not significantly improve performance.
- **High variance (over-fitting):** Training error is low but validation error is much higher. As training set size increases, training error may increase slightly while validation error decreases, converging toward the training error.
- **Ideal case:** Both training and validation error decrease with training set size and converge to a low value, indicating good bias-variance trade-off.

## Questions to research

- How can you distinguish between a model suffering from high bias versus high variance by examining its learning curve?
- What changes would you expect to see in the learning curve if you increased the model complexity (e.g., added polynomial features) while keeping the training set size fixed?
- Why does the validation error eventually decrease with increasing training set size even for a complex model, and what does this indicate about the bias-variance trade-off?

## See also

- [[Regularization]] — fixing under-fitting / over-fitting
- [[Gradient Descent]] — convergence over training