# 🩺 Breast Cancer Classification

An end-to-end machine learning classification project that predicts whether a breast tumor is **benign or malignant** using diagnostic features derived from breast cancer cell measurements.

This project is a hands-on ML practice project focused on strengthening the complete machine learning workflow — from understanding the dataset and defining the problem to exploratory analysis, preprocessing, model comparison, evaluation, and model serialization.

---

## 📌 Project Overview

The project uses the **Breast Cancer Wisconsin (Diagnostic) dataset**, which contains numerical measurements computed from digitized images of breast mass cell nuclei.

The objective is to build a binary classification model that predicts the tumor diagnosis based on these diagnostic measurements.

### Problem Type

**Binary Classification**

* **Input:** 30 numerical diagnostic features
* **Target:** `diagnosis`
* **Classes:** Benign (`B`) and Malignant (`M`)

> **Note:** This project is intended for machine learning practice and educational purposes. It is not a medical diagnostic system.

---

## 📊 Dataset

**Dataset:** Breast Cancer Wisconsin (Diagnostic) Data Set

The dataset contains:

* **569 observations**
* **30 numerical diagnostic features**
* `diagnosis` target column
* `id` identifier column
* One empty unnamed column in the original dataset

The diagnostic features represent measurements such as:

* Radius
* Texture
* Perimeter
* Area
* Smoothness
* Compactness
* Concavity
* Concave Points
* Symmetry
* Fractal Dimension

Each characteristic is represented through different statistical measurements, including mean, standard error, and worst-case values.

---

## 🔍 Exploratory Data Analysis

The exploratory analysis examines:

* Feature distributions
* Differences between benign and malignant cases
* Feature skewness
* Feature correlations
* Target distribution

The analysis showed that several diagnostic measurements, particularly many mean and worst-case features, exhibit noticeable differences between benign and malignant cases.

The correlation analysis also showed strong relationships among groups of related measurements, such as radius, perimeter, and area.

EDA was used to understand the dataset and provide context for modelling rather than to make final feature-selection decisions.

---

## ⚙️ Machine Learning Workflow

The project follows an end-to-end classification workflow:

1. Dataset understanding
2. Data inspection and cleaning
3. Exploratory data analysis
4. Feature correlation analysis
5. Feature and target preparation
6. Train-test split
7. Feature scaling
8. Baseline evaluation
9. Model training
10. Model evaluation
11. Cross-validation
12. Final model selection
13. Model serialization
14. Saved-model verification

---

## 🤖 Models Evaluated

Three classification algorithms were evaluated:

### 1. Logistic Regression

Used as a linear classification model and performed strongly on the dataset.

### 2. Decision Tree

Used to compare a tree-based approach that does not require feature scaling.

### 3. Random Forest

Used to compare an ensemble of decision trees with the individual Decision Tree model.

---

## 📈 Model Results

The models were evaluated using test-set accuracy, confusion matrices, classification reports, and cross-validation.

| Model               | Test Accuracy | Mean CV Accuracy |
| ------------------- | ------------: | ---------------: |
| Logistic Regression |        96.49% |          97.14%* |
| Decision Tree       |        93.86% |           91.87% |
| Random Forest       |        96.49% |           95.82% |

*The Logistic Regression cross-validation uses scaling within the cross-validation workflow.

Logistic Regression was selected as the final model based on its overall evaluation and cross-validation performance.

For the final Logistic Regression pipeline:

* **Test Accuracy:** 96.49%
* **ROC-AUC:** 0.996
* **Malignant-class Recall:** 93%
* **Malignant-class F1-score:** 95%

The final test-set confusion matrix was:

```text
[[71, 1],
 [ 3, 39]]
```

---

## 🧩 Final Model Pipeline

The final model combines preprocessing and classification into a single Scikit-learn pipeline:

**StandardScaler → Logistic Regression**

This keeps preprocessing and prediction together and makes the complete workflow easier to save and reuse.

---

## 💾 Model Serialization

The trained pipeline is saved using `joblib`.

```text
models/
└── breast_cancer_logistic_regression_pipeline.joblib
```

The saved pipeline was subsequently loaded and evaluated on the test set to verify that the serialized workflow produces the same predictive performance as the original trained pipeline.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Jupyter Notebook

---

## 📁 Project Structure

```text
PROJECT_3_breast_cancer/
│
├── .gitignore
├── README.md
│
├── data/
│   └── raw/
│       └── data.csv
│
├── models/
│   └── breast_cancer_logistic_regression_pipeline.joblib
│
└── notebooks/
    └── breast_cancer_classification.ipynb
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/ikalra858-cell/breast-cancer-classification.git
cd breast-cancer-classification
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

### 3. Open the notebook

```bash
jupyter notebook
```

Then open:

```text
notebooks/breast_cancer_classification.ipynb
```

---

## 🎯 Learning Objective

This project was built as a practical ML warm-up to strengthen understanding of:

* Binary classification
* Exploratory data analysis
* Feature scaling
* Baseline modelling
* Model comparison
* Confusion matrices and classification reports
* ROC-AUC
* Cross-validation
* Scikit-learn pipelines
* Model serialization

The focus is on understanding and implementing the complete ML workflow rather than simply optimizing model performance.

---

## ⚠️ Disclaimer

This project is for **educational and machine learning practice purposes only**. The model should not be used for medical diagnosis or clinical decision-making.
