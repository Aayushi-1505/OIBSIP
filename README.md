# OIBSIP

# 🚀 OIBSIP — Oasis Infobyte Data Science Internship

**Intern:** Aayushi
**Track:** 📊 Data Science
**Organization:** [Oasis Infobyte](https://www.oasisinfobyte.com)
**Repository:** All task submissions for the OIBSIP Data Science Internship Program

---

## 📋 About This Repository

This repository contains my completed projects for the **Oasis Infobyte Data Science Internship (OIBSIP)**. The track requires a minimum of **3 tasks** — all three are completed below, covering the core pillars of applied machine learning: **classification, regression, and natural language processing (NLP)**.

Each task folder contains a fully executed Jupyter Notebook, a detailed README, the dataset (or loading instructions), and screenshots of key outputs.

---

## ✅ Completed Tasks — Overview

| # | Task | Domain | Best Model | Key Result | Link |
|---|------|--------|-----------|------------|------|
| 1 | 🌸 Iris Flower Classification | Multi-class Classification | [Random Forest] | [XX.X]% Accuracy | [📁 View](./DataScience-Task1-IrisClassification) |
| 3 | 🚗 Car Price Prediction | Regression | Linear Regression | R² = 0.7411 | [📁 View](./DataScience-Task3-CarPricePrediction) |
| 4 | 📧 Email Spam Detection | NLP / Binary Classification | Logistic Regression | F1 = 0.9139, Recall = 92.6% | [📁 View](./DataScience-Task4-EmailSpamDetection) |

---

## 🌸 Task 1 — Iris Flower Classification

> Classify iris flowers into *Setosa*, *Versicolor*, or *Virginica* from sepal/petal measurements.

- **Dataset:** Built-in scikit-learn Iris dataset (150 samples, perfectly balanced)
- **Models:** Logistic Regression · KNN (k=5) · Random Forest
- **Highlights:** Pairplot & boxplot EDA revealed **petal dimensions** as the most discriminative features; Setosa is linearly separable while all misclassifications occur only between Versicolor and Virginica
- **Result:** [Best model] achieved **[XX.X]% accuracy** on the test set

---

## 🚗 Task 3 — Car Price Prediction

> Predict the resale price of used cars from brand, age, mileage, fuel type, and transmission.

- **Dataset:** CarDekho Vehicle Dataset (Kaggle) — 299 cars after cleaning
- **Feature Engineering:** `Car_Age` (2024 − Year) and `Brand` extracted from car name
- **Models:** Linear Regression · Random Forest · Gradient Boosting
- **Highlights:** `Present_Price` dominates predictions (importance **0.89**); Diesel cars resell ~3× higher than Petrol; automatic transmission holds value better
- **Result:** Linear Regression won with **R² = 0.7411** | MAE = 1.54 | RMSE = 2.58

---

## 📧 Task 4 — Email Spam Detection

> An NLP pipeline that classifies SMS/email messages as **Spam** or **Ham**.

- **Dataset:** UCI SMS Spam Collection — 5,574 messages (86.6% ham / 13.4% spam)
- **Pipeline:** lowercase → punctuation removal → stopwords → Porter stemming → **TF-IDF** (5k features, bigrams)
- **Models:** Multinomial Naive Bayes · Logistic Regression · Linear SVM
- **Highlights:** Class imbalance handled via stratification + `class_weight='balanced'`; recall prioritised since missed spam (phishing) costs more than a false alarm; WordClouds & misclassification error analysis included
- **Result:** Logistic Regression won with **97.67% accuracy | F1 = 0.9139 | Recall = 92.6%**

---

## 🛠️ Tech Stack (Common Across All Tasks)

| Layer | Tools |
|-------|-------|
| Language | Python 3.10 |
| Data Handling | `pandas`, `numpy` |
| Machine Learning | `scikit-learn` |
| NLP (Task 4) | `nltk`, `re`, TF-IDF |
| Visualisation | `matplotlib`, `seaborn`, `wordcloud` |
| Environment | Jupyter Notebook |

---

## 📂 Repository Structure

```
OIBSIP/
├── README.md                                  # This file
├── DataScience-Task1-IrisClassification/
│   ├── Iris_Flower_Classification.ipynb
│   ├── README.md
│   └── screenshots/
├── DataScience-Task3-CarPricePrediction/
│   ├── Car_Price_Prediction.ipynb
│   ├── car data.csv
│   ├── README.md
│   └── screenshots/
└── DataScience-Task4-EmailSpamDetection/
    ├── Email_Spam_Detection.ipynb
    ├── spam.csv
    ├── README.md
    ├── requirements.txt
    └── screenshots/
```

---

## 🎓 Skills Demonstrated

- **Data Cleaning** — duplicates, inconsistent categories, type correction
- **Feature Engineering** — derived features (Car_Age, Brand), text preprocessing
- **EDA & Visualisation** — pairplots, boxplots, heatmaps, WordClouds
- **Supervised Learning** — classification (binary & multi-class) and regression
- **NLP** — tokenisation, stemming, stopword removal, TF-IDF vectorisation
- **Model Evaluation** — accuracy, precision, recall, F1, MAE, RMSE, R², confusion matrices, residual analysis
- **Model Comparison & Interpretation** — feature importance, coefficient analysis, error analysis

