# Parkinson's Disease Predictor using Voice Data (R Project)

## 📊 Overview

This project uses machine learning techniques in **R** to predict whether an individual has **Parkinson’s disease** based on **biomedical voice measurements**. It covers data exploration, visualization, feature selection, and model building using several popular classification algorithms.

The analysis is implemented in an R Markdown file, which produces a self-contained HTML report.

---

## 📁 Dataset

The dataset used in this project includes biomedical voice measurements from patients with and without Parkinson's disease. It consists of **195 observations** and **24 features**, including:

- **Frequency measures:** e.g., `MDVP:Fo(Hz)`, `MDVP:Fhi(Hz)`
- **Jitter and shimmer measures**
- **Noise-to-Harmonic Ratio (NHR)** and **Harmonic-to-Noise Ratio (HNR)**
- **Nonlinear dynamic complexity measures** like `RPDE`, `DFA`, and `PPE`
- **Target variable:** `status` (1 = has Parkinson’s, 0 = healthy)

---

## 📦 Libraries Used

The following R libraries are used:

- `dplyr`, `tidyr`, `tibble`, `Hmisc`
- `ggplot2`, `corrplot`
- `caTools`, `caret`
- `rpart`, `randomForest`
- `e1071`, `xgboost`, `glmnet`

---

## 🧪 Process Overview

### 🔍 1. Data Preparation & Cleaning
- Missing values are removed
- `status` is converted to a factor (binary classification)
- Unnecessary columns like `name` are dropped

### 📈 2. Exploratory Data Analysis (EDA)
- Bar plots, box plots, and violin plots show distributions
- A correlation matrix is used to explore relationships with the target
- Focus is placed on features like `NHR`, `HNR`, and `RPDE` which show strong correlation with `status`

### ⚙️ 3. Feature Selection
- LASSO (L1 regularization) is used to select the most informative features

---

## 🧠 Models Implemented

The following ML models are built and compared:

| Model           | Accuracy  | Highlights |
|----------------|-----------|------------|
| **Decision Tree** | 76.32%    | Balanced performance |
| **Random Forest** | 81.58%    | Highest overall accuracy |
| **SVM (RBF Kernel)** | 81.58% | Perfect specificity, but low sensitivity |
| **XGBoost**        | 71.79%   | Underperformed in this scenario |

> 📌 **Best Model:** Random Forest achieved the highest accuracy with good generalization.

---

## 📉 Evaluation Metrics

Each model was evaluated using:
- Accuracy
- Confusion Matrix
- Sensitivity & Specificity
- Positive/Negative Predictive Values
- Balanced Accuracy

Plots were used to visually compare performance across models.

---

## 📁 Output

The following files are generated as part of the analysis:
- `decision_tree_model_parkinsons.rds`
- `rf_model_parkinsons.rds`
- `lasso_svm_model_parkinsons.rds`
- `lasso_xgb_model_parkinsons.rds`
- `model_accuracy_comparison.png` (bar chart of model performance)

---

## ✅ Conclusion

- **Random Forest** is the most reliable model for predicting Parkinson’s disease based on voice data.
- **SVM** and **Decision Tree** also show promising results but have trade-offs in sensitivity vs. specificity.
- Further improvements can be made using more data, advanced feature engineering, and model tuning.

---

## 🔧 Future Enhancements

- Apply **SMOTE** for class imbalance
- Use **SHAP** for model interpretability
- Try **deep learning** with larger datasets
- Explore **spectral features** from audio waveforms

---

## 📂 How to Run

1. Install the required packages listed at the top of the R Markdown file.
2. Ensure your dataset is saved as `parkinsons_data.csv` in the working directory.
3. Open the `.Rmd` file in RStudio.
4. Click **"Knit"** to generate the HTML report.

---

## 📌 Author

**Yashwanth Kumar Kurakula**  
Date: *27 October 2024*

---

## 📜 License

This project is for academic and research purposes. Feel free to use and modify it with proper attribution.

