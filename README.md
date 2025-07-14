# Wine-Quality-Prediction
🔍 Overview
This project predicts wine quality from physicochemical attributes and presents the results in a Power BI dashboard built on the scaled feature set (StandardScaler). It covers data cleaning, preprocessing, model selection, tuning, and interactive visualisation.

📌 Objective
Classify wine samples into quality tiers (Low, Medium, High) so producers can automate routine quality checks.

📁 Dataset
Source: UCI Wine Quality (red & white combined)

Features: 11 physicochemical inputs → scaled to μ = 0, σ = 1 before modelling and before exporting to Power BI.

Label: Quality score (0–10)

⚙️ Techniques & Algorithms Used
Stage	Key Steps
Pre‑processing	Missing‑value scan (none found) • Outlier trimming via IQR • StandardScaler → saved as wine_scaled.csv (used by Power BI) • Label binning (Low 3‑4, Medium 5‑6, High 7‑8)
EDA	Correlation heat‑map, pair‑plots on scaled data
Models	Logistic Reg, SVM (RBF), KNN, Decision Tree, Random Forest, XGBoost
Tuning	Stratified K‑Fold + Grid/Random Search
Metrics	F1‑Score (macro & per‑class), Confusion Matrix, MAE/RMSE (regression baseline)

🧪 Challenges & ✅ Solutions
Challenge	Solution
Imbalanced labels skewing accuracy	Binning + Stratified K‑Fold + macro‑F1
Overfitting on tree ensembles	Limited tree depth & learning rate, early stopping (XGB)
Keeping visuals consistent after scaling	Exported the same scaled DataFrame to Power BI, ensuring dashboard KPIs match model inputs

📊 Power BI Dashboard (from wine_scaled.csv)
Card KPIs: Precision, Recall, F1 by class

Clustered bar: Alcohol (scaled) vs Predicted Quality

Stacked column: Actual vs Predicted counts

Density scatter: Volatile Acidity (scaled) vs Quality

Curved cards & custom dark canvas background for aesthetics

🚀 Results
Best model: Tuned Random Forest

Macro F1: 0.78

Overall accuracy: 0.73 after binning

Dashboard :-
https://github.com/ankeshmaurya/Wine-Quality-Prediction/blob/main/Dashboard.png
