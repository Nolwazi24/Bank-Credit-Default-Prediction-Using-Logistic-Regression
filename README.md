# Comparative Analysis of Traditional and Machine Learning-Based Logistic Regression for Credit Default Prediction

## Project Overview

This project investigates the use of traditional statistical logistic regression and machine learning-based logistic regression for predicting bank credit default.

The study compares the two approaches in terms of predictive performance and interpretability. The main objective is to determine whether machine learning-based logistic regression provides improved predictive performance compared with traditional logistic regression, while considering the trade-off between prediction accuracy and model interpretability.

## Dataset

The dataset contains financial information for banks between 2000 and 2011.

* Original number of records: 7,999
* Default cases: 143
* Non-default cases: 7,856
* Default rate: approximately 1.79%

The dataset is highly imbalanced, with default cases representing a small proportion of the observations.

During data cleaning, duplicate `(ID, Year)` combinations were identified and investigated. The duplicated records contained conflicting financial values and could not be treated as simple repeated observations. Therefore, the affected records were removed before further analysis.


## Variables

The financial variables used in the analysis include:

* Total Assets
* Reported Equity
* Loan Growth
* Tangible CE / Tangible Assets
* Internal Capital Generation
* Loans / Deposits
* Wholesale Funding / Total Funding
* Operating ROE

The target variable is:

* `Default`

  * `1`: Bank default
  * `0`: Non-default

## Methodology

The analysis consists of the following stages:

1. Data cleaning and preparation
2. Exploratory data analysis
3. Traditional logistic regression
4. Machine learning-based logistic regression
5. Model evaluation and comparison

### Traditional Logistic Regression

The traditional approach uses logistic regression estimated using Maximum Likelihood Estimation. Statistical analysis focuses on model coefficients and their interpretation.

### Machine Learning-Based Logistic Regression

The machine learning approach uses logistic regression as a predictive model and may include techniques such as regularisation and feature selection.

## Model Evaluation

The models are evaluated using:

* Accuracy
* Precision
* Recall
* AUC-ROC

K-fold cross-validation is used to assess model performance.

## Repository Structure

```text
├── data/
│   ├── raw/              # Original dataset (not included)
│   └── processed/        # Cleaned data
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_traditional_logistic_regression.ipynb
│   └── 04_ml_logistic_regression.ipynb
│
├── results/
│   ├── figures/          # Visualisations
│   └── tables/           # Model comparison results
│
├── .gitignore
├── README.md
└── requirements.txt
```

## Tools and Libraries

The analysis is conducted using Python and includes the following libraries:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* statsmodels
* scipy

## Research Focus

This project addresses the following questions:

1. How does machine learning-based logistic regression compare with traditional logistic regression in predicting bank default?
2. Does the machine learning approach improve AUC-ROC and recall?
3. What are the trade-offs between predictive performance and interpretability?

## Reproducibility

To install the required Python packages:

```bash
pip install -r requirements.txt
```

## Author

Nolwazi Sekhala
