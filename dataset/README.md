
# Dataset

This project uses a publicly available ADHD dataset and a transformed version generated in this study.

The original dataset is available on Kaggle:  
Mohamed, A. (2024), "ADHD Dataset – 4 Classes"  
https://www.kaggle.com/datasets/a7md19/adhd-dataset-4-classes-u2

## 📁 Files

* `adhd_data_realistic.csv`  
  Transformed dataset generated using the proposed **Realistic Transformation Algorithm (RTA)**.

## 🧪 Transformation Overview

The `adhd_data_realistic.csv` dataset was created to simulate real-world clinical conditions by introducing controlled noise:

- **16% Label Noise:** Simulates diagnostic uncertainty  
- **Feature Variability:** Reflects subjective symptom reporting  
- **Uncertain Cases:** Focus on borderline samples to test model robustness  

## ⚖️ Notes

- The transformed dataset is designed to evaluate machine learning models under realistic clinical conditions.
