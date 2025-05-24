# 💎 Diamond Price Prediction using Multiple Linear Regression

This project predicts the price of diamonds based on their physical and quality characteristics using an end-to-end **machine learning regression pipeline**. It includes data preprocessing, feature engineering, multicollinearity handling, and thorough model evaluation — making it a clean and interpretable example of a real-world regression problem.

---

## 📦 Dataset

- **Source**: [Kaggle - Diamonds Dataset](https://www.kaggle.com/datasets/shivam2503/diamonds)
- **Target Variable**: `price` (in USD)
- **Features**:
  - **Carat** (weight)
  - **Cut**, **Color**, **Clarity** (quality-based categorical variables)
  - **Depth**, **Table** (percent measurements)
  - **x**, **y**, **z** (dimensions in mm)

---

## 🧠 ML Pipeline Overview

### 🧹 Data Preprocessing
- Dropped redundant columns like `Unnamed: 0`
- Converted categorical features (`cut`, `color`, `clarity`) into **ordinal encodings** based on domain hierarchy
- No missing values were found — data was clean

### 📊 Exploratory Data Analysis (EDA)
- Used **boxplots** to analyze how `price` varies with `cut`, `color`, and `clarity`
- Created **scatter plots** to explore relationships between numeric features and price
- Plotted a **probability density curve** of price to examine its distribution

---

## 🌡️ Multicollinearity Handling

- A **correlation heatmap** revealed very high correlation (r > 0.95) between `carat`, `x`, `y`, and `z`
- To avoid multicollinearity and coefficient instability:
  - **Dropped `x`, `y`, and `z`**
  - Retained only `carat` as the representative size feature
- Verified feature independence with **Variance Inflation Factor (VIF)** — retained only features with **VIF < 10**

---

## 📐 Modeling & Evaluation

### 🔁 Linear Regression (Scikit-learn)
- Trained a model on the cleaned and filtered dataset
- Used **R²**, **RMSE**, and **MAE** to assess performance

| Dataset | R² Score | RMSE (USD) | MAE (USD) |
|---------|----------|------------|-----------|
| Train   | 0.902    | 1251.96    | 865.61    |
| Test    | 0.902    | 1235.86    | 859.14    |

✔️ **Consistent train/test performance**  
✔️ **High R²** and low error indicate a **strong and generalizable model**

---

## 📉 Residual Analysis

- Histograms of residuals showed errors were **normally distributed around zero**
- Scatter plots of errors vs actual price revealed **no major bias**, though slightly higher variance at high price range — typical of real-world data

---

## 🧾 Key Insights

- **`carat` is the strongest predictor** of price — retains nearly all the signal from dimensions
- Dropping multicollinear features improved **model stability** without reducing accuracy
- The model is **simple, interpretable, and effective**

---

---

## 🚀 How to Run

1. Clone this repository  
   `git clone https://github.com/<your-username>/diamond-price-prediction.git`
2. Launch the notebook  
   `jupyter notebook DiamondPricePrediction.ipynb`
3. Run all cells to reproduce the workflow and results

---

## 📚 Tools Used

- Python 3
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn
- statsmodels (VIF)

---






