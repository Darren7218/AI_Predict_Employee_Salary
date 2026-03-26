# AI_Predict_Employee_Salary

## 📌 Project Overview
This project is developed for the **UCCD2063 Artificial Intelligence Techniques** Group Assignment. The primary objective is to build and evaluate machine learning models capable of predicting the salary category (Low, Medium, High) of IT professionals based on various demographic and professional attributes.

## 📊 Dataset
* **Source:** `Tech_employee_salary.csv`
* **Size:** 5,000 records, 20 features.
* **Target Variable:** `salary_category` (Classes: Low, Medium, High)
* **Key Features:** Years of experience, education level, job title, work mode, performance rating, projects completed, and GitHub contributions.

## 🛠️ Tech Stack & Libraries
* **Language:** Python
* **Data Manipulation & Visualization:** Pandas, NumPy, Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn
* **Gradient Boosting Frameworks:** XGBoost, LightGBM, CatBoost
* **Deep Learning:** TensorFlow / Keras (for custom Embedding Neural Networks)

## ⚙️ Methodology & Workflow
1. **Data Preprocessing:** * Handled missing values using median imputation for numerical data (`bonus_percentage`, `remote_work_days`, `satisfaction_score`) and categorical imputation (`stock_options`).
   * Encoded categorical variables using `LabelEncoder`.
   * Standardized numerical features using `StandardScaler`.
2. **Model Training (Baseline):** Trained Random Forest, XGBoost, and MLP Neural Networks.
3. **Advanced Gradient Boosting:** Implemented CatBoost and LightGBM with early stopping to prevent overfitting.
4. **Deep Learning:** Built a custom Neural Network utilizing Categorical Embeddings for high-cardinality features.
5. **Hyperparameter Tuning:** Applied `GridSearchCV` and `RandomizedSearchCV` to optimize the Random Forest, XGBoost, MLP, CatBoost, and LightGBM models.

## 📈 Model Performance & Results
After hyperparameter tuning, **XGBoost** emerged as the best-performing model for this dataset.

| Model | Final Test Accuracy |
| :--- | :--- |
| **XGBoost (Tuned)** | **~79.6%** |
| CatBoost (Tuned) | ~79.3% |
| LightGBM (Tuned) | ~78.9% |
| Random Forest (Tuned)| ~72.4% |
| Custom NN (Embeddings)| ~69.9% |
| MLP Neural Net (Tuned)| ~65.7% |

## 💡 Key Findings & Conclusion

* **Best Performing Model:** **XGBoost** achieved the highest accuracy (79.6%) and the best balance of Precision and Recall across all three salary categories. Gradient boosting methods (XGBoost, CatBoost, LightGBM) significantly outperformed standard Neural Networks and Random Forests on this tabular data.
* **Important Features:** Based on the XGBoost and Random Forest feature importance plots, the most critical factors determining salary category generally revolve around professional tenure and output *(Note: Update this bullet point with the exact top 3 features shown in your generated bar charts, e.g., years_experience, projects_completed, etc.)*.
* **Limitations & Biases:** * **Class Imbalance:** The model performs exceptionally well at identifying "Medium" salaries (88% recall with XGBoost) but struggles slightly more with the "High" salary category (59% recall).
   * **Data Constraints:** Certain features like `stock_options` and `bonus_percentage` had missing values that required imputation, which may introduce slight statistical bias. Furthermore, external economic factors (like inflation or specific company budgets) are not captured in this dataset.

---
**Course:** UCCD2063 Artificial Intelligence Techniques  
**Institution:** Universiti Tunku Abdul Rahman (UTAR)  
**Program:** Computer Science
