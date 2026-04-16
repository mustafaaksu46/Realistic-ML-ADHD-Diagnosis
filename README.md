
# Realistic-ML-ADHD-Diagnosis

This repository provides the official implementation and experimental setup for evaluating machine learning models for ADHD diagnosis under realistic clinical conditions. 

Unlike traditional studies that rely on clean and idealized datasets, this framework introduces a **Realistic Transformation Algorithm** to simulate diagnostic uncertainty and symptom variability, enabling a more realistic assessment of model robustness.

## Key Highlights
* **Realistic Data Transformation:** Injection of 16% label noise and controlled feature variability into a DSM-5-based synthetic dataset (n = 6,500) to better reflect real-world clinical conditions.
* **Multi-Model Analysis:** Systematic comparison of 10 models, including classical machine learning, ensemble methods, and deep learning architectures.
* **Methodological Rigor:** Data leakage is prevented by isolating all preprocessing and feature selection steps within training folds.
* **Clinical Thresholding:** Decision thresholds are optimized using the Matthews Correlation Coefficient (MCC) to balance Type I and Type II errors.

## Evaluation Metrics
Beyond standard accuracy, the following metrics are used to reflect clinical relevance:
* **Clinical Robustness:** ROC-AUC and MCC
* **Diagnostic Reliability:** Sensitivity (TPR) and Specificity (TNR)
* **Operational Efficiency:** Training time and computational cost

## Model Selection Guide
Based on performance under realistic noise conditions:
* **Low-Resource (Mobile / Edge):** Naive Bayes & Logistic Regression  
  (Competitive performance with minimal computational cost)
* **Balanced Performance:** Random Forest & XGBoost  
  (Reliable results with efficient inference)
* **High-End (Robust CDSS):** CatBoost  
  (Best overall performance: ROC-AUC = 95.90%, MCC ≈ 0.86, strong robustness to noise)
