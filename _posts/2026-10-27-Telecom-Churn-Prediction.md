---
layout: post
title: Telecom Customer Churn Prediction (Python)
tags: [Python, scikit-learn, Random Forest, Classification]
---

In this project I built a random forest classifier on a public telecom dataset of 3,150 customers. The question: which customers are likely to churn, and which signals matter most?

About 15.7% of customers churned, so always predicting "stayed" would score 84.3% accuracy. Accuracy alone is not the measure; recall on the customers who actually left is.

---

## Results

I evaluated with 5-fold cross-validation (mean ± standard deviation).

| | All columns | Without Complains and Status |
|---|---|---|
| Accuracy | 0.955 ± 0.007 | 0.938 ± 0.012 |
| Churn recall | 0.81 ± 0.04 | 0.74 ± 0.05 |

Complains and Status add about 7 points of recall, and they were also the strongest signals. Without them, usage and billing columns alone still identify about three in four churners.

---

## What it suggests

- Importance is spread across complaints, usage and tenure rather than resting on one column. The top features were Complains, Seconds of Use, Status, Subscription Length and Frequency of use.
- Complaints may be recorded shortly before a customer leaves, so they may be a late signal rather than an early warning. Feature importance shows what the model uses, not what causes churn.

---

## Limits

The model uses default settings with no tuning. Precision, F1 and feature importances come from a single train/test split. The dataset is a public sample, so none of this is a claim about a real company.

[Code and full write-up on GitHub](https://github.com/fraserparrott/telecom-churn)

---

**Tools:** Python, pandas, scikit-learn.
