# Automated Analysis Pipeline Exploration

## Overview

This project was completed for HSE 751: Programming for Health Data Science. The purpose of the notebook is to explore how conditional logic, automated data processing, statistical analysis, and machine learning can be integrated into a structured and reproducible health data science workflow.

The provided automated analysis pipeline was executed and modified using the Pima Indians Diabetes Database. The notebook demonstrates data ingestion, data-quality assessment, exploratory analysis, inferential statistics, preprocessing, supervised machine learning, and model evaluation.

Four additional automated workflow components were implemented to extend the original pipeline:

1. **Automated Data Quality Audit** – evaluates variables for missing values, zero values, data types, and other potential data-quality concerns.
2. **Automated Visualization Selection** – uses conditional logic to select an appropriate visualization based on whether a user-selected variable is numeric or categorical.
3. **Expanded Machine Learning Model Comparison** – adds a Random Forest classifier to the existing Logistic Regression and Decision Tree models and evaluates it using the same test data and performance metrics.
4. **Automated Best-Model Selection** – allows the user to specify an evaluation metric and automatically identifies the best-performing model according to that analytical goal.

## Dataset

The analysis uses the **Pima Indians Diabetes Database**, which contains diagnostic measurements for women aged 21 years or older of Pima Indian heritage.

The binary outcome variable, `Outcome`, indicates diabetes status:

- `0` = No diabetes
- `1` = Diabetes

The dataset contains **768 observations and 9 variables**.

Both the original Excel dataset and a CSV version are included in this repository to support reproducibility.

## Running the Analysis

The notebook can be run in Google Colab without requiring a local Python installation.

### Open in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1B8ZTEaVrJsS38yAOPXGGR-n-6JRhGy1G?usp=sharing)

To reproduce the analysis:

1. Open the notebook using the Colab badge above.
2. Upload the dataset when prompted by the automated data-ingestion cell.
3. Run the notebook cells sequentially from top to bottom.
4. Review the generated data-quality reports, visualizations, statistical analyses, and machine learning results.

The notebook uses a fixed random seed (`random_state=42`) where applicable to improve reproducibility.

## Required Software and Libraries

The analysis was developed in **Google Colab using Python 3**.

The primary Python libraries used include:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scipy`
- `statsmodels`
- `scikit-learn`

These libraries are available in the standard Google Colab environment.

## Machine Learning Workflow

The supervised machine learning portion of the notebook evaluates three binary classification models:

- Logistic Regression
- Decision Tree
- Random Forest

Models are evaluated using:

- Accuracy
- Recall
- Precision
- F1 score
- ROC AUC

The automated model-selection modification allows the user to select a performance metric and identifies the model with the highest score for that metric.

Using **F1 score** as the selection criterion in this analysis, the Decision Tree was selected as the best-performing model with an F1 score of **0.654**.

## Assumptions and Limitations

Several considerations should be kept in mind when interpreting the analysis:

- The dataset is used for educational and demonstration purposes and should not be interpreted as a clinically validated prediction tool.
- The study population consists of women aged 21 years or older of Pima Indian heritage, which limits generalizability to other populations.
- Some clinical variables contain zero values that may represent missing or invalid measurements rather than true physiological values.
- The automated data-quality audit identified potential invalid zeros and missing values that require appropriate preprocessing.
- Median imputation is used for missing predictor values within the machine learning pipeline.
- Model performance is based on a single training/test split and may vary with different samples or modeling approaches.
- Different performance metrics prioritize different aspects of classification performance; therefore, the preferred model depends on the analytical objective.

## Repository Contents

- `Automated_Analysis_Pipeline_Notebook.ipynb` – completed analysis notebook
- Pima Indians Diabetes dataset (`.xlsx`) – original dataset
- Pima Indians Diabetes dataset (`.csv`) – CSV version for reproducibility
- `README.md` – project documentation
