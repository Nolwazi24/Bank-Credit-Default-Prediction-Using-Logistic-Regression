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

# Comparative Analysis of Traditional and Machine Learning-Based Logistic Regression for Credit Default Prediction

## Project Overview

This project investigates the use of traditional statistical logistic regression and machine learning-based logistic regression for predicting bank credit default.

The study compares the two approaches in terms of predictive performance and interpretability. The main objective is to determine whether machine learning-based logistic regression provides improved predictive performance compared with traditional logistic regression, while considering the trade-off between predictive performance and model interpretability.

The analysis is organised into two main notebooks:

1. **Data Cleaning, Exploratory Data Analysis, Train-Test Split and Scaling** – data preparation, quality checks, exploratory analysis, train-test splitting and scaling.
2. **Logistic Regression Models** – implementation of both traditional and machine learning-based logistic regression, followed by model evaluation and comparison.

---

## Dataset

The dataset contains financial information for banks between 2000 and 2011.

* **Original number of records:** 7,999
* **Default cases:** 143
* **Non-default cases:** 7,856
* **Default rate:** approximately 1.79%

The dataset is highly imbalanced, with default cases representing a small proportion of the observations.

During data cleaning, duplicate `(ID, Year)` combinations were identified and investigated. The duplicated records contained conflicting financial values and could not be treated as simple repeated observations. Therefore, the affected records were removed before model implementation.

---

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

### Target Variable

The target variable is `Default`:

* `1` = Bank default
* `0` = Non-default

---

## Methodology

The analysis follows two main stages.

### 1. Data Cleaning, EDA, Train-Test Split and Scaling

The first notebook combines data preparation and exploratory analysis with the steps required to prepare the data for modelling.

This stage includes:

* Inspecting the structure of the dataset
* Checking data types
* Checking for missing values
* Identifying and investigating duplicate `(ID, Year)` records
* Removing problematic duplicate observations
* Examining the distribution of the `Default` variable
* Assessing class imbalance
* Exploring the distributions of the financial variables
* Examining relationships between financial variables and default
* Checking multicollinearity using Variance Inflation Factor (VIF)
* Splitting the data into training and testing sets
* Scaling the predictor variables where required

The data is **split into training and testing sets before scaling** to prevent information from the test set from influencing the scaling process.

A fixed `random_state = 42` is used for reproducibility.

Two versions of the prepared data are produced:

* **Unscaled data** for the traditional Maximum Likelihood Estimation (MLE) logistic regression.
* **Scaled data** for the machine learning logistic regression with L1 regularisation.

VIF is also re-checked using the training data to assess whether the treatment of multicollinearity remains appropriate after the train-test split.

### 2. Logistic Regression Model Implementation and Comparison

Both logistic regression approaches are implemented in the second notebook.

#### Traditional Logistic Regression

The traditional statistical approach uses logistic regression estimated using **Maximum Likelihood Estimation (MLE)**.

The analysis focuses on:

* Estimated coefficients
* Statistical significance
* Model interpretation
* Predictions
* Predictive performance

#### Machine Learning Logistic Regression

The machine learning approach uses **logistic regression with L1 regularisation**.

The model is trained using the scaled training data and evaluated using the test data. The L1 penalty allows the model to perform regularisation and can reduce the influence of less important predictors.

Both approaches are implemented in the same notebook to allow for a direct comparison.

---

## Model Evaluation

The two models are evaluated and compared using:

* **Accuracy**
* **Precision**
* **Recall**
* **AUC-ROC**

Because the dataset is highly imbalanced, particular attention is given to **recall and AUC-ROC**, rather than relying on accuracy alone.

---

## Research Focus

This project addresses the following research questions:

1. How does machine learning-based logistic regression compare with traditional logistic regression in predicting bank default?

2. Does the machine learning approach improve predictive performance, particularly in terms of AUC-ROC and recall?

3. What are the trade-offs between predictive performance and interpretability between the two approaches?

---

## Repository Structure

```text
Bank-Credit-Default-Prediction-Using-Logistic-Regression/
│
├── data/
│   ├── raw/                         # Original dataset (not included)
│   └── processed/                   # Cleaned and prepared data
│
├── notebooks/
│   ├── 01_data_cleaning_eda_split_scaling.ipynb
│   └── 02_logistic_regression_models.ipynb
│
├── results/
│   ├── figures/                     # Visualisations and model plots
│   └── tables/                      # Model results and comparisons
│
├── .gitignore
├── README.md
└── requirements.txt
```

### Notebook Overview

| Notebook                                   | Description                                                                                                                                 |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `01_data_cleaning_eda_split_scaling.ipynb` | Data cleaning, duplicate investigation, exploratory data analysis, class imbalance analysis, VIF analysis, train-test splitting and scaling |
| `02_logistic_regression_models.ipynb`      | Traditional MLE logistic regression, machine learning logistic regression with L1 regularisation, model evaluation and comparison           |

---

## Tools and Libraries

The analysis is conducted using Python and includes the following libraries:

* **pandas** – data manipulation and analysis
* **numpy** – numerical computation
* **matplotlib** – data visualisation
* **seaborn** – statistical visualisation
* **scikit-learn** – machine learning, preprocessing and model evaluation
* **statsmodels** – statistical logistic regression and inference
* **scipy** – statistical analysis and supporting computations

---

## Reproducibility

The notebooks should be run in the following order:

```text
01_data_cleaning_eda_split_scaling.ipynb
                    ↓
02_logistic_regression_models.ipynb
```

A fixed `random_state = 42` is used during the train-test split to ensure reproducibility.

The original dataset is not included in this repository.

To install the required Python packages:

```bash
pip install -r requirements.txt
```

---

## Author

**Nolwazi Sekhala**

