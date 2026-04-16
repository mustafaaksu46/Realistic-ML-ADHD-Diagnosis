# Realistic-ML-ADHD-Diagnosis

This repository provides the official implementation and experimental setup for evaluating Machine Learning models for ADHD diagnosis under simulated clinical reality. Unlike traditional studies that evaluate models on perfectly clean, idealized datasets, this framework introduces a Realistic Transformation Algorithm to analyze model robustness against diagnostic uncertainty and symptom variability.

## Key Highlights
* **Realistic Data Transformation:** Injection of 16% label noise and feature variability into a DSM-5-based synthetic dataset (n=6,500) to reflect real-world clinical "gray areas."
* **Multi-Model Analysis:** Systematic comparison of 10 different architectures, including Classical ML, Ensembles, and Deep Learning methods.
* **Methodological Rigor:** Strict prevention of data leakage by isolating data transformation and feature selection (Consensus Ranking) strictly to the training folds.
* **Clinical Thresholding:** Optimization of decision boundaries using the Matthews Correlation Coefficient (MCC) to balance Type I and Type II clinical errors.

## Evaluation Metrics
We go beyond standard accuracy to include metrics critical for psychiatric clinical decision support:
* **Clinical Robustness:** ROC-AUC and MCC (Matthews Correlation Coefficient).
* **Diagnostic Reliability:** Sensitivity (True Positive Rate) and Specificity (True Negative Rate).
* **Operational Efficiency:** Computational cost and training times for mobile health integration.

## Model Selection Guide
Based on our findings under realistic noise conditions, we categorize models by their optimal clinical use-case:
* **Low-Resource (Mobile Diagnostics):** Naive Bayes & Logistic Regression (Competitive performance [>95% AUC] with minimal computational cost, ideal for low-equipped devices).
* **Balanced Alternative:** Random Forest & XGBoost (Strong ensemble alternatives providing reliable results and fast inference under clinical reality conditions).
* **High-End (Robust Clinical CDSS):** CatBoost (Achieved the highest overall performance with 95.90% ROC-AUC and 0.86 MCC, demonstrating superior resilience to diagnostic noise).
