# Machine Learning Framework for Rapid Detection of Dengue Fever

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Accuracy](https://img.shields.io/badge/Accuracy-93.44%25-brightgreen)

## 📌 Abstract
Dengue fever presents a growing threat to global public health, particularly in tropical regions. While standard diagnostic methods (ELISA, PCR) are accurate, they are often costly and time-consuming. [cite_start]This study investigates the potential of Machine Learning (ML) to serve as a rapid, low-cost screening alternative using data from routine Complete Blood Count (CBC) tests[cite: 5, 6, 7].

## 🚀 Key Features
* [cite_start]**Data Imputation:** Utilizes KNN Imputation (k=5) to handle missing medical data values effectively[cite: 35].
* [cite_start]**Feature Scaling:** Standard Scaling applied to normalize parameters like RBC (millions) and Eosinophils (single digits)[cite: 40, 41].
* [cite_start]**Multi-Model Evaluation:** Comparative analysis of Logistic Regression, SVM, Random Forest, and MLP[cite: 8].
* [cite_start]**High Performance:** Achieved a peak accuracy of **93.44%** with Logistic Regression and Random Forest[cite: 9].

## 📂 Dataset
The dataset aggregates CBC records from patients suspected of dengue infection. It includes standard parameters such as:
* [cite_start]Haemoglobin, ESR, WBC, Neutrophil, Lymphocyte, Monocyte, Eosinophil, Basophil, RBC, and Platelets[cite: 40].
* **Target Label:** Positive / Negative (Binary Classification).

## 🛠 Methodology
1.  **Preprocessing:** Data cleaning and label encoding for categorical variables (Gender).
2.  [cite_start]**Imputation:** Missing values filled using K-Nearest Neighbors to preserve biological patterns[cite: 35].
3.  **Model Selection:**
    * *Logistic Regression (LR)*: Baseline linear classifier.
    * [cite_start]*Support Vector Machine (SVM)*: RBF kernel for non-linear boundaries[cite: 45].
    * [cite_start]*Random Forest (RF)*: Ensemble of 100 decision trees[cite: 46].
    * [cite_start]*Neural Network (MLP)*: Feed-forward Multi-Layer Perceptron[cite: 47].

## 📊 Results
The models were evaluated on an 80/20 train-test split.

| Model | Accuracy | Precision (W. Avg) | Recall (W. Avg) |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | **93.44%** | **0.94** | **0.93** |
| Random Forest | 93.44% | 0.94 | 0.93 |
| Neural Network (MLP) | 91.80% | 0.93 | 0.92 |
| SVM (RBF) | 90.16% | 0.91 | 0.90 |

[cite_start]*Table Data Source: [cite: 68]*

## 📉 Visualizations
The project includes detailed analysis using:
* [cite_start]**Confusion Matrices:** To analyze False Negatives vs False Positives[cite: 60].
* [cite_start]**ROC Curves:** Demonstrating high AUC (0.98) for Random Forest and Logistic Regression[cite: 102].
* [cite_start]**Correlation Matrix:** Identifying Platelets and WBC as key negative correlations[cite: 79].

## 💻 Installation & Usage
1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Dengue-Detection-ML-CBC.git](https://github.com/YOUR_USERNAME/Dengue-Detection-ML-CBC.git)
