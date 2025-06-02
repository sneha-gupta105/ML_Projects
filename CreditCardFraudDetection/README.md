Link to Jupyter Source File:
https://colab.research.google.com/drive/11Cdi0fjB30uHdYSIo_07hVdAZlIcmAR2?usp=sharing


# Credit Card Fraud Detection

## Overview

This project aims to detect fraudulent credit card transactions using various machine learning classification algorithms. The dataset is highly imbalanced, with very few fraud cases compared to legitimate transactions. This project explores different sampling techniques and multiple classification models to address the class imbalance and evaluate model performance effectively.

## Dataset

* The dataset contains 31 columns: 30 feature columns and 1 target column (`Class`).
* The `Class` column has two values:

  * `0` for non-fraudulent transactions.
  * `1` for fraudulent transactions.
* The dataset is already normalized.

## Data Visualization

* Initial visualization shows a highly imbalanced dataset with far fewer fraud cases.
* Scatter plots of features help to visualize the distribution and class separation.
* Bar plots highlight the class imbalance.

## Sampling Techniques

To handle the imbalance, three sampling methods are applied:

1. **Sampling 1:** Randomly sample 10% of both the normal and fraud classes, maintaining the original class ratio.
2. **Sampling 2:** Undersample the normal class to match the number of fraud cases (making the classes balanced).
3. **Sampling 3:** Combine undersampling of the normal class and oversampling (with replacement) of the fraud class to create a balanced dataset of 30,000 samples (15,000 each).

## Models Used

The following classification algorithms are trained and evaluated on the original and sampled datasets:

* Decision Tree Classifier
* AdaBoost Classifier
* XGBoost Classifier
* K-Nearest Neighbors
* Support Vector Machine (SVM)
* Linear Discriminant Analysis (LDA)
* Multilayer Perceptron Neural Network (MLP)

## Evaluation Metrics

Model performance is evaluated using multiple metrics to address the imbalance:

* Confusion Matrix (True Negatives, False Positives, False Negatives, True Positives)
* Precision
* Recall / Sensitivity
* Specificity
* Accuracy
* F1 Score (weighted)
* ROC AUC Score

Visualizations of the confusion matrix and metric scores are provided after each model evaluation.

## How to Run

1. Mount your Google Drive in Google Colab.
2. Load the dataset from the specified path.
3. Run the data visualization cells.
4. Train and evaluate models on the original and sampled datasets.
5. View results and confusion matrix plots for model comparison.

## Dependencies

* pandas
* numpy
* matplotlib
* scikit-learn
* xgboost
* Google Colab (for drive mounting)

## Notes

* The dataset is highly imbalanced; hence, accuracy alone is insufficient to assess model performance.
* Sampling strategies significantly affect model evaluation.
* This project emphasizes using multiple evaluation metrics for comprehensive analysis.
