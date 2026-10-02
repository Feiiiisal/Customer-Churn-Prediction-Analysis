# Customer Churn Prediction and Analysis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-classification-orange)
![Jupyter](https://img.shields.io/badge/notebook-Jupyter-lightgrey)

An end-to-end churn analysis for a telecom company: combining data from three
sources, exploring what drives customers to leave, testing hypotheses, and
training classification models to predict churn. The best model, a tuned
**Random Forest**, is served in the companion app
[ChurnPredictor-GradioApp](https://github.com/Feiiiisal/ChurnPredictor-GradioApp).

## Why it matters

Keeping an existing customer is cheaper than winning a new one. Knowing which
customers are likely to leave lets a company act early with offers or support.

## Data

The customer records are split across three places, as in a real project:

| Part | Records | Where |
|---|---|---|
| First dataset | first 3,000 | a remote SQL database (needs credentials, see below) |
| Second dataset | next 2,000 | `Telco-churn-second-2000.xlsx` (used as the test set) |
| Third dataset | last 2,000 | `LP2_Telco-churn-last-2000.csv` in this repository |

`df.csv` and `df_test.csv` are the prepared training and test tables.

## Approach

1. **Data collection**: load and combine the three sources.
2. **Exploratory analysis**: profiling reports, charts
   (`Descriptive_Statistics_Boxplots.html`) and statistical analysis.
3. **Preparation**: cleaning, feature engineering, encoding, scaling and class
   balancing with SMOTE.
4. **Modelling**: eight classifiers compared: SVC, Gaussian Naive Bayes, Decision
   Tree, Random Forest, XGBoost, Gradient Boosting, AdaBoost and Logistic
   Regression, followed by hyperparameter tuning of the best candidates.

## Results

The tuned **Random Forest** gave the most balanced results. On a balanced
evaluation set of 1,478 customers (739 per class) the notebook reports:

| Class | Precision | Recall | F1-score |
|---|---|---|---|
| No churn | 0.87 | 0.85 | 0.86 |
| Churn | 0.86 | 0.88 | 0.87 |

Overall **accuracy: 0.86**. Gradient Boosting reached 0.85, SVC 0.81 and
Gaussian Naive Bayes 0.75 in the same comparison.

## Repository contents

```
lp2_new.ipynb                       The full analysis and modelling notebook
LP2_Telco-churn-last-2000.csv       Third part of the data
Telco-churn-second-2000.xlsx        Second part of the data (test set)
df.csv, df_test.csv                 Prepared train / test tables
Descriptive_Statistics_Boxplots.html  Exported interactive charts
Export2/ml.pkl                      Saved trained model
requirements.txt
.env.example
```

## Setup

```bash
pip install -r requirements.txt
```

The notebook reads the first 3,000 records from an Azure SQL database using
credentials from a `.env` file. Copy `.env.example` to `.env` and fill in the
values you were given (never commit `.env`). Without database access you can
still work with the CSV and Excel files.

## License

[MIT](LICENSE)
