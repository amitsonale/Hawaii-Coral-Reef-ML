# Hawaii-Coral-Reef-ML
# Predicting Coral Reef Regimes from Human and Natural Influences

## Overview
This repository contains the code and resources for a machine learning mini-project focused on classifying Hawaiian coral reef regimes. The project builds upon the reference paper *Predicting Coral Reef Regimes from Human and Natural Influences* (CS229, 2019) by implementing a K-Nearest Neighbors (KNN) classifier as an extension to the originally reported models.

## Problem Statement
The goal is to predict discrete coral reef regimes (Classes: 1, 2, 3, and 5) based on 25 predictors, which include 20 original environmental/human factors (e.g., Effluent, Sedimentation, Sea Surface Temperature) and 5 engineered interaction features. Because the target classes are imbalanced, the primary evaluation metric is the micro-averaged F1 score.

## Dataset
*   **Total Observations:** 620
*   **Training Set:** 496 observations (80%) 
*   **Test Set:** 124 observations (20%)
*   **Features:** 25 numeric predictors

## Setup and Installation
1. Clone this repository to your local machine:
   `git clone https://github.com/amitsonale/Hawaii-Coral-Reef-ML.git`
2. Ensure you have Python 3.x installed along with the following libraries:
   `pip install numpy pandas matplotlib seaborn scikit-learn`
3. The data is fetched directly within the notebooks from the reference GitHub repository URLs. No manual data downloading is required.

## Usage
*   **EDA & Preprocessing:** Run the first Jupyter notebook to view the Exploratory Data Analysis, target class distributions, and feature correlations.
*   **Model Training & Evaluation:** Run the `Part 2 Extension` notebook. This script will:
    1. Load the prepared train/validation/test text files.
    2. Build a scikit-learn `Pipeline` utilizing `StandardScaler` and `KNeighborsClassifier`.
    3. Perform hyperparameter tuning using 5-fold cross-validation (`GridSearchCV`).
    4. Output the final Micro-F1 scores, classification report, and confusion matrix.

## Results
The KNN model was optimized to use 7 neighbors, Manhattan distance, and distance-based weighting. 
*   **Best 5-fold CV Micro-F1:** 0.6693
*   **Held-out Test Micro-F1:** 0.6532

**Conclusion:** The KNN model performs slightly worse than the reference project's best-performing Random Forest model, which achieved a test Micro-F1 score of 0.70. However, KNN provides a computationally inexpensive, distance-based classification baseline that successfully handles the standardized features.
