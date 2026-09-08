# =====================================================================
# 📊 PROJECT: End-to-End Loan Data Analysis & Exploration Pipeline
# =====================================================================
# Author       : Shahd Mohamed Sayed Ahmed
# Tech Stack   : Python | Pandas | NumPy | Matplotlib | Seaborn
# Target File  : loans.csv
# Pipeline State : Production-Ready & Cleaned
# =====================================================================

## 📌 01. PROJECT_OVERVIEW
This repository contains a comprehensive exploratory data analysis (EDA) and data engineering pipeline built to analyze lending records, evaluate borrower profiles, and extract actionable financial insights from raw loan data (`loans.csv`).

---

## ⚙️ 02. PIPELINE_EXECUTION_STEPS

### [STEP 1] Data_Ingestion & Initial_Inspection
  ├── import_libraries()      # Loaded pandas, numpy, matplotlib, and seaborn
  ├── pd.read_csv('loans.csv') # Ingested raw dataset records
  ├── df.shape                # Inspected structural boundaries -> (443 Rows, 8 Features)
  └── df.info()               # Examined initial schema and memory footprint

### [STEP 2] Data_Cleaning & Type_Casting
  ├── df['loan_id'] = df['loan_id'].astype(object)          # Formatted ID as categorical/object
  ├── df['repaid'] = df['repaid'].astype('category')        # Optimized memory for binary status
  ├── pd.to_datetime(df['loan_start'])                     # Converted start timestamps to datetime64[ns]
  ├── pd.to_datetime(df['loan_end'])                       # Converted end timestamps to datetime64[ns]
  └── df.isnull().sum()                                    # Verified data integrity (Confirmed 0 null values)

### [STEP 3] Exploratory_Data_Analysis (EDA) & Aggregations
  ├── df['loan_amount'].mean()                             # Computed baseline global average (~7,982.31)[cite: 2]
  ├── high_value_filter = df[df['loan_amount'] > threshold]# Isolated top-tier portfolio exposures
  └── df.groupby('loan_type')['loan_amount'].mean()        # Evaluated average distributions across categories:
      ├── Category: 'home'
      ├── Category: 'credit'
      ├── Category: 'cash'
      └── Category: 'other'

### [STEP 4] Statistical_Summaries & Outlier_Detection (IQR Method)
  ├── df.describe(include='all')                           # Generated full statistical profile (count, mean, std, min, max, percentiles)
  ├── Q1 = df['loan_amount'].quantile(0.25)                # Calculated 25th percentile
  ├── Q3 = df['loan_amount'].quantile(0.75)                # Calculated 75th percentile
  ├── IQR = Q3 - Q1                                        # Computed Interquartile Range
  └── outlier_bounds [Lower_Bound, Upper_Bound]            # Flagged and handled extreme value anomalies

---

## 🗂️ 03. SCHEMA_DOCUMENTATION
The dataset consists of 8 core features tracking loan lifecycles:
  ├── client_id   : Unique alphanumeric identifier assigned to each client[cite: 2]
  ├── loan_id     : Unique identifier tracking individual loan issuance[cite: 2]
  ├── loan_type   : Categorical segmentation (home, credit, cash, other)[cite: 2]
  ├── loan_amount : Numerical financial valuation of the distributed loan[cite: 2]
  ├── repaid      : Target indicator flag (1 = fully repaid, 0 = default/unpaid)[cite: 2]
  ├── loan_start  : Timestamp marking the initiation of the loan agreement[cite: 2]
  ├── loan_end    : Timestamp marking the closure or maturity of the loan[cite: 2]
  └── rate        : Annualized or applicable interest rate applied to the loan[cite: 2]

---

## 🚀 04. QUICK_START_GUIDE
To replicate or run this analysis locally, execute the following commands in your terminal:

  $ git clone https://github.com/your-username/loan-data-analysis.git
  $ cd loan-data-analysis
  $ pip install -r requirements.txt
  $ jupyter notebook loan_analysis.ipynb

# =====================================================================
# [EXECUTION STATUS]: SUCCESS. All pipeline checks passed cleanly.
# =====================================================================
