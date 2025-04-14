
# 🏎️ F1 Race Results Prediction with FastF1 + scikit-learn

This project explores predictive modeling for Formula 1 race outcomes using the [FastF1](https://theoehrly.github.io/Fast-F1/) library and `scikit-learn`. By analyzing qualifying data and race metrics, it aims to predict whether a driver will finish in the top 10. Several script variations allow for experimentation with different driver groups and data conditions.

---

## 📁 Project Files

| File Name                  | Description |
|---------------------------|-------------|
| `prediction1.py`          | Main model: collects FastF1 race/qualifying data, trains a Decision Tree to classify drivers finishing in the top 10. |
| `prediction2.py`          | Refined version of `prediction1.py`, streamlining data cleaning and focusing on current drivers only. |
| `prediction2_nochange.py` | Tests the model while leaving some driver identity and result conditions untouched. Serves as a control case. |
| `prediction2_olddrivers.py` | Focuses on past or historical drivers. Aims to test how the model generalizes beyond current season data. |

---

## 🚀 Project Overview
This repository contains a **Gradient Boosting Machine Learning model** that predicts race results based on past performance, qualifying times, and other structured F1 data. The model leverages:
- FastF1 API for historical race data
- 2024 race results
- 2025 qualifying session results
- Over the course of the season we will be adding additional data to improve our model as well
- Feature engineering techniques to improve predictions

## 📊 Data Sources
- **FastF1 API**: Fetches lap times, race results, and telemetry data
- **2025 Qualifying Data**: Used for prediction
- **Historical F1 Results**: Processed from FastF1 for training the model

## ⚙️ How It Works

1. Enable FastF1's cache and load a qualifying & race session.
2. Extract driver-level features:
   - Qualifying position
   - Fastest lap time
   - Race completion status
   - Driver names (optionally anonymized)
3. Preprocess and encode features.
4. Train a `DecisionTreeClassifier` on labeled data.
5. Evaluate the model's ability to predict top-10 finishes.

---

## 📦 Requirements

```bash
pip install fastf1 scikit-learn pandas numpy
```

Ensure you create a cache directory for FastF1:

```bash
mkdir f1_cache
```

---

## ▶️ Run the Code

```bash
python prediction1.py
# or any other variant:
python prediction2.py
python prediction2_nochange.py
python prediction2_olddrivers.py
```

---

## 🧪 Model

- **Algorithm**: `DecisionTreeClassifier` from scikit-learn
- **Target**: Binary (Top 10 finish = 1, otherwise = 0)
- **Feature Engineering**:
  - Lap times converted to numeric
  - Qualifying results as integer rank
  - Status mapped to binary outcome (Finished or not)

---

## 📌 Notes

- All scripts assume internet access to pull data from the FastF1 API.
- Be sure to run qualifying and race sessions from the **same event**.
- Models are relatively simple—useful for experimentation or as a foundation for more complex ML workflows.

---
## 📈 Model Performance
The Mean Absolute Error (MAE) is used to evaluate how well the model predicts race times. Lower MAE values indicate more accurate predictions.

## 📈 Future Enhancements

- Replace `DecisionTreeClassifier` with ensemble methods (e.g., RandomForest, XGBoost)
- Visualize prediction performance with confusion matrix and ROC curves
- Include weather and pit stop data as features
- Deploy predictions as an API or web app
- Explore **deep learning** models for improved accuracy

---

*Developed by Mohammed Chauhan – 2025*
