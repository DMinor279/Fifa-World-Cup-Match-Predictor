# FIFA World Cup Match Outcome Prediction

## Project Overview

This project develops and compares multiple machine learning models for predicting the outcome of FIFA World Cup matches using historical tournament data and pre-match features.

The objective is to determine whether the **home team wins**, **draws**, or **loses** against the away team before the match is played.

The project uses historical FIFA World Cup match data, FIFA rankings, and tournament statistics to engineer predictive features and train four classification algorithms.

---

# Objectives

* Predict FIFA World Cup match outcomes.
* Compare the performance of multiple machine learning algorithms.
* Identify the most influential factors affecting match outcomes.
* Produce a reproducible sports analytics workflow suitable for deployment and portfolio presentation.

---

# Dataset

The project uses three datasets:

## 1. Match Dataset (`matches_1930_2022.csv`)

Contains historical FIFA World Cup match information, including:

* Teams
* Scores
* Match dates
* Tournament stages
* Expected Goals (xG)
* Attendance
* Match officials

---

## 2. FIFA Ranking Dataset (`fifa_ranking_2026-06-08.csv`)

Contains:

* Team rankings
* FIFA points
* Confederation information
* Rated matches

---

## 3. World Cup Dataset (`world_cup.csv`)

Contains:

* Tournament winners
* Runner-ups
* Number of matches
* Historical tournament information

---

# Problem Statement

This is a **multiclass classification problem**.

## Target Variable

`match_result`

| Value | Meaning       |
| ----- | ------------- |
| 1     | Home Team Win |
| 0     | Draw          |
| -1    | Away Team Win |

---

# Feature Engineering

The following pre-match features are used.

## Team Strength Features

* Home FIFA Rank
* Away FIFA Rank
* Home FIFA Points
* Away FIFA Points
* Rank Difference
* Points Difference

---

## Confederation Features

* Home Confederation
* Away Confederation

---

## Historical Performance Features

* Previous World Cup Performance
* Number of World Cup Titles
* Number of World Cup Appearances
* Match Experience Difference

---

## Tournament Features

* Tournament Stage
* Days of Rest Difference

---

## Performance Features

* Expected Goals Difference (xG Difference)

---

# Engineered Features

| Feature                   | Description                         |
| ------------------------- | ----------------------------------- |
| rank_difference           | Away Rank − Home Rank               |
| points_difference         | Home Points − Away Points           |
| world_cups_won_difference | Home Titles − Away Titles           |
| matches_played_difference | Home Appearances − Away Appearances |
| days_rest_difference      | Home Rest Days − Away Rest Days     |
| xg_difference             | Home xG − Away xG                   |

---

# Machine Learning Workflow

```text
Data Collection
        ↓
Data Understanding
        ↓
Data Cleaning
        ↓
Feature Engineering
        ↓
Encoding & Scaling
        ↓
Train-Test Split
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
Model Selection
```

---

# Data Preprocessing

## Missing Values

### Numerical Features

* Median Imputation

### Categorical Features

* Most Frequent Imputation

---

## Categorical Encoding

One-Hot Encoding is applied to:

* Confederation
* Tournament Stage

---

## Feature Scaling

Standardization is applied to numerical features:

```text
Z = (X − μ) / σ
```

where:

* μ = Mean
* σ = Standard Deviation

---

# Train-Test Split

The dataset is divided into:

* Training Set: 80%
* Testing Set: 20%

Stratified sampling is used to preserve the class distribution.

---

# Models Trained

## 1. Artificial Neural Network (ANN)

Characteristics:

* Learns complex nonlinear relationships.
* Captures feature interactions.

---

## 2. Support Vector Machine (SVM)

Characteristics:

* Uses an RBF kernel.
* Creates optimal decision boundaries.

---

## 3. Random Forest (RF)

Characteristics:

* Ensemble of decision trees.
* Resistant to overfitting.
* Provides feature importance.

---

## 4. K-Nearest Neighbours (KNN)

Characteristics:

* Instance-based learner.
* Makes predictions based on neighboring observations.

---

# Model Evaluation Metrics

The following metrics are used to compare model performance.

## Accuracy

```text
Accuracy = Correct Predictions / Total Predictions
```

---

## Precision

```text
Precision = TP / (TP + FP)
```

---

## Recall

```text
Recall = TP / (TP + FN)
```

---

## F1-Score

```text
F1 = 2 × (Precision × Recall) / (Precision + Recall)
```

---

# Expected Outputs

The notebook generates:

* Evaluation metrics for all models.
* Classification reports.
* Confusion matrices.
* Feature importance analysis.
* Model comparison table.

Example:

| Model         | Accuracy | Precision | Recall | F1-Score |
| ------------- | -------- | --------- | ------ | -------- |
| ANN           |          |           |        |          |
| SVM           |          |           |        |          |
| Random Forest |          |           |        |          |
| KNN           |          |           |        |          |

---

# Project Structure

```text
├── data
│   ├── matches_1930_2022.csv
│   ├── fifa_ranking_2026-06-08.csv
│   └── world_cup.csv
│
├── notebooks
│   └── FIFA_World_Cup_Match_Prediction.ipynb
│
├── models
│   └── saved_models
│
├── README.md
└── requirements.txt
```

---

# Installation

```bash
git clone <repository-url>
cd fifa-world-cup-prediction
pip install -r requirements.txt
```

---

# Running the Project

```bash
jupyter notebook
```

Open:

```text
FIFA_World_Cup_Match_Prediction.ipynb
```

and run all cells.

---

# Future Improvements

* Incorporate recent international match results.
* Add Elo ratings.
* Include player-level statistics.
* Perform hyperparameter tuning.
* Implement cross-validation and model ensembling.
* Deploy the best-performing model as an API using Flask or Django.

---

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook

---

# Author

**Dominion Tom**

Computer Science Student | Data Analyst | Machine Learning Engineer | Sports Analytics Enthusiast
