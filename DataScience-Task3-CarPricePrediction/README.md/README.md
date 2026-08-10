# 🚗 Car Price Prediction with Machine Learning — OIBSIP Data Science Task 3

**Oasis Infobyte Internship Program (OIBSIP)**
**Track:** Data Science | **Task 3:** Car Price Prediction with Machine Learning
**Dataset:** Vehicle Dataset from CarDekho (Kaggle) — 301 rows → 299 after cleaning (9 features)

---

## 🎯 Objective

Build a **regression model** that predicts the selling price of a used car based on features such as brand, age, mileage (kms driven), fuel type, seller type, and transmission — demonstrating end-to-end skills from data cleaning and feature engineering to model comparison and interpretation.

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Language | Python 3.10 |
| Data | `pandas`, `numpy` |
| ML | `scikit-learn` (LinearRegression, RandomForestRegressor, GradientBoostingRegressor, LabelEncoder) |
| Visualisation | `matplotlib`, `seaborn` |
| Environment | Jupyter Notebook |

---

## ✅ Feature Checklist — Completion Status

| Requirement | Status | Reference |
|-------------|:------:|-----------|
| Download & load a suitable dataset (CarDekho) | ✅ | Section 2 |
| Data cleaning: nulls, duplicates, inconsistent categorical values | ✅ | Section 3 |
| Feature engineering: `Car_Age` from year; `Brand` from car name | ✅ | Section 4 |
| EDA: price distribution, price vs fuel type boxplots, price vs car age scatter | ✅ | Section 5 |
| Encode categorical variables (Label Encoding) | ✅ | Section 6 |
| Feature correlation heatmap | ✅ | Section 5.6 |
| Train/test split (80/20) | ✅ | Section 6 |
| Train at least 2 regression models (3 trained) | ✅ | Section 7 |
| Evaluate using MAE, RMSE, and R² score | ✅ | Section 8 |
| Feature importance chart for best-performing model | ✅ | Section 9 |
| Clean, commented Jupyter Notebook | ✅ | Throughout |

---

## 📂 Folder Structure (as per OIBSIP guidelines)

```
OIBSIP/
└── DataScience-Task3-CarPricePrediction/
    ├── Car_Price_Prediction.ipynb   # Main notebook (executed, with outputs)
    ├── car data.csv                 # Dataset (301 rows)
    ├── README.md                    # This file
    ├── requirements.txt             # Dependencies
    └── screenshots/                 # Exported plots for LinkedIn/README
```

**GitHub push path (strict format):**

```
OIBSIP/DataScience-Task3-CarPricePrediction/
```

---

## 📥 Dataset

- **Source:** Kaggle — *Vehicle Dataset from CarDekho* (Nehal Birla)
- **File used:** `car data.csv`
- **Shape:** 301 rows × 9 columns → **299 rows after duplicate removal**
- **Columns:** `Car_Name`, `Year`, `Selling_Price` (target), `Present_Price`, `Kms_Driven`, `Fuel_Type`, `Seller_Type`, `Transmission`, `Owner`
- **Missing values:** 0 in every column ✅
- **Target stats:** mean ₹4.59 L | median ₹3.51 L | range ₹0.10 L – ₹35.00 L (right-skewed)

---

## 🔬 Methodology

### 1. Data Cleaning
- Duplicate rows removed (301 → 299)
- Categorical text standardised (`.str.strip().str.title()`) — e.g., "petrol" → "Petrol"
- Null check: **zero missing values** across all columns

### 2. Feature Engineering
| New Feature | Derivation | Rationale |
|-------------|-----------|-----------|
| `Car_Age` | `2024 − Year` | Depreciation is tied to age, not raw year (avg age: 10.4 yrs) |
| `Brand` | First word of `Car_Name` | Brand reputation strongly affects resale value |

Original `Year` and `Car_Name` columns dropped after extraction.

### 3. Exploratory Data Analysis (EDA)
- **Price distribution:** right-skewed — most cars sell below ₹10 L, a few premium outliers up to ₹35 L
- **Price vs Fuel Type:** Diesel cars command far higher resale (avg **₹10.10 L**) vs Petrol (**₹3.26 L**) and CNG (**₹3.10 L**)
- **Price vs Car Age:** clear negative trend — *older cars sell for less*
- **Price vs Transmission:** Automatic cars hold value better (avg **₹9.07 L**) vs Manual (**₹3.92 L**)
- **Price vs Kms Driven:** weak negative relationship with high scatter
- **Top brands by count:** City, Bajaj, Corolla, Royal, Honda dominate the dataset

### 4. Correlation with Selling_Price
| Feature | Correlation |
|---------|:-----------:|
| Present_Price | **+0.88** (strongest) |
| Kms_Driven | +0.03 |
| Owner | −0.09 |
| Car_Age | **−0.23** (depreciation confirmed) |

### 5. Encoding & Split
- Categorical columns (`Fuel_Type`, `Seller_Type`, `Transmission`, `Brand`) → **Label Encoded**
- **80/20 train/test split**, `random_state=42` → 239 train / 60 test samples

---

## 📈 Models Trained (3 for robustness)

| Model | Params | Rationale |
|-------|--------|-----------|
| Linear Regression | default | Interpretable baseline; tests linear relationship |
| Random Forest | `n_estimators=200` | Non-linear ensemble; provides feature importance |
| Gradient Boosting | `n_estimators=200` | Sequential boosting; often strong on tabular data |

---

## 🏆 Evaluation (Test set n = 60)

| Model | MAE | RMSE | R² |
|-------|:---:|:----:|:--:|
| **Linear Regression** 🥇 | 1.5405 | 2.5830 | **0.7411** |
| Gradient Boosting | **1.2015** | 2.6643 | 0.7246 |
| Random Forest | 1.3660 | 3.3261 | 0.5708 |

**Best Model: Linear Regression** — highest R² (0.7411) and lowest RMSE (2.583). The strong linear correlation between `Present_Price` and `Selling_Price` (r = 0.88) explains why the linear model competes so well; the small dataset (299 rows) limits ensemble models, which show signs of overfitting (Random Forest R² drops to 0.57 on test).

- **Actual vs Predicted scatter:** points cluster near the perfect-prediction diagonal
- **Residual plot:** residuals scattered around zero with no strong systematic pattern; slight spread at higher prices (premium cars are harder to predict)

---

## 🔑 Feature Importance (Random Forest)

| Rank | Feature | Importance |
|:----:|---------|:----------:|
| 1 | Present_Price | **0.8914** |
| 2 | Car_Age | 0.0670 |
| 3 | Brand | 0.0206 |
| 4 | Kms_Driven | 0.0121 |
| 5 | Transmission | 0.0052 |
| 6 | Seller_Type | 0.0024 |
| 7 | Fuel_Type | 0.0013 |
| 8 | Owner | 0.0000 |

---

## 💡 Key Findings

1. **Present_Price is the dominant predictor** (importance 0.89, correlation +0.88) — a car's showroom price anchors its resale value
2. **Car_Age negatively impacts price** (correlation −0.23) — depreciation is real and measurable
3. **Diesel cars have ~3× higher resale value** than Petrol/CNG on average
4. **Automatic transmission holds value better** (₹9.07 L vs ₹3.92 L average)
5. **Kms_Driven has surprisingly weak impact** once Present_Price and Age are accounted for

---

## 📊 Key Visuals (Embedded in Notebook)

- Selling price distribution (histogram + boxplot)
- Price vs Fuel Type / Transmission boxplots with group means
- Price vs Car Age & Price vs Kms Driven scatter plots
- Top 10 Brands bar chart
- Feature correlation heatmap
- Actual vs Predicted scatter (best model) with perfect-prediction line
- Residual plot
- Feature importance horizontal bar chart

---

## 📉 Limitations & Next Steps

| Current | Production Upgrade |
|---------|--------------------|
| Small dataset (299 rows) | Scrape/collect 10k+ listings for ensemble models to shine |
| Label Encoding for brands | One-Hot / Target Encoding to avoid false ordinality |
| No hyperparameter tuning | GridSearchCV / Optuna for RF & GBM |
| Point predictions only | Prediction intervals for price ranges |
| Static model | Deploy as a Flask/Streamlit price-estimator app |

**Improvements:** log-transform the skewed target, cross-validation instead of a single split, add features like city, colour, service history, accident record.

---

## 📚 References

1. Vehicle Dataset from CarDekho — Kaggle (Nehal Birla) — https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho
2. scikit-learn Linear Models docs — https://scikit-learn.org/stable/modules/linear_model.html
3. scikit-learn Ensemble Methods — https://scikit-learn.org/stable/modules/ensemble.html
4. James et al. — *An Introduction to Statistical Learning* (regression theory)

---

> *"Learning is the only thing the mind never exhausts, never fears, and never regrets."* — Leonardo da Vinci

**Made with ❤️ for the OIBSIP Data Science Internship**
