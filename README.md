# 🏥 Liver Disease Prediction for Gaza — A Knowledge Discovery Approach

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Course-Knowledge_Discovery-1F4E79?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/UCAS-Gaza-green?style=for-the-badge"/>
</p>

<p align="center">
  <b>Knowledge Discovery Course Project — 2026</b><br/>
  University College of Applied Sciences (UCAS), Gaza, Palestine<br/>
  Student: Rand Majed Salem — ID: 220210128
</p>

---

## 🧠 Overview

This project applies **Knowledge Discovery and Machine Learning** techniques to predict liver disease — with Gaza, Palestine as the intended real-world context.

Liver disease has become a critical public health concern in Gaza, where the ongoing humanitarian crisis has severely impacted healthcare infrastructure, water quality, and access to early diagnostic services. The goal of this project is to build a **binary classification model** that can assist in **early detection of liver disease** from routine medical tests — a tool that could be especially valuable in resource-limited settings.

> ⚠️ **Data Availability Note:** No structured liver disease dataset exists for Gaza due to the ongoing conflict and collapse of health data infrastructure. As a proxy, the **Indian Liver Patient Dataset (ILPD)** was used — a publicly available real-world dataset with clinically relevant features comparable to what would be collected in Gaza's medical facilities.

---

## 🎯 Motivation & Problem Statement

In Gaza:
- Healthcare systems are severely strained, limiting access to specialist diagnosis
- Liver conditions linked to contaminated water and malnutrition are rising
- Early-stage liver disease is frequently missed without predictive screening tools

**Our approach:** Train a binary classification model on available real-world medical data that could, in principle, be retrained on local Gaza data once it becomes accessible.

- **Input:** Patient medical features (age, gender, blood test results)
- **Output:** `1` = Liver Disease | `0` = No Liver Disease

---

## 🗄️ Dataset

**Indian Liver Patient Dataset (ILPD)**
*Used as a clinical proxy due to the unavailability of Gaza-specific data*

| Property | Value |
|---|---|
| Source | Real patient data — publicly available |
| Instances | 583 patients (after cleaning) |
| Features | 10 medical + demographic features |
| Target | `Dataset`: 1 (disease) / 0 (no disease) |
| Class balance | Imbalanced (~71% positive) |

### Features

| Feature | Type | Notes |
|---|---|---|
| Age | Continuous | Patient age |
| Gender | Categorical | Encoded: Male=0, Female=1 |
| Total_Bilirubin | Continuous | Liver function marker |
| Direct_Bilirubin | Continuous | Liver function marker |
| Alkaline_Phosphotase | Continuous | Enzyme level |
| Alamine_Aminotransferase | Continuous | Liver enzyme |
| Aspartate_Aminotransferase | Continuous | Outliers > 3000 removed |
| Total_Protiens | Continuous | Protein level |
| Albumin | Continuous | Protein produced by liver |
| Albumin_and_Globulin_Ratio | Continuous | Missing values → median imputed |

---

## ✨ Methodology

### 1. Data Preprocessing
- ✅ Missing value imputation (median for `Albumin_and_Globulin_Ratio`)
- ✅ Outlier removal (`Aspartate_Aminotransferase > 3000`)
- ✅ Duplicate record removal
- ✅ Gender encoding (categorical → numerical)
- ✅ Feature scaling with `StandardScaler`

### 2. Exploratory Data Analysis (EDA)
- Age & gender distribution
- Target class balance (countplot + pie chart)
- Correlation heatmap
- Outlier detection via boxplots
- Average feature values by class

### 3. Models Compared

| Model | Configuration |
|---|---|
| Logistic Regression | Default scikit-learn |
| Random Forest | 100 estimators, random_state=42 |
| SVM | probability=True, random_state=42 |

```
Train/Test Split : 80% / 20% (stratified, random_state=42)
Scaling          : StandardScaler (fit on train only)
Evaluation       : Accuracy, Precision, Recall, F1, Confusion Matrix
```

---

## 📊 Results

> *Run the notebook on Google Colab to reproduce. Update values below after running.*

| Model | Accuracy |
|---|---|
| Logistic Regression | [73.68]% |
| Random Forest | [68.42%]% |
| SVM | [71.05%]% |

---

## 🔭 Future Work

If Gaza-specific liver disease data becomes accessible, this pipeline can be directly retrained with:
- Local patient records from Gaza hospitals
- Features adapted to locally prevalent conditions (Hepatitis B/C, malnutrition markers)
- Additional fairness and bias analysis for local population demographics

---

## 📁 Repository Structure

```
├── liver-disease-prediction-gaza.ipynb                    
├── hepatic disease.csv      
└── README_LiverDisease.md                         # 
```

---

## 🚀 How to Run

```bash
# Install dependencies
pip install pandas numpy seaborn matplotlib scikit-learn gdown

# Run notebook (dataset downloads automatically)
jupyter notebook Project.ipynb
```

---

## 🛠️ Tech Stack

`Python` · `pandas` · `NumPy` · `scikit-learn` · `Seaborn` · `Matplotlib` · `gdown`

---

## 👤 Author

**Rand Majed Salem** | [GitHub](https://github.com/Randsalem19) · [LinkedIn](https://linkedin.com/in/rand-majed-salem) · [Kaggle](https://kaggle.com/randsalem)

<p align="center">Made at UCAS, Gaza, Palestine 🇵🇸</p>
