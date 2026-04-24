# NYC 311 Modeling Plan

**Date created:** 04/01/2026

## Business question
Predict what factors drive resolution time

## Data source
- **S3 path:** cmse492-hopki219-nyc311-339713165743-us-east-1-an/raw/
- **Records:** 173851
- **Athena query:** sql/athena_to_modeling.sql

## Features (update/expand based on your query)
- agency (string)
- borough (string)
- n_complaints (numeric, count of complaints)
- avg_days_to_close (numeric, average resolution time)
- ... (other features)

## Target
- **Name:** days_to_close
- **Type:** Classification
- **Balance/Distribution:** Class balance: {0: 0.622, 1: 0.101, 2: 0.071, 3: 0.047, 4: 0.033, 5: 0.026, 6: 0.018, 7: 0.011, 8: 0.008, 9: 0.007, 10: 0.005, 11: 0.004, 12: 0.004, 13: 0.004, 14: 0.003, 15: 0.003, 16: 0.003, 17: 0.002, 19: 0.002, 18: 0.002, 20: 0.002, 21: 0.002, 22: 0.002, 23: 0.002, 26: 0.001, 30: 0.001, 25: 0.001, 24: 0.001, 27: 0.001, 29: 0.001, 28: 0.001, 32: 0.001, 31: 0.001, 33: 0.001, 35: 0.001, 36: 0.001, 34: 0.001, 40: 0.0, 38: 0.0, 37: 0.0, 41: 0.0, 39: 0.0, 42: 0.0, 45: 0.0, 43: 0.0, 44: 0.0, 46: 0.0, 48: 0.0, 47: 0.0, 49: 0.0}

## Modeling approach
- **Baseline:** Logistic regression (interpretable, fast to train)
- **Metrics:** Accuracy, precision, recall
- **Train/test split:** 80/20

## Data quality notes
- [Any missing values, outliers, or issues to watch for]

## Next steps (What you'll work on in the next class period; update/modify based on your plan)
- Train/test split
- Fit baseline logistic regression
- Evaluate and interpret results