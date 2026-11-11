# Realistic-ML-ADHD-Diagnosis

Code and experimental setup for the manuscript *"A Realistic Transformation Algorithm for Synthetic Clinical Data: Benchmarking Machine Learning Models in ADHD Screening Simulation."*

The repository benchmarks machine learning models for ADHD screening on a synthetic, DSM-5-based dataset that has been made less idealized by a **Realistic Transformation Algorithm**. The algorithm simulates response noise and diagnostic uncertainty.

> **Scope.** This is a simulation study on synthetic data. It does not claim clinical validity and must not be used for diagnosis or clinical decisions. The labels are derived from the same DSM-5 items used as input features, so results describe model behavior on the simulated data, not clinical utility.

## Key Features
* **Realistic Transformation:** Item-level response noise (Gaussian noise plus random ±1 response shifts) and a 16% diagnostic relabeling rate (3.6% effective change in the binary label), concentrated in the diagnostic boundary regions, applied to a DSM-5-based synthetic dataset (n = 6,500).
* **Ten Models:** Logistic Regression, Naive Bayes, SVM, Random Forest, XGBoost, CatBoost, ANN, 1D-CNN, ResNet, LSTM.
* **Leakage-Aware Evaluation:** Stratified 70/30 train/test split (4,550 / 1,950). Feature scaling (StandardScaler) and consensus feature selection are fitted on the training set only. Class imbalance is handled by stratification, class weights (Random Forest), PR-AUC-based tuning and imbalance-robust metrics; no resampling is used.
* **Threshold Optimization:** Decision thresholds are chosen from cross-validated training predictions by maximizing the Matthews Correlation Coefficient (MCC).
* **Statistics:** Friedman test with Wilcoxon/Dunn post-hoc comparisons and bootstrap 95% confidence intervals.

## Evaluation Metrics
Accuracy, F1-Score, ROC-AUC, PR-AUC, MCC, Cohen's Kappa, Sensitivity, Specificity, model size, inference latency and total development time.

## Main Results (test set)
* CatBoost: ROC-AUC 95.89%, accuracy 94.92%, MCC 0.8619.
* Random Forest and XGBoost: ROC-AUC 95.88% and 95.73%. The differences among the top ensemble models were not statistically significant.
* Logistic Regression and Naive Bayes reached about 95% ROC-AUC at very low computational cost.

Timing values depend on the hardware and are meant for relative comparison.

## Practical Notes (simulation-based)
* **Low-resource settings:** Naive Bayes and Logistic Regression offer competitive scores at minimal cost. Confirmation on real data is needed.
* **Highest scores in this benchmark:** CatBoost, Random Forest and XGBoost.

## Data
* Original synthetic dataset: Kaggle, *ADHD Dataset – 4 Classes* (Mohamed, 2024): https://www.kaggle.com/datasets/a7md19/adhd-dataset-4-classes-u2
* The raw and the realistically transformed datasets are in this repository.

## Reproducibility
Run the notebook top to bottom (Restart & Run All). Random seeds are fixed where applicable, except the bootstrap resampling, whose confidence intervals may vary slightly between runs.
