# 📈 Jane Street Real-Time Market Data Forecasting — Exploratory Analysis & Data Preparation

This repository provides a comprehensive analysis and utility suite for the **Jane Street Real-Time Market Data Forecasting** competition on Kaggle. It focuses on **Exploratory Data Analysis (EDA)**, missing value inspection, temporal pattern discovery, and metadata understanding to support downstream modeling.

---
## 🎯 Objective

> **Build a forecasting model** that accurately predicts `responder_6` for multiple financial instruments, using features extracted from market microstructure data, with special consideration for missing data, symbol/date evolution, and non-stationarity.

---


## 🧠 Dataset Components

| File                | Description |
|---------------------|-------------|
| `train.parquet/`    | 10-part training set with `date_id`, `time_id`, `symbol_id`, `weight`, 79 features, and 9 responders |
| `features.csv`      | Metadata about each feature and their associated tags |
| `responders.csv`    | Metadata about each responder (including `responder_6`) |
| `test.parquet/`     | Mock single-time-batch test set used via API |
| `lags.parquet/`     | Lag-1 values of responders for each symbol_id |
| `sample_submission.csv` | Example submission format for predictions |

## 🔍 What’s Inside

### ✅ Dataset Overview
- **Training Data (`train.parquet`)** – 10 partitions with 79 features and 9 responders.
- **Test Data (`test.parquet`)** – Single date-time batch for API prediction.
- **Lags Data (`lags.parquet`)** – Responder values from previous date_id.
- **Metadata** – `features.csv`, `responders.csv`, and `sample_submission.csv`.

---

## 📌 Key Highlights

✅ End-to-end EDA pipeline for Kaggle’s market forecasting challenge  
✅ Optimized with `polars` for fast loading and computation  
✅ Ready-to-extend structure for modeling and feature engineering  
✅ Fully reproducible scripts + Jupyter notebooks  
✅ Aligned with API-specific submission formats  

---
## ⚙️ Setup Instructions

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/jane-street-market-forecasting.git
    cd jane-street-market-forecasting
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

---

## 🧠 Analysis Process

### 1. Data Loading
- Use `polars` for efficient loading and querying.
- Partitioned data handled by `load_train_partition(partition_id)`.

### 2. Missing Value Analysis
- Focused on non-null `responder_6` rows.
- Shows missing count and ratio per feature with visual bar plots.

### 3. Feature Correlation
- Correlation heatmap of all 79 features.
- Highlights clusters and multicollinearity.

### 4. Responder Insights
- Histograms for all 9 responders.
- Statistics (mean, std, min, max).
- Visual checks for clipped distributions (bounded between -5 and 5).

### 5. Symbol & Date Distribution
- Distribution of `symbol_id` and `date_id` across partitions.
- Ensures temporal and symbol consistency.

### 6. Test & Lag Dataset
- Validate structure of test sets and lag features.
- Aligns lag values for time-aware modeling.

---

## 🚀 Utility Scripts

You can use the following batch scripts:

- `scripts/run_null_analysis.py`  
  ➤ Generates missing value profiles.

- `scripts/run_feature_corr.py`  
  ➤ Creates feature-feature correlation heatmap.

---

## 🛠 Notebooks

All analysis is also available as interactive notebooks under `notebooks/`, including:
- `01_eda_features.ipynb`
- `02_eda_responders.ipynb`
- `03_missing_value_analysis.ipynb`
- `04_symbol_date_distribution.ipynb`

---

## 🧾 Requirements

Dependencies are listed in `requirements.txt`, including:
- pandas
- polars
- matplotlib
- seaborn
- numpy
- scikit-learn
- pyarrow
- jupyterlab

---


---

## 📌 License

This repository is distributed under the MIT License.


