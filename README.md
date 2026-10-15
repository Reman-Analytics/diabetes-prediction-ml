# 🩺 Diabetes Prediction Using Random Forest Classifier

An end-to-end Machine Learning project that predicts the onset of diabetes based on clinical diagnostic measurements from the **Pima Indians Diabetes Dataset**. This project achieves a robust **88.27% accuracy** and a clinically significant **84% recall** by prioritizing medical data integrity and handling domain-specific anomalies safely.

---

## 🚀 Key Highlights & Clinical Logic

Instead of blindly applying standard preprocessing shortcuts, this workflow focuses heavily on **clinical validity**:

*   **Smart Missing Data Handling:** Critical medical indicators like `Insulin` (48.7% missing) and `SkinThickness` (29.5% missing) were masked as zeros in the raw data. Instead of dropping them or filling them with global metrics, patients were segmented by their outcome to apply a **Group-based Imputation** that preserved true healthcare patterns.
*   **Zero-Drop Strategy for Selected Features:** Features like `Glucose`, `BMI`, and `BloodPressure` had very minor missing values (<5%), which were safely dropped row-wise to ensure 100% authentic biological baselines.
*   **Preserving Real Outliers:** Extreme values (e.g., Insulin levels up to 800) were left intact to capture severely diabetic cases. A tree-based **Random Forest Classifier** was deployed because it natively handles extreme values without distorting the model's performance.

---

## 📊 Model Performance Report

The model was trained using an 80/20 train-test split, stratified to balance class distributions. 

```text
Model Accuracy: 0.8827586206896552

Classification Report:
               precision    recall  f1-score   support

           0       0.91      0.91      0.91        95
           1       0.82      0.84      0.83        50

    accuracy                           0.88       145
   macro avg       0.87      0.87      0.87       145
weighted avg       0.88      0.88      0.88       145
```

### 🧠 Why Recall Matters Here
In healthcare informatics, minimizing **False Negatives** is life-saving. A **84% Recall for Class 1 (Diabetic)** ensures that the model successfully catches a vast majority of high-risk patients, preventing critical cases from slipping away undetected.

---

## 🛠️ Project Structure & Workflow

1.  **Exploratory Data Analysis (EDA):** Individual column outlier analysis using Boxplots.
2.  **Data Cleaning:** Converting false `0` values to `NaN` and handling them based on missing percentages.
3.  **Feature Split:** Segregating the dataset into `X` (Features) and `y` (Target: Outcome).
4.  **Model Training:** Training 100 Decision Trees concurrently via `RandomForestClassifier`.
5.  **Evaluation:** Measuring success via Confusion Matrices and Scikit-Learn Metrics.

---

## 💻 Tech Stack Used

*   **Language:** Python
*   **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn
*   **Environment:** Jupyter Notebook / VS Code

---

<img width="1188" height="615" alt="bbb" src="https://github.com/user-attachments/assets/475fa1f6-9aae-40b2-9864-498c6ed04500" />






