# Student Performance Prediction System

A classroom prototype that flags students who may be at risk of failing the final Mathematics grade.

## Problem
Academic risk is often noticed only after poor results. This prototype explores early identification using available student indicators (study time, absences, failures, G1, G2, etc.).

## Dataset
[UCI Machine Learning Repository – Student Performance](https://archive.ics.uci.edu/dataset/320/student+performance), fetched with `ucimlrepo` (ID 320).

## Prediction target
`G3 < 10` → **AT RISK**; `G3 >= 10` → **NOT AT RISK**. G3 is the target only and is never used as an input feature (avoids target leakage).

## Technologies
Python 3.10+, pandas, scikit-learn (Random Forest), joblib, Streamlit, GitHub.

## Installation and run
```bash
pip install -r requirements.txt
python train_model.py      # downloads data, trains model, creates student_data.csv and student_model.pkl
streamlit run app.py       # opens http://localhost:8501
```
In the app, download the sample input CSV, then upload it to see predictions. Removing a required column should show an error message.

## Limitations
- Trained on one Portuguese secondary-school dataset; it may not generalize to other institutions or populations.
- Predictions are not diagnoses and must not be the sole basis for real student decisions.
- Accuracy alone is not enough; review precision, recall and F1-score, especially recall for the "At risk" class.
