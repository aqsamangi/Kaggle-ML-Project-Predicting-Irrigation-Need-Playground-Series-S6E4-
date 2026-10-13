# Predicting Irrigation Need | Kaggle Playground Series S6E4

## Overview

This project focuses on predicting agricultural irrigation requirements using machine learning. It is a multiclass classification problem in which the goal is to classify irrigation needs as **Low, Medium, or High** based on agricultural and environmental features.

The project was completed as part of a machine learning assignment using the Kaggle Playground Series S6E4 competition.

**Competition:** [Predicting Irrigation Need - Kaggle](https://www.kaggle.com/competitions/playground-series-s6e4)

## Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- Jupyter Notebook

## Dataset

The dataset contains numerical and categorical features related to soil properties, crop characteristics, and environmental conditions.

- `train.csv`: Training data containing features and target labels.
- `test.csv`: Test data used to generate predictions.
- `sample_submission.csv`: Template specifying the required submission format.

The dataset can be accessed from the Kaggle competition page linked above.

## Methodology

### 1. Data Preprocessing

- Separated features, target labels, and test IDs.
- Used `LabelEncoder` to encode the target classes.
- Applied `SimpleImputer` to handle missing values.
- Used `OneHotEncoder` for categorical features.
- Combined preprocessing steps using `ColumnTransformer` and `Pipeline`.

### 2. Model Training and Evaluation

Four classification models were compared:

- Decision Tree
- Gaussian Naive Bayes
- Logistic Regression
- Random Forest

The data was split into training and validation sets using an 80/20 stratified split. Models were evaluated using **Balanced Accuracy** to account for the imbalanced target classes.

Five-fold stratified cross-validation was also performed on the selected model.

### 3. Results

| Model | Validation Balanced Accuracy |
|---|---:|
| Random Forest | 0.9579 |
| Decision Tree | 0.9494 |
| Gaussian Naive Bayes | 0.7794 |
| Logistic Regression | 0.6654 |

Random Forest achieved the highest validation balanced accuracy and was selected for final prediction generation.

### 4. Final Submission

The selected model was retrained on the full training dataset and used to predict irrigation requirements for the test data.

The generated `submission.csv` contains the required columns:

- `id`
- `Irrigation_Need`

The predictions are provided as the original class labels: Low, Medium, and High.

## Kaggle Performance

- **Public leaderboard score:** 0.95904
- **Evaluation metric:** Balanced Accuracy

Leaderboard scores and rankings may change as competition results are updated.

## Repository Contents

- `README.md`: Project documentation.
- `irrigation_need_prediction.ipynb`: Notebook containing preprocessing, model training, evaluation, cross-validation, and submission generation.
- `submission.csv`: Final prediction file.

## How to Run

1. Download `train.csv`, `test.csv`, and `sample_submission.csv` from the Kaggle competition page.
2. Place the CSV files in the notebook's working directory.
3. Install the required libraries if they are not already available.
4. Open and run `irrigation_need_prediction.ipynb` from the first cell to the last.
5. The notebook generates `submission.csv` containing the predictions.

## Key Learnings

- Building preprocessing pipelines for mixed numerical and categorical data.
- Comparing classification algorithms using balanced accuracy.
- Evaluating models with stratified cross-validation.
- Training a final model on the full dataset and preparing a Kaggle submission.
