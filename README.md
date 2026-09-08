# 📊 End-to-End Loan Data Analysis & Exploration Pipeline

[![Python](https://img.shields.io/badge/Python-3.8%252B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-orange.svg)](https://pandas.pydata.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()

A comprehensive exploratory data analysis (EDA) and data pipeline project built to process, clean, and extract financial insights from loan records (`loans.csv`).

---

## 🚀 Project Overview
This repository implements a complete data analysis lifecycle. The workflow focuses on rigorous data cleaning, type optimization, statistical aggregation, and anomaly detection to uncover core lending trends and portfolio behaviors.

---

## ⚙️ Pipeline Workflow

### 1. Data Ingestion & Inspection
* **Loading:** Ingested raw loan records using `pandas.read_csv()`.
* **Shape Verification:** Inspected structural boundaries, confirming a dataset size of **443 rows and 8 features**.
* **Schema Audit:** Evaluated initial data types and memory allocation.

### 2. Data Cleaning & Type Casting
* **`loan_id`**: Converted from numerical format to `object` dtype for categorical tracking.
* **`repaid`**: Cast into `category` dtype to optimize classification workflows.
* **Timestamps (`loan_start` & `loan_end`)**: Parsed successfully into standard `datetime64[ns]` formats to enable temporal analysis.
* **Data Integrity:** Validated null counts across all columns, confirming **0 missing values**.

### 3. Exploratory Data Analysis (EDA) & Aggregations
* **Global Metrics:** Computed baseline indicators, including a global average loan amount of `~7,982.31`[cite: 2].
* **Conditional Filtering:** Isolated high-value loan exposures to track major portfolio risks.
* **Categorical Grouping:** Evaluated average distributions segmented by `loan_type` (home, credit, cash, other)[cite: 2].

### 4. Statistical Summaries & Outlier Detection
* **Descriptive Statistics:** Generated full statistical profiles (count, mean, standard deviation, min, max, and percentiles).
* **IQR Method:** Calculated Interquartile Ranges ($Q1, Q3, \text{IQR}$) to detect and isolate extreme anomalies in `loan_amount` distributions.

---

## 🗂️ Dataset Schema

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `client_id` | Object / String | Unique identifier assigned to each client[cite: 2] |
| `loan_id` | Object / String | Unique identifier tracking individual loan issuance[cite: 2] |
| `loan_type` | Category | Classification category (home, credit, cash, other)[cite: 2] |
| `loan_amount` | Numeric (Float/Int) | Financial valuation of the issued loan[cite: 2] |
| `repaid` | Category (Binary) | Repayment status flag (1 = Repaid, 0 = Default)[cite: 2] |
| `loan_start` | Datetime | Timestamp marking loan initiation[cite: 2] |
| `loan_end` | Datetime | Timestamp marking loan closure/maturity[cite: 2] |
| `rate` | Numeric | Applicable annual interest rate[cite: 2] |

---

## 🛠️ Tech Stack & Libraries
* **Python**: Core logic and script execution.
* **Pandas & NumPy**: Data manipulation, cleaning, and mathematical aggregations.
* **Matplotlib & Seaborn**: Exploratory data visualization and plotting.

---

## 💻 Quick Start Guide

To run this analysis locally on your machine, follow these steps:

1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/loan-data-analysis.git](https://github.com/your-username/loan-data-analysis.git)
