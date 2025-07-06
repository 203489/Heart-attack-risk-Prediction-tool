# 🫀 Heart Attack Risk Prediction with Ensemble Machine Learning

This project analyzes cleaned medical data to **predict the probability of a heart attack** in patients using an ensemble of machine learning models. It calculates individual risk scores, classifies risk levels, evaluates model performance, and exports the results into an Excel file. Visualizations are also generated for insights and explainability.

> ✅ Final predictions include: `Risk Score (%)`, `Risk Category (Low, Moderate, High)`, and a unique `Patient ID`.

---

## 📁 Project Structure

```
heart-attack-predictor/
├── heart_attack_data_cleaned.xlsx        # Input data (Excel format)
├── heart_attack_probabilistic_results.xlsx  # Output file with predictions
├── roc_curves.png                        # ROC plot for model comparison
├── feature_importance_rf.png             # Random Forest feature importances
├── app.py                                # Main Python script
├── requirements.txt                      # Python dependencies
└── README.md                             # Project documentation
```

---

## 💡 Features

- Reads and processes structured medical records.
- Encodes categorical data and scales numeric features.
- Trains three models:  
  - **Logistic Regression**  
  - **Random Forest**  
  - **Gradient Boosting**
- Combines model probabilities using ensemble averaging.
- Applies sigmoid sharpening (`expit(logit(p)*1.5)`) for contrast.
- Classifies risk into **Low**, **Moderate**, or **High**.
- Visualizes:
  - Risk category distribution
  - ROC curves
  - Model comparison (Accuracy, Precision, Recall)
  - Random Forest feature importance
  - Top 10 patients' risk scores

---

## 📊 Input Columns (examples)

- `Age`, `Gender`, `Cholesterol`, `Resting ECG`, `Max Heart Rate`, etc.
- Target column: `Heart_Attack_Risk` (0 or 1)

---

## 🧪 How It Works

1. **Preprocessing**  
   - Encodes categorical features using Label Encoding  
   - Scales features with MinMaxScaler  

2. **Training**  
   - Fits all three models using 80/20 split  
   - Predicts probabilities on the full dataset  

3. **Ensembling & Adjustment**  
   - Averages the model outputs  
   - Sharpens predictions using sigmoid + logit  
   - Assigns risk labels with:
     ```
     if p < 0.31 → Low  
     0.31 ≤ p ≤ 0.65 → Moderate  
     p > 0.65 → High
     ```

4. **Outputs**  
   - Saves an Excel file with:
     - Patient ID
     - Risk Score (%)
     - Risk Category
     - All original data

---

## 📉 Evaluation

Performance metrics displayed and visualized for all models:

- Accuracy
- Precision
- Recall
- ROC Curves
- Feature Importance (Random Forest)

Example ROC Curve output:  
![ROC Curve](./roc_curves.png)

---

## 📦 Installation & Usage

### Step 1: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 2: Add your data file

Place your Excel file named `heart_attack_data_cleaned.xlsx` in the root folder.

### Step 3: Run the Script

```bash
python app.py
```

---

## ✅ Output

- 📊 **File:** `heart_attack_probabilistic_results.xlsx`
- 📈 **Charts:**
  - `roc_curves.png`
  - `feature_importance_rf.png`

Sample fields in the final Excel:

| Patient ID | Risk Score (%) | Risk Category | ... |
|------------|----------------|---------------|-----|
| PID103422  | 71.45          | High          | ... |

---

## 📘 Notes

- Model uses an **ensemble** to improve prediction stability.
- Can be expanded into a **Flask/Django web app** or dashboard.
- Suitable for **early warning systems** and **preventive screening** in healthcare settings.

---

## 📜 License

MIT License — For research, learning, and non-commercial use.

---

## 🙌 Acknowledgements

- Patient dataset courtesy of **Maro Medical Center** *(anonymized)*
- Developed as part of a master's study in **Big Data Analytics**
