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
4.  **Neural Network (MLP):** Feed-forward Multi-Layer Perceptron to capture latent patterns.

## 📊 Performance Results
The models were evaluated on an 80/20 train-test split. **Logistic Regression** and **Random Forest** achieved the highest accuracy, effectively minimizing False Negatives—a critical metric for epidemic screening.

| Model | Accuracy | Precision (Weighted) | Recall (Weighted) | AUC Score |
| :--- | :--- | :--- | :--- | :--- |
| **Logistic Regression** | **93.44%** | **0.94** | **0.93** | **0.98** |
| **Random Forest** | **93.44%** | **0.94** | **0.93** | **0.98** |
| Neural Network (MLP) | 91.80% | 0.93 | 0.92 | 0.79 |
| SVM (RBF) | 90.16% | 0.91 | 0.90 | 0.83 |

## 📉 Visual Analysis
The notebook includes detailed visualizations to interpret the model's logic:
* **Confusion Matrices:** Detailed breakdown of True Positives vs. False Negatives.
* **ROC Curves:** Visualizing the trade-off between sensitivity and specificity.
* **Correlation Heatmap:** Highlights strong negative correlations between the target variable and Platelet/WBC counts.
* **Boxplots:** Validates biological logic by showing compressed platelet distributions in positive cases.

## 💻 Installation & Usage

### Prerequisites
The project requires Python and the following machine learning libraries. You can install dependencies using:

    pip install -r requirements.txt

### Running the Analysis
1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/YOUR-USERNAME/Dengue-Detection-ML-CBC.git](https://github.com/YOUR-USERNAME/Dengue-Detection-ML-CBC.git)
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

* *Badhan Ghosh*
* *Md. Fardin Tayeebi Sami*
* *Hozayfah R. Karim*
* *S.M. Rokibul Hasan*
* *Tawhid Hasan*

**Supervisor:**
* *Dr. Md. Asraf Ali*

## 📄 License
This project is open-source and licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more details.