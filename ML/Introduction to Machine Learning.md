---
subject: ML
date: 2026-09-08
topics-covered:
  - Definitions of machine learning
  - The ML workflow
  - Types of ML: supervised, unsupervised, reinforcement
---

# Introduction to Machine Learning

## Topics covered

- Definitions of machine learning (Samuel, Mitchell)
- The 6-step ML workflow
- Supervised vs. unsupervised vs. reinforcement learning

## Notes

### Definitions

- **Machine Learning:** a field of study that gives computers the ability to learn from data without being explicitly programmed (Arthur Samuel).
- A program is said to **learn** from experience $E$ with respect to task $T$ and performance measure $P$ if its performance on $T$ improves with $E$ (Tom Mitchell).

### Workflow

1. Collect / gather data
2. Clean and preprocess data
3. Split into training and testing sets
4. Train the model
5. Evaluate performance
6. Tune / improve and deploy

### Types of ML

- **Supervised learning** — labelled data
    - Regression → predicts continuous values (see [[Linear Regression]])
    - Classification → predicts discrete classes (see [[Classification]])
- **Unsupervised learning** — unlabelled data (e.g., customer segmentation, clustering)
- **Reinforcement learning** — agent learns from rewards / punishments (e.g., game playing, robotics)

## Examples worked in class

- Email spam detection: classifying emails as spam or not spam (supervised binary classification)
- Customer segmentation: grouping customers based on purchasing behaviour (unsupervised clustering)
- Game AI: an agent learning to play chess through rewards and punishments (reinforcement learning)

## Questions to research

- How does the choice of performance measure $P$ affect what a machine learning system learns in the definition $P$ improves with experience $E$?
- Why is it essential to split data into training and testing sets, and what problems can arise if we skip this step?
- Compare supervised, unsupervised, and reinforcement learning: give one real-world example for each and explain why it fits that category.

## See also

- [[Linear Regression]]
- [[Classification]]
- [[Gradient Descent]]