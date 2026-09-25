---
subject: ML
date: 2026-09-22
topics-covered:
  - Confusion matrix (TP, TN, FP, FN)
  - Accuracy, precision, recall, F1
  - Comparing error types and deciding what to fix
---

# Error Analysis

## Topics covered

- The confusion matrix and its four entries
- Accuracy, precision, recall and F1
- How to prioritise which errors to fix (false positives vs. false negatives)

## Notes

- Error analysis is the process of **examining the mistakes** a classifier makes to decide what to improve next — the accuracy number alone does not say *how* the model fails.

### Confusion Matrix

- A table of predicted vs. actual classes; everything else in classification evaluation is derived from it.

|  | Predicted Positive | Predicted Negative |
| --- | --- | --- |
| **Actual Positive** | True Positive (TP) | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN) |

- **True Positive (TP):** correctly predicted positive (e.g., spam flagged as spam).
- **True Negative (TN):** correctly predicted negative (e.g., normal email left alone).
- **False Positive (FP):** negative predicted as positive (normal email flagged as spam) — **Type I error**.
- **False Negative (FN):** positive predicted as negative (spam delivered to inbox) — **Type II error**.

### Accuracy

- $\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$
- Fraction of all predictions that are correct.
- **Misleading on imbalanced data:** if 95% of emails are not spam, a model that always predicts "not spam" has 95% accuracy but catches zero spam.

### Precision, Recall, F1

- **Precision:** of all predicted positives, how many are actually positive:
    - $\text{Precision} = \frac{TP}{TP + FP}$ — high when there are few false alarms.
- **Recall (Sensitivity):** of all actual positives, how many are correctly caught:
    - $\text{Recall} = \frac{TP}{TP + FN}$ — high when few positives are missed.
- **F1:** harmonic mean balancing precision and recall:
    - $\text{F1} = \frac{2 \cdot \text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}$
    - Useful when both false alarms and missed positives matter.

### Which Error to Fix

- Cost of errors decides the metric to optimise:
    - **Spam filter:** a missed spam (FN) is annoying; a deleted legit email (FP) is worse → optimise precision.
    - **Medical screening:** missing a disease (FN) is far worse than a false alarm (FP) → optimise recall.
- Error analysis loop:
    1. Collect misclassified examples (the FP and FN sets).
    2. Look for patterns / common traits among them (e.g., "long spam emails are missed", "emails with images are flagged").
    3. Fix the biggest, clearest pattern first — more data, new features, or threshold tuning in [[Logistic Regression]].

## Examples worked in class

### Spam Classifier Confusion Matrix

Out of 100 test emails (20 actual spam, 80 actual not-spam), the model predicts:

|  | Predicted Spam | Predicted Not-spam |
| --- | --- | --- |
| **Actual Spam** | TP = 15 | FN = 5 |
| **Actual Not-spam** | FP = 10 | TN = 70 |

- **Accuracy** = $\frac{15 + 70}{100} = 0.85$
- **Precision** = $\frac{15}{15 + 10} = 0.6$ — only 60% of flagged emails are really spam.
- **Recall** = $\frac{15}{15 + 5} = 0.75$ — 75% of spam is caught.
- **F1** = $\frac{2 \cdot 0.6 \cdot 0.75}{0.6 + 0.75} \approx 0.67$

**Reading the analysis:** precision (0.6) is the weak spot — 10 legit emails are being flagged. Error analysis on those 10 would look for what makes them look like spam (e.g., the word "FREE" in promotional mail), then add features or tune the threshold.

## Questions to research

- Why is accuracy a poor metric on imbalanced datasets, and when is F1 more informative than precision or recall alone?
- For a spam filter, should you optimise precision or recall? What about for fraud detection or medical diagnosis?
- How does the confusion matrix concept extend to [[Classification]]'s multi-class case (one-vs-rest)?

## See also

- [[Classification]] — the task being evaluated
- [[Logistic Regression]] — thresholds that trade precision against recall
- [[Learning Curves]] — bias vs. variance, another lens on why a model fails
- [[Regularization]] — a common fix for errors caused by overfitting
- [[Regression Metrics]] — the equivalent evaluation for regression models