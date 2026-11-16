# project-28

# NVIDIA Historical Stock Trading Analysis

## 1. Project Overview

This project investigates NVIDIA (NVDA) historical stock trading patterns using exploratory data analysis, supervised machine learning, and unsupervised clustering.

The analysis examines stock returns, price movements, trading volatility, downside risk, and historical market regimes.

Multiple machine learning models are compared to evaluate their suitability for different research questions. Model selection is based on task-specific evaluation metrics, with particular attention to time-series structure, predictive performance, interpretability, and appropriate baseline comparisons.

The project is implemented in Python using a Quarto (`.qmd`) notebook.

## 2. Research Objectives

The project addresses five research questions:

| RQ | Research Question | Analytical Approach |
|---|---|---|
| RQ1 | Can historical trading indicators predict NVIDIA's next-day stock returns? | Regression |
| RQ2 | Can historical trading indicators predict the direction of NVIDIA's next-day stock returns? | Binary Classification |
| RQ3 | Can historical trading indicators predict the magnitude of NVIDIA's next-day price movements? | Regression |
| RQ4 | Can historical trading indicators identify the risk of large next-day stock price declines? | Binary Classification |
| RQ5 | What distinct historical trading regimes can be identified from NVIDIA's trading characteristics? | K-Means Clustering |

These questions examine different aspects of stock market behavior, including return predictability, directional classification, volatility-related price movements, downside risk, and historical trading environments.

## 3. Dataset Description

The project uses historical daily trading data for NVIDIA Corporation (NVDA).

The dataset contains approximately 6,957 daily return observations after calculating daily percentage changes.

### Main Variables

| Variable | Description |
|---|---|
| Date | Trading date |
| Open | Opening stock price |
| High | Highest trading price |
| Low | Lowest trading price |
| Close | Closing stock price |
| Volume | Daily trading volume |
| Daily Return | Percentage change in closing price |
| Intraday Return | Percentage change between opening and closing prices |
| Daily Range | Intraday price range expressed as a percentage |
| Overnight Gap | Percentage difference between the previous close and current open |
| Rolling Volatility | Historical volatility calculated over a rolling window |
| Drawdown | Percentage decline relative to a historical price peak |
| Moving Averages | Rolling average prices over specified periods |

Additional lagged returns, rolling statistics, and technical indicators are constructed during feature engineering.

## 4. Data Preprocessing

Data preprocessing is performed before model development to ensure consistent and reliable analysis.

The preprocessing workflow includes:

1. Converting trading dates into a consistent datetime format.
2. Sorting observations chronologically.
3. Checking missing values, duplicate observations, and variable types.
4. Identifying categorical or textual variables that require appropriate encoding.
5. Constructing historical trading indicators using available information.
6. Generating next-day prediction targets through forward shifting.
7. Removing observations with unavailable target values.
8. Applying feature imputation and scaling where required.

Preprocessing transformations used for modeling are fitted on the training data to reduce data leakage.

## 5. Project Structure

A suggested project organization is:

```text
NVIDIA-Stock-Analysis/
│
├── data/
│   └── NVDA.csv
│
├── NVDA_Analysis.qmd
│
├── README.md
│
└── outputs/
    ├── figures/
    └── tables/
```

The actual dataset and notebook filenames should be adjusted to match the local project files.

## 6. Software and Dependencies

The project uses Python and Quarto.

### Main Python Libraries

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
