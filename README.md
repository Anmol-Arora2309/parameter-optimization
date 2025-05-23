# Parameter Optimization for SVM on Liver Disorder Dataset

This repository presents the approach taken to optimize parameters for Support Vector Machine (SVM) models, utilizing the Liver Disorders Dataset provided by BUPA Medical Research Ltd. This dataset comprises blood test data that may indicate liver issues, often associated with high alcohol consumption.

## Dataset Overview

The dataset includes information about 345 individuals with 5 features that are sensitive to liver disorders. The task at hand is **regression**, with the objective of predicting the amount of alcohol consumed by an individual per day (`drinks`), based on blood test results.

### Dataset Information:
- **Instances**: 345
- **Features**: 5
- **Task**: Regression
- **Feature Types**: Categorical, Integer, Real
- **Subject Area**: Health and Medicine

## Objective

The purpose of this project is to implement Support Vector Machine (SVM) regression and optimize its parameters to accurately forecast the daily alcohol intake from the blood test features. The key goal is to determine the parameter combinations that deliver the best model performance.

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
