# Air Quality Index (AQI) Prediction

Archived course project — a regression pipeline predicting AQI for Indian monitoring stations from pollutant measurements. Kept private as a record of coursework.

## Summary

- **Data:** `station_day.csv` (Kaggle — "Air Quality Data in India"), 108,035 station-day records; pollutant features: PM2.5, PM10, NO2, CO, SO2, O3.
- **Cleaning:** median imputation for missing values, boxplot-based outlier inspection, feature selection down to 7 columns.
- **Models compared** (validation split): Linear Regression (R² 0.793), Gradient Boosting (0.863), KNN (0.866), Random Forest (0.879).
- **Tuning:** Random Forest via `RandomizedSearchCV` (25 iterations, 3-fold CV over depth, features, leaf/split sizes).
- **Final test performance:** **R² 0.887 · MAE 21.8 · RMSE 41.4.**
- **Extra:** predictions bucketed into official AQI categories (Good → Severe) with a per-class classification report; tuned model persisted with `joblib`.

## Run

```bash
pip install -r requirements.txt
# place station_day.csv next to the notebook
jupyter notebook notebook/AQI_prediction.ipynb
```

