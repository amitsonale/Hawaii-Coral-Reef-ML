# Hawaii-Coral-Reef-ML

## Overview
This repository contains a machine learning mini-project that predicts the ecological health (or "regime") of coral reefs in Hawaii. We used an existing Stanford CS229 paper as our starting point, replicated their baseline models, and then built our own K-Nearest Neighbors (KNN) model to see if a simple, distance-based algorithm could beat their results.

## The Problem
Coral reefs are impacted by a mix of human activities (like fishing and pollution) and natural factors (like sea surface temperature and wave action). Our goal is to take 25 of these environmental factors and predict which of four regimes (Classes 1, 2, 3, or 5) a reef falls into. Because some reef types are more common than others in our data, we use the Micro-F1 score to grade our models fairly.

## The Data
*   **Total Locations:** 620 spatial observations.
*   **Training Data:** 496 locations (80%) used to teach the models.
*   **Test Data:** 124 locations (20%) held back to test the models.
*   **Features:** 25 numerical inputs (20 raw environmental factors + 5 custom mathematical features).

## How to Run the Code
1. Clone this repository to your computer:
   `git clone https://github.com/amitsonale/Hawaii-Coral-Reef-ML.git`
2. Make sure you have Python installed, along with these standard libraries:
   `pip install numpy pandas matplotlib seaborn scikit-learn`
3. Run `Part1_EDA.ipynb` first. This downloads the data directly from the web, shows some visual graphs, and replicates the original paper's baseline models.
4. Run `Part2_KNN_Extension.ipynb` next. This trains our custom KNN model, tunes it, and prints out a final comparison table against the models from Part 1.

## Results
After testing various configurations, our best KNN model used 7 neighbors and Manhattan distance.
*   **Logistic Regression (Baseline):** 61% accuracy on the test set.
*   **Our KNN Model:** 65% accuracy on the test set.
*   **Random Forest (Paper's Best):** 72% accuracy on the test set.

Our KNN model successfully beat the baseline but couldn't quite catch the Random Forest. Tree-based models tend to win here because they are better at handling complex, messy environmental rules rather than just looking at the spatial distance between data points.
