# Upload Task 3 to GitHub — Step by Step

---

## Step 1 — Download Your Notebook

1. In your Kaggle notebook, click **File** (top left menu)
2. Click **"Download Notebook"**
3. It will save as `task-3.ipynb` on your computer

---

## Step 2 — Go to Your GitHub Repo

1. Open your browser
2. Go to: `https://github.com/YOUR_USERNAME/OIBSIP`

---

## Step 3 — Create Task 3 Folder + README

1. Click **"Add file"** → **"Create new file"**
2. In the filename box type:

```
DataScience-Task3-CarPricePrediction/README.md
```

3. Paste this content:

```markdown
# 🚗 Car Price Prediction

**Intern:** [Your Full Name]
**Track:** Data Science
**Organization:** Oasis Infobyte (OIBSIP)

## Objective
Predict the selling price of used cars based on features like 
brand, age, mileage, fuel type, and transmission.

## Dataset
- Source: Kaggle (Vehicle dataset from CarDekho)
- Samples: 299
- Features: 9

## Tech Stack
- Python 3
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- Kaggle Notebook

## Approach
1. Loaded and cleaned dataset
2. Feature engineering (Car Age, Brand extraction)
3. EDA with multiple visualizations
4. Encoded categorical variables
5. Trained 3 regression models
6. Evaluated using MAE, RMSE, R²
7. Analysed feature importance

## Results
| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Linear Regression | — | — | — |
| Random Forest | — | — | — |
| Gradient Boosting | — | — | — |

> Update values from your notebook output

## Key Findings
- Present Price is the strongest predictor of selling price
- Car Age negatively impacts price
- Diesel cars have higher resale value
- Automatic transmission cars hold value better

## How to Run
Open the notebook in Kaggle or Jupyter and run all cells in order.
```

4. Click **"Commit changes"**

---

## Step 4 — Upload Your Notebook

1. Click on the **`DataScience-Task3-CarPricePrediction`** folder
2. Click **"Add file"** → **"Upload files"**
3. Drag and drop your downloaded `task-3.ipynb` file
4. Click **"Commit changes"**

---

## Step 5 — Upload Screenshots

1. Go back to the **`DataScience-Task3-CarPricePrediction`** folder
2. Click **"Add file"** → **"Create new file"**
3. Type: `screenshots/.gitkeep`
4. Click **"Commit changes"**
5. Open the **`screenshots`** folder
6. Click **"Add file"** → **"Upload files"**
7. Upload screenshots of your key plots:
   - Price distribution
   - Correlation heatmap
   - Model comparison
   - Feature importance
   - Actual vs Predicted
8. Click **"Commit changes"**

---

## Your Repo Should Now Look Like This

```
OIBSIP/
│
├── README.md
│
├── DataScience-Task1-IrisClassification/     ✅ Done
│   ├── README.md
│   ├── Iris_Classification.ipynb
│   └── screenshots/
│
├── DataScience-Task3-CarPricePrediction/     ✅ Just uploaded
│   ├── README.md
│   ├── task-3.ipynb
│   └── screenshots/
│
└── DataScience-Task4-EmailSpamDetection/     ⬜ Next
    ├── README.md
    ├── Email_Spam_Detection.ipynb
    └── screenshots/
```

---

## Progress

| Task | Code | GitHub |
|------|------|--------|
| ✅ Task 1 — Iris | Done | Uploaded |
| ✅ Task 3 — Car Price | Done | **Upload now** |
| ⬜ Task 4 — Spam Detection | **Next** | After code is done |

---

## After Uploading Task 3

Type **"next"** and I'll give you the **complete Task 4 (Email Spam Detection)** code — all cells from start to finish, just like Task 3! 🚀