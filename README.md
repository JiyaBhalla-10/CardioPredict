# CardioPredict: Cardiovascular Disease Prediction using Machine Learning

## 📌 Overview
CardioPredict is a machine learning-based system for predicting the presence of cardiovascular disease (heart disease) using clinical and demographic patient data. The project compares seven different classification models and selects **XGBoost** as the best-performing algorithm, achieving **99.5% accuracy** and **99.94% AUC-ROC**. The model is made interpretable using **SHAP** (Explainable AI) to identify key risk factors.

## 📊 Dataset
- **Source**: https://data.mendeley.com/datasets/dzz48mvjht/1 
- **Number of records**: 1000 patients  
- **Number of attributes**: 14 (including target variable)  
- **Key features**:
  - Age, Gender, Chest pain type (4 types)
  - Resting blood pressure, Serum cholesterol (mg/dl)
  - Fasting blood sugar (>120 mg/dl)
  - Resting ECG results, Maximum heart rate achieved
  - Exercise-induced angina, ST depression (old peak)
  - Slope of peak exercise ST segment, Number of major vessels
  - Target: Presence or absence of heart disease

## 🧹 Data Preprocessing
- Removed patient ID (non-informative)
- Handled missing and duplicate records
- Median imputation for zero cholesterol values (biologically impossible)
- Encoded categorical features (chest pain type, resting ECG)
- Feature scaling using StandardScaler
- Train-test split: 80% – 20%

## 🤖 Models Implemented
| Model | Accuracy | Recall | AUC-ROC |
|-------|----------|--------|---------|
| **XGBoost** | **99.5%** | **100%** | **99.94%** |
| ANN | 99.5% | 100% | 99.92% |
| Random Forest | 98.5% | 99.14% | 99.89% |
| Logistic Regression | 98.0% | 98.28% | 99.84% |
| SVM | 97.5% | 99.14% | 99.90% |
| Decision Tree | 97.0% | 96.55% | 97.09% |
| KNN | 97.0% | 96.55% | 98.53% |

✅ **XGBoost was chosen as the final model** because it handles tabular data well, is computationally efficient, and generalizes better than ANN for this dataset.

## 📈 Key Results
- **Accuracy**: 99.5%
- **Precision**: 99.15%
- **Recall**: 100% (no false negatives)
- **F1 Score**: 99.57%
- **ROC-AUC**: 99.94%
- Only **one false positive** in test predictions
- Confusion matrix confirms near-perfect classification

## 🔍 Explainability (SHAP)
SHAP (SHapley Additive exPlanations) was used to interpret the XGBoost model. The most influential features were:
1. Slope of ST segment
2. Resting blood pressure
3. Chest pain type
4. Serum cholesterol level

This makes the model transparent and suitable for clinical decision support.

## 🚀 How to Run the Project

### Option 1: Google Colab (Recommended)
1. Open `Copy_of_heart_disease_project.ipynb` in Google Colab.
2. Upload the dataset `Cardiovascular_Disease_Dataset.csv` when prompted (or mount Google Drive).
3. Run all cells sequentially.

### Option 2: Local Jupyter Notebook
1. Clone this repository:
   ```bash
   git clone https://github.com/JiyaBhalla-10/CardioPredict.git
   cd CardioPredict
