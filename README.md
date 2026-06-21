# Cafe Sales Data Cleaning & Profiling Pipeline

## 📌 Project Overview
This project builds an automated data engineering pipeline to ingest, profile, and clean a real-world cafe sales dataset. The raw transactional data contained severe structural anomalies, missing values, and corrupted data types that prevented accurate business analysis.

## 🛠️ Tech Stack & Tools
- **Language:** Python
- **Libraries:** Pandas, NumPy
- **Environments:** Kaggle Notebook

## 🔍 Data Quality Issues Identified & Resolved
1. **Structural Anomaly Handling:** Detected text-based error placeholders like "UNKNOWN" and "ERROR" and systematically replaced them with proper numerical null formats (`np.nan`).
2. **Categorical Data Imputation:** Handled missing text data in critical columns (`Item`, `Payment Method`, `Location`) by cleanly filling null cells with a default `"Unknown"` flag.
3. **Type Conversion & Corrupted Data Fixes:** Enforced strict data types by converting messy object columns (`Quantity`, `Price Per Unit`, `Total Spent`) into explicit numerical formats using `pd.to_numeric()` with error coercion.
4. **Skew-Resistant Imputation:** Filled missing numerical fields by calculating and injecting column-specific `median()` values to protect against data skew.
5. **Datetime Standardization:** Eliminated records missing structural timestamps and standardized valid date strings into clear, formal `datetime` schemas using `pd.to_datetime()`.

## 📊 Final Results
The completed pipeline successfully transforms raw, unaligned transactional logging data into a clean, normalized, and production-ready tabular dataset. It outputs a standardized file (`cleaned_cafe_sales.csv`) that is fully optimized for downstream statistical modeling and visualization.
