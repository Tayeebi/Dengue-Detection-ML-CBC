Markdown

# Machine Learning Framework for the Rapid Detection of Dengue Fever via CBC Parameters

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Research_Complete-success?style=for-the-badge)
![Accuracy](https://img.shields.io/badge/Accuracy-93.44%25-brightgreen?style=for-the-badge)

## 📌 Abstract
Dengue fever presents a growing threat to global public health, particularly in tropical regions where outbreaks are frequent. While standard diagnostic methods such as ELISA and PCR are highly accurate, their cost and processing time often limit their utility in resource-constrained environments. 

This project implements an automated diagnostic framework that utilizes **Complete Blood Count (CBC)** data to screen for dengue fever. By training machine learning classifiers on hematological patterns (such as Thrombocytopenia and Leukopenia), this study provides a rapid, low-cost decision-support tool for clinicians.

## 🧬 Key Biological Markers
The model analyzes standard CBC parameters to detect pathophysiological changes induced by dengue:
* **Platelets:** Significant decline (Thrombocytopenia) is a primary indicator.
* **WBC (White Blood Cells):** Leukopenia is often observed in positive cases.
* **Haemoglobin & Hematocrit:** Monitored for signs of plasma leakage.
* **Other Parameters:** Neutrophil, Lymphocyte, Monocyte, Eosinophil, Basophil, RBC, Age, and Gender.

## 🛠 Methodology
The project follows a structured data science pipeline:

### 1. Data Preprocessing & Imputation
* **Data Source:** Clinical data aggregating CBC records from patients suspected of dengue infection.
* **Cleaning:** Removal of non-predictive identifiers (Serial ID, Date).
* **Imputation:** Missing biological values were handled using **K-Nearest Neighbors (KNN, k=5)** to preserve multidimensional feature patterns rather than simple mean imputation.
* **Encoding:** Categorical variables (Gender) were label-encoded; Target variable mapped to Binary (0: Negative, 1: Positive).

### 2. Feature Scaling
* **Standardization:** Applied `StandardScaler` to normalize features with vastly different ranges (e.g., RBC in millions vs. Eosinophils in single digits), ensuring model stability.

### 3. Machine Learning Classifiers
Four distinct algorithms were trained and evaluated:
1.  **Logistic Regression (LR):** Baseline linear classifier.
2.  **Support Vector Machine (SVM):** Utilized Radial Basis Function (RBF) kernel for non-linear decision boundaries.
3.  **Random Forest (RF):** Ensemble of 100 decision trees to reduce overfitting.
4.  **Neural Network (MLP):** Multi-Layer Perceptron to capture latent patterns.

## 📊 Performance Results
The models were evaluated on an 80/20 train-test split. **Logistic Regression** and **Random Forest** achieved the highest accuracy, effectively minimizing False Negatives—a critical metric for epidemic screening.

| Model | Accuracy | Precision (Weighted) | Recall (Weighted) | AUC Score |
| :--- | :--- | :--- | :--- | :--- |
| **Logistic Regression** | **93.44%** | **0.94** | **0.93** | **0.98** |
| **Random Forest** | **93.44%** | **0.94** | **0.93** | **0.98** |
| Neural Network (MLP) | 91.80% | 0.93 | 0.92 | 0.79 |
| SVM (RBF) | 90.16% | 0.91 | 0.90 | 0.83 |

> *Note: High AUC scores in Random Forest and Logistic Regression confirm their reliability as robust screening tools.*

## 📉 Visual Analysis included in Notebook
* **Confusion Matrices:** Detailed breakdown of True Positives vs. False Negatives.
* **ROC Curves:** Visualizing the trade-off between sensitivity and specificity.
* **Correlation Heatmap:** Highlights strong negative correlations between the target variable and Platelet/WBC counts.
* **Boxplots:** Validates biological logic by showing compressed platelet distributions in positive cases.

## 💻 Installation & Usage

### Prerequisites
Ensure you have Python installed. You can install the required dependencies using pip:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
Running the Analysis
Clone this repository to your local machine.

Navigate to the project directory.

Launch Jupyter Notebook:

Bash

jupyter notebook Dengue_Detection_Analysis.ipynb
Run all cells to reproduce the preprocessing steps, model training, and visualizations.

👥 Authors & Acknowledgments
Md. Fardin Tayeebi Sami - Department of Computer Science and Engineering, AIUB

Hozayfah R. Karim - Department of Computer Science and Engineering, AIUB

S. M. Rokibul Hasan - Department of Computer Science and Engineering, AIUB

Tawhid Hasan - Department of Computer Science and Engineering, AIUB

Supervisor:

Dr. Md. Asraf Ali

Institution:

American International University-Bangladesh (AIUB)

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.


***

### 🔍 **Source Validation (For your reference):**
* [cite_start]**Title & Authors:** Derived directly from the uploaded PDF header[cite: 1, 2].
* [cite_start]**Methodology:** KNN Imputation ($k=5$) [cite: 35][cite_start], Standard Scaling [cite: 41][cite_start], and the four specific models (LR, SVM, RF, MLP) [cite: 8, 43-47] are explicitly cited from the paper's methodology section.
* [cite_start]**Results:** The accuracy table matches Table 1 in the PDF (93.44% for LR/RF)[cite: 58, 68].
* [cite_start]**Biological Markers:** The description of Platelets and WBC correlations is based on Section I and Section III-B of the text[cite: 21, 79].
