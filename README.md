# Parameter Optimization for SVM on Liver Disorder Dataset

This repository demonstrates the process of parameter optimization for Support Vector Machine (SVM) models using the **Liver Disorders Dataset** from the BUPA Medical Research Ltd. database. The dataset contains information about blood tests for liver disorders, potentially arising from excessive alcohol consumption.

## Dataset Overview

The dataset includes information about 345 individuals with 5 features that are sensitive to liver disorders. The task at hand is **regression**, with the objective of predicting the amount of alcohol consumed by an individual per day (`drinks`), based on blood test results.

### Dataset Information:
- **Instances**: 345
- **Features**: 5
- **Task**: Regression
- **Feature Types**: Categorical, Integer, Real
- **Subject Area**: Health and Medicine

## Objective

This project focuses on applying **Support Vector Machine (SVM)** for regression tasks with parameter optimization to predict the alcohol consumption (`drinks`) using blood test results. The goal is to find the optimal parameters that improve the SVM model's performance.

## Methodology
- **Data Loading:**
The dataset is loaded using ucimlrepo and split into features X and target y.

- **Train-Test Split:**
For each of 10 random seeds, the data is split into 70% test and 30% train sets.

- **Limited Training Size:**
From each training split, only 50 samples are selected to simulate low-resource training.

- **Random Search Optimization:**
For each sample:

100 random combinations of:
kernel: 'linear', 'poly', 'rbf', 'sigmoid'
C ∈ [0.1, 10.0]
gamma ∈ [0.001, 1.0]
Accuracy is calculated on the test set for each combination.
The best combination is logged.
- **Visualization:**
The best sample across all runs is visualized using a convergence plot that shows how the best accuracy improves over iterations.

## Dataset Details

- **Number of Instances**: 345
- **Number of Features**: 5 (continuous variables)
- **Target Variable**: `drinks` (continuous)

## Convergence Plot

![convergence_plot.png](https://github.com/user-attachments/assets/5f609524-07a5-4dde-955b-47e10c893711)


**Interpretation:**

- **X-axis**: Iteration number (logged every 10 iterations)
- **Y-axis**: Best accuracy found up to that iteration
- The plot reflects how progressively better hyperparameters are found

**Conclusion**
The SVM parameter optimization curve shows that the model performs best at a specific range of parameters. This means the tuning was successful, helping the model avoid both underfitting and overfitting. Beyond this point, further changes do not improve performance much, indicating convergence.
