# Dataset

This project uses a publicly available synthetic ADHD dataset and a transformed version generated in this study.

## Original dataset
Mohamed, A. (2024). *ADHD Dataset – 4 Classes* (Kaggle):  
https://www.kaggle.com/datasets/a7md19/adhd-dataset-4-classes-u2

The original file is not redistributed here; please download it from Kaggle.

## 📁 Files

* `adhd_data_realistic.csv`  
  Dataset produced by applying the **Realistic Transformation Algorithm (RTA)** to the original data.

## 🧪 Transformation Overview

`adhd_data_realistic.csv` was created to make the synthetic data less idealized by adding controlled noise:

- **Response noise:** Gaussian item noise (σ = 0.65) and random ±1 response shifts (probability 0.18) in the symptom items, simulating subjective symptom reporting.
- **Variation in continuous variables:** 15–30% variation.
- **Diagnostic relabeling (16%):** 25% of samples in the diagnostic boundary zones (total score 14–23 and 30–44) and 7% elsewhere were relabeled, simulating diagnostic uncertainty. This changed 686 four-class labels (10.6%) and 235 binary labels (3.6%).

After the transformation the dataset contains 1,575 healthy and 4,925 ADHD records (originally 1,600 and 4,900).

## ⚖️ Notes

- The data are synthetic, and the labels derive from DSM-5 criteria that are also the input features. Results obtained with this dataset describe model behavior in a simulation. They do not demonstrate clinical validity or utility.
- The transformation is applied once, before the train/test split. Scaling and feature selection are fitted on the training set only (see the notebook).
