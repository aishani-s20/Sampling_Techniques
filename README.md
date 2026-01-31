# 📊 Credit Card Fraud Analysis: Sampling & ML Evaluation

[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)](https://scikit-learn.org/)
[![Status](https://img.shields.io/badge/Project-Completed-green)]()

## 📌 Project Objective
Real-world datasets, especially in fraud detection, are often highly imbalanced. This project demonstrates how to handle such imbalances by:
1. Balancing the dataset using **Random Oversampling**.
2. Extracting five distinct subsets using various **Sampling Techniques**.
3. Benchmarking the performance of five different **Machine Learning Models** across these samples to determine the most effective combination.

---

## 🛠️ Methodology

### 1. Data Preparation
The initial dataset contained **772 records** with a massive class imbalance (only 9 fraud cases). To ensure model reliability, we balanced the dataset to **1,526 records** (763 Fraud / 763 Non-Fraud).

### 2. Sampling Strategies Applied
We utilized a calculated sample size ($n=385$) based on a 95% confidence level and 5% margin of error for the following techniques:
* **Sampling 1 (Simple Random)**: Every instance has an equal chance of selection.
* **Sampling 2 (Systematic)**: Instances are selected at fixed periodic intervals.
* **Sampling 3 (Stratified)**: Ensures the sample maintains the balanced proportions of both classes.
* **Sampling 4 (Cluster)**: Data is divided into groups (clusters), and specific clusters are randomly selected.
* **Sampling 5 (Bootstrap)**: Random sampling with replacement.

### 3. Machine Learning Models
* **M1**: Logistic Regression (Linear Model)
* **M2**: Random Forest (Ensemble Model)
* **M3**: Decision Tree (Tree-based Model)
* **M4**: Support Vector Classifier (Kernel-based Model)
* **M5**: K-Nearest Neighbors (Distance-based Model)
---

## 📈 Performance Results (Accuracy %)

The table below summarizes the accuracy achieved by each model when trained on the various sampling types:

| Model | Simple Random | Systematic | Stratified | Cluster | Bootstrap |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **M1 (Logistic Regression)** | 89.61 | 85.71 | 88.31 | 89.61 | **96.10** |
| **M2 (Random Forest)** | **100.00** | **100.00** | 98.70 | **100.00** | **100.00** |
| **M3 (Decision Tree)** | **100.00** | **100.00** | 87.01 | 94.81 | 94.81 |
| **M4 (SVC)** | **98.70** | 96.10 | 97.40 | 94.81 | **98.70** |
| **M5 (KNN)** | **98.70** | 90.91 | 92.21 | 87.01 | **98.70** |

---

## 🏆 Final Discussion
* **Best Model**: **Random Forest (M2)** demonstrated the highest stability and accuracy, frequently hitting 100% across multiple samples.
* **Best Technique**: **Simple Random Sampling (Sampling 1)** and **Bootstrap Sampling (Sampling 5)** yielded the highest average performance across the majority of the models.
* **Observation**: Linear and Distance-based models (M1 and M5) showed significant improvement when the data was scaled and sampled using Bootstrapping.

---
