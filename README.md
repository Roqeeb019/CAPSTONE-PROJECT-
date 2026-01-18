# Chronic Kidney Disease Prediction Pipeline

## Project Overview
This project develops a comprehensive machine learning pipeline for the prediction of Chronic Kidney Disease (CKD) using the 'chronic-kidney-disease-dataset-analysis' dataset. The pipeline covers all essential stages from environment setup and data acquisition to exploratory data analysis, data preprocessing, machine learning model training, and evaluation. The goal is to provide a robust and reproducible framework for CKD prediction.

## Setup Instructions

### 1. Environment Configuration
To set up the project environment, you need to install the required Python libraries. A `requirements.txt` file is generated automatically when the `main.py` script is run for the first time.

To manually install dependencies, run:
```bash
pip install -r requirements.txt
```

### 2. Kaggle API Credentials
To download the dataset, you need to configure your Kaggle API credentials. Follow these steps:
1.  **Download `kaggle.json`**: Go to your Kaggle account page (Profile -> Account), scroll down to the 'API' section, and click 'Create New API Token'. This will download a `kaggle.json` file.
2.  **Place `kaggle.json`**: Upload the `kaggle.json` file to your working directory (e.g., `/content/` in a Colab environment). The `main.py` script will automatically move it to `~/.kaggle/` and set the correct permissions.

Alternatively, you can set `KAGGLE_USERNAME` and `KAGGLE_KEY` as environment variables.

## How to Run the Project
The entire machine learning pipeline can be executed by running the `main.py` script. This script orchestrates all the steps, including environment setup, data download, EDA, preprocessing, and model training/evaluation.

```bash
python main.py
```

### Pipeline Stages:
1.  **Project Setup and Environment Configuration**: Installs necessary Python libraries and generates `requirements.txt`.
2.  **Data Acquisition**: Downloads the 'chronic-kidney-disease-dataset-analysis' dataset from Kaggle into a `data/` directory.
3.  **Exploratory Data Analysis (EDA)**: Loads the dataset, performs initial data exploration (info, describe, missing values), visualizes feature distributions (histograms), and calculates/visualizes the correlation matrix.
4.  **Data Preprocessing and Feature Engineering**: Cleans the data by dropping irrelevant columns ('DoctorInCharge', 'PatientID'), separates features and target, and scales numerical features using `StandardScaler`.
5.  **Machine Learning Model Training and Evaluation**: Splits the data into training and testing sets, trains a Logistic Regression model and a Random Forest Classifier, and evaluates their performance using accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrices.

## Key Findings & Model Performance Summary
After preprocessing and scaling, two classification models were trained:

### Logistic Regression
-   **Accuracy**: 0.9337
-   **Precision**: 0.9387
-   **Recall**: 0.9935
-   **F1-Score**: 0.9653
-   **ROC-AUC**: 0.8259

### Random Forest Classifier
-   **Accuracy**: 0.9307
-   **Precision**: 0.9305
-   **Recall**: 1.0000
-   **F1-Score**: 0.9640
-   **ROC-AUC**: 0.7689

Both models showed strong performance, with Logistic Regression achieving slightly better overall metrics (especially ROC-AUC) on this dataset, while Random Forest had perfect recall (identifying all positive cases).

## Data Source
The dataset used in this project is 'chronic-kidney-disease-dataset-analysis' from Kaggle.

## Acknowledgements
Special thanks to the dataset provider on Kaggle for making this data available.
