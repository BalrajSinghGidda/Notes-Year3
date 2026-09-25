---
subject: ML
date: 2026-09-08
topics-covered:
  - Classification as a supervised task
  - Binary, multi-class and multi-label classification
  - Multioutput classification
---

# Classification

## Topics covered

- Classification as a supervised machine learning method
- Binary, multi-class and multi-label classification
- Multioutput classification

## Notes

- A **supervised machine learning** method.
- Task: assign a **label** (class) to new examples based on learned patterns.
- Labeling: the training data comes with predefined labels.

### Types

- **Binary classification** — exactly 2 classes, e.g., spam or not spam, pass or fail.
- **Multi-class classification** — more than 2 *exclusive* classes, e.g., classify an image as cat, dog or bird.
- **Multi-label classification** — one instance can belong to multiple classes at once, e.g., a photo containing a dog and a cat gets both labels.
- **Multioutput classification** — one instance produces *several output variables*, each with its own set of classes (possibly different class sets per output), e.g., predict a person's age group **and** gender from a face; can even mix classification and regression (multioutput-multiclass).

### Multioutput vs. Multi-label

- **Multi-label:** a single output variable that can take *multiple values at once* (one binary decision per class).
- **Multioutput:** *several separate output variables*, each predicted independently, each possibly multi-class (or even regression).
- Example: self-driving car frame — for each object, predict both its class (multiclass) and its bounding box (regression) → a multioutput task mixing both.

## Examples worked in class

- Spam vs. not spam — see the full worked example in [[Logistic Regression]].

## Questions to research

- What is the fundamental difference between multi-class and multi-label classification, and provide an example where multi-label is more appropriate?
- In a multi-class classification problem with three classes, why can't we simply train three binary classifiers, and what issues might arise?
- Name two real-world applications where multi-label classification is commonly used, and explain why.
- Give an example of a multioutput task that mixes classification and regression, and explain why the outputs cannot be treated as a single multi-class variable.

## See also

- [[Logistic Regression]] — the go-to model for binary classification probabilities
- [[Error Analysis]] — confusion matrix, precision / recall / F1
- [[Introduction to Machine Learning]]
- [[Regularization]] — preventing overfitting in classifiers