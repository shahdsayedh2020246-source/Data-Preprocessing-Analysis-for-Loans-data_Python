# =====================================================================
# 📊 PROJECT: Loan Data Analysis & Exploration Pipeline
# =====================================================================
# Author       : Shahd Mohamed Sayed Ahmed
# Stack        : Python | Pandas | NumPy | Matplotlib | Seaborn
# Target Data  : loans.csv (443 Rows × 8 Features)
# Status       : Completed & Cleaned
# =====================================================================

## 📁 01_DATA_INGESTION_AND_INSPECTION
  ├── load_dataset()          # Loaded 'loans.csv' successfully
  ├── check_shape()           # Verified dimensions: (443 rows, 8 columns)
  └── inspect_dtypes()        # Identified mixed column types

## 🧹 02_DATA_CLEANING_AND_TRANSFORMATION
  ├── convert_to_object()     # Cast 'loan_id' to object type
  ├── convert_to_category()   # Cast 'repaid' status to category type
  ├── parse_datetimes()       # Converted 'loan_start' & 'loan_end' to datetime64
  └── missing_values_check()  # Confirmed 0 null values across all features

## 🔍 03_EXPLORATORY_DATA_ANALYSIS_EDA
  ├── compute_baselines()     # Calculated overall mean loan amount (~7,982.31)
  ├── filter_high_value()     # Isolated high-exposure loan records
  └── group_by_category()     # Evaluated average distributions across:
      ├── 'home'
      ├── 'credit'
      ├── 'cash'
      └── 'other'

## 📈 04_STATISTICAL_SUMMARIES_AND_OUTLIERS
  ├── generate_describe()     # Computed statistical metrics (count, mean, std, min, max)
  └── iqr_outlier_detection() # Detected and bounded outliers in 'loan_amount'

## ⚙️ QUICK_START_GUIDE
  $ git clone https://github.com/your-username/loan-data-analysis.git
  $ pip install numpy pandas matplotlib seaborn
  $ python main_analysis.py

# =====================================================================
# [STATUS]: Pipeline executed successfully with zero errors.
# =====================================================================
