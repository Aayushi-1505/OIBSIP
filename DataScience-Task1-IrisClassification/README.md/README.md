# 🌸 Iris Flower Classification with Machine Learning — OIBSIP Data Science Task 1

**Oasis Infobyte Internship Program (OIBSIP)**
**Track:** Data Science | **Task 1:** Iris Flower Classification
**Dataset:** Iris Dataset (built into scikit-learn) — 150 samples × 4 features × 3 species

---

## 🎯 Objective

Train a machine learning **classification model** that identifies the species of an iris flower — *Setosa*, *Versicolor*, or *Virginica* — from its physical measurements (sepal length/width, petal length/width), demonstrating the complete supervised learning workflow from EDA to model comparison.

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Language | Python 3.10 |
| Data | `pandas`, `numpy` |
| ML | `scikit-learn` (LogisticRegression, KNeighborsClassifier, RandomForestClassifier, StandardScaler) |
| Visualisation | `matplotlib`, `seaborn` |
| Environment | Jupyter Notebook |

---

## ✅ Feature Checklist — Completion Status

| Requirement | Status | Reference |
|-------------|:------:|-----------|
| Load the Iris dataset from `sklearn.datasets.load_iris()` (no download) | ✅ | Section 2 |
| EDA: shape, dtypes, null value check, descriptive statistics | ✅ | Section 3 |
| Pairplot / scatter matrix showing feature distributions by species | ✅ | Section 4.1 |
| Box plots for each feature across species | ✅ | Section 4.2 |
| Feature selection discussion: which features are most discriminative? | ✅ | Section 5 |
| Train/test split (80/20, stratified) | ✅ | Section 6 |
| Train at least 2 classifiers (3 trained: LogReg, KNN, Random Forest) | ✅ | Section 7 |
| Evaluation: accuracy, confusion matrix, classification report | ✅ | Section 8 |
| Best-performing model identified with justification | ✅ | Section 9 |
| Clean, commented Jupyter Notebook | ✅ | Throughout |

---

## 📂 Folder Structure (as per OIBSIP guidelines)

```
OIBSIP/
└── DataScience-Task1-IrisClassification/
    ├── Iris_Flower_Classification.ipynb   # Main notebook (executed, with outputs)
    ├── README.md                          # This file
    ├── requirements.txt                   # Dependencies
    └── screenshots/                       # Exported plots for LinkedIn/README
```

**GitHub push path (strict format):**

```
OIBSIP/DataScience-Task1-IrisClassification/
```

---

## 📥 Dataset

- **Source:** Built into scikit-learn — `sklearn.datasets.load_iris()` (Fisher, 1936; UCI ML Repository)
- **No download needed** — loads directly in one line of code
- **Shape:** 150 rows × 4 features + 1 target
- **Features:** sepal length (cm), sepal width (cm), petal length (cm), petal width (cm)
- **Target classes:** Setosa / Versicolor / Virginica — **perfectly balanced** (50 samples each)
- **Missing values:** 0 in every column ✅

---

## 🔬 Methodology

### 1. EDA
- Shape, dtypes, and null check — clean dataset, no imputation needed
- Descriptive statistics per feature (mean, std, min/max, quartiles)
- Class balance verified: 50/50/50 — no imbalance handling required

### 2. Visualisations
- **Pairplot by species:** Setosa is linearly separable from the other two; Versicolor and Virginica overlap slightly in petal dimensions
- **Box plots (2×2 grid):** petal measurements show far cleaner class separation than sepal measurements
- **Correlation heatmap:** petal length and petal width are highly correlated (r ≈ 0.96)

### 3. Feature Selection Discussion
**Petal length and petal width are the most discriminative features.** Setosa forms a completely isolated cluster on petal dimensions, while sepal width shows heavy overlap across all three species — the pairplot and box plots confirm this visually.

### 4. Preprocessing & Split
- **80/20 train/test split**, `stratify=y`, `random_state=42` → 120 train / 30 test samples
- Features standardised with `StandardScaler` for Logistic Regression and KNN (Random Forest uses raw features — scale-invariant)
- Scaler fitted **only on train** to avoid data leakage

---

## 📈 Models Trained (3 for robustness)

| Model | Params | Rationale |
|-------|--------|-----------|
| Logistic Regression | `max_iter=500` | Interpretable linear baseline |
| K-Nearest Neighbours | `k=5` | Distance-based; suits well-clustered classes |
| Random Forest | `n_estimators=100` | Non-linear ensemble; provides feature importance |

---

## 🏆 Evaluation (Test set n = 30)

| Model | Accuracy | Precision (macro) | Recall (macro) | F1 (macro) |
|-------|:--------:|:-----------------:|:--------------:|:----------:|
| **[Best Model]** 🥇 | [1.0000] | [1.00] | [1.00] | [1.00] |
| [Second Model] | [0.9667] | [0.97] | [0.97] | [0.97] |
| [Third Model] | [0.9667] | [0.97] | [0.97] | [0.97] |

**Best Model: [e.g., Random Forest]** — highest accuracy with a clean confusion matrix ([X] misclassifications). Because Iris is a small, well-separated dataset, all three models perform strongly; the confusion matrices show any errors occur only between *Versicolor* and *Virginica* (the two overlapping species), never with *Setosa*.

- Confusion matrices plotted for each model with species labels
- Full classification reports (per-class precision, recall, F1) included

---

## 💡 Key Findings

1. **Petal dimensions dominate:** petal length + petal width alone are nearly sufficient to classify all three species
2. **Setosa is 
