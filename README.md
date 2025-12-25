# Machine Learning Framework for the Rapid Detection of Dengue Fever via CBC Parameters

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Research_Complete-success?style=for-the-badge)
![Accuracy](https://img.shields.io/badge/Accuracy-93.44%25-brightgreen?style=for-the-badge)

## 📌 Abstract
[cite_start]Dengue fever presents a growing threat to global public health, particularly in tropical regions where outbreaks are frequent[cite: 5]. [cite_start]While standard diagnostic methods such as ELISA and PCR are highly accurate, their cost and processing time often limit their utility in resource-constrained environments[cite: 6]. 

[cite_start]This project implements an automated diagnostic framework that utilizes **Complete Blood Count (CBC)** data to screen for dengue fever[cite: 7]. [cite_start]By training machine learning classifiers on hematological patterns (such as Thrombocytopenia and Leukopenia), this study provides a rapid, low-cost decision-support tool for clinicians[cite: 25].

## 🧬 Key Biological Markers
The model analyzes standard CBC parameters to detect pathophysiological changes induced by dengue:
* [cite_start]**Platelets:** Significant decline (Thrombocytopenia) is a primary indicator[cite: 21].
* [cite_start]**WBC (White Blood Cells):** Leukopenia is often observed in positive cases[cite: 21].
* [cite_start]**Haemoglobin & Hematocrit:** Monitored for signs of plasma leakage[cite: 37].
* [cite_start]**Other Parameters:** Neutrophil, Lymphocyte, Monocyte, Eosinophil, Basophil, RBC, Age, and Gender[cite: 37, 40].

## 🛠 Methodology
The project follows a structured data science pipeline:

### 1. Data Preprocessing & Imputation
* [cite_start]**Data Source:** Clinical data aggregating CBC records from patients suspected of dengue infection[cite: 29].
* [cite_start]**Cleaning:** Removal of non-predictive identifiers (Serial ID, Date)[cite: 36].
* [cite_start]**Imputation:** Missing biological values were handled using **K-Nearest Neighbors (KNN, k=5)** to preserve multidimensional feature patterns rather than simple mean imputation[cite: 35].
* **Encoding:** Categorical variables (Gender) were label-encoded; [cite_start]Target variable mapped to Binary (0: Negative, 1: Positive)[cite: 37].

### 2. Feature Scaling
* [cite_start]**Standardization:** Applied `StandardScaler` to normalize features with vastly different ranges (e.g., RBC in millions vs. Eosinophils in single digits), ensuring model stability[cite: 41].

### 3. Machine Learning Classifiers
[cite_start]Four distinct algorithms were trained and evaluated [cite: 43-47]:
1.  **Logistic Regression (LR):** Baseline linear classifier.
2.  **Support Vector Machine (SVM):** Utilized Radial Basis Function (RBF) kernel for non-linear decision boundaries.
3.  **Random Forest (RF):** Ensemble of 100 decision trees to reduce overfitting.
4.  **Neural Network (MLP):** Feed-forward Multi-Layer Perceptron to capture latent patterns.

## 📊 Performance Results
[cite_start]The models were evaluated on an 80/20 train-test split[cite: 56]. [cite_start]**Logistic Regression** and **Random Forest** achieved the highest accuracy, effectively minimizing False Negatives—a critical metric for epidemic screening[cite: 58].

| Model | Accuracy | Precision (Weighted) | Recall (Weighted) | AUC Score |
| :--- | :--- | :--- | :--- | :--- |
| **Logistic Regression** | **93.44%** | **0.94** | **0.93** | **0.98** |
| **Random Forest** | **93.44%** | **0.94** | **0.93** | **0.98** |
| Neural Network (MLP) | 91.80% | 0.93 | 0.92 | 0.79 |
| SVM (RBF) | 90.16% | 0.91 | 0.90 | 0.83 |

> [cite_start]*Source: Table 1 - Performance Metrics of Classifiers[cite: 68].*

## 📉 Visual Analysis
The notebook includes detailed visualizations to interpret the model's logic:
* [cite_start]**Confusion Matrices:** Detailed breakdown of True Positives vs. False Negatives[cite: 61].
* [cite_start]**ROC Curves:** Visualizing the trade-off between sensitivity and specificity[cite: 101].
* [cite_start]**Correlation Heatmap:** Highlights strong negative correlations between the target variable and Platelet/WBC counts[cite: 79].
* [cite_start]**Boxplots:** Validates biological logic by showing compressed platelet distributions in positive cases[cite: 84].

## 💻 Installation & Usage

### Prerequisites
The project requires Python and the following machine learning libraries. You can install dependencies using:

    pip install pandas numpy scikit-learn matplotlib seaborn

## 💻 Installation & Usage

### Running the Analysis
1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/your-username/Dengue-Detection-ML-CBC.git](https://github.com/your-username/Dengue-Detection-ML-CBC.git)
    cd Dengue-Detection-ML-CBC
    ```

2.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook Dengue_Detection_Analysis.ipynb
    ```

3.  **Execute the Kernel**:
    Run all cells in the notebook to reproduce the preprocessing steps, model training, and generate the evaluation metrics.

## 👥 Authors
This research was conducted by the **Department of Computer Science and Engineering** at **American International University-Bangladesh (AIUB)**.

* **Md. Fardin Tayeebi Sami** 
* **Hozayfah R. Karim**
* **S.M. Rokibul Hasan** 
* **Tawhid Hasan**

**Supervisor:**
* **Dr. Md. Asraf Ali**

## 📄 License
This project is open-source and licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more details.
