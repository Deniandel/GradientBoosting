## **Gradient Boosting for Wine Quality Prediction**

### **Overview**
This project investigated the use of **Gradient Boosting**, specifically through **XGBoost**, to predict the quality of red wine based on various physicochemical features. The study compares the performance of **XGBoost** against a **baseline Decision Tree model** for both regression and classification tasks. In this repository, you will find a full paper writeup of the results found, a presentation that sums up what was done, along with the actual code used to peform Gradient Boosting on the dataset.

---

### **Dataset**
- **Source**: [Wine Quality Dataset – Kaggle](https://www.kaggle.com/datasets/yasserh/winequality-dataset)
- **Samples**: ~1600 red wine records
- **Features**: 11 numeric attributes (e.g., pH, alcohol, acidity)
- **Target**: Wine quality score (0–10, later binned into classes 3–8 for classification)

---

### **Methodology**
- **Preprocessing**: Dropped non-informative features, scaled inputs for consistency
- **Models Implemented**:
  - Decision Tree (baseline)
  - XGBoost (with and without hyperparameter tuning)
- **Tuning**: Performed via **GridSearchCV** (3-fold cross-validation)
- **Evaluation Metrics**:
  - **Regression**: RMSE, R²
  - **Classification**: Accuracy, Confusion Matrix

---

###**Results Summary**

#### **Regression (Continuous Score)**
| Model                | RMSE   | R²     |
|----------------------|--------|--------|
| Decision Tree        | 0.7103 | 0.1324 |
| XGBoost (Untuned)    | 0.5848 | 0.4013 |
| XGBoost (Tuned)      | 0.5782 | 0.4251 |

#### **Classification (Binned Classes 3–8)**
| Model                | Accuracy |
|----------------------|----------|
| Decision Tree        | 59.83%   |
| XGBoost (Untuned)    | 68.12%   |
| XGBoost (Tuned)      | 69.43%   |

---

### **Key Insights**
- **XGBoost significantly outperformed Decision Trees** in both regression and classification tasks.
- **Model tuning improved results**, though the gains beyond the default XGBoost model were marginal.
- **Class imbalance** affected classification accuracy, with minority labels frequently misclassified.
- Feature importance revealed **alcohol** as the most predictive attribute, followed by **sulfates** and **volatile acidity**.

---

### **Conclusion**
Gradient Boosting via XGBoost proved to be a **powerful, flexible, and generalizable model** for structured data tasks. While some limitations arose due to label imbalance, the method demonstrated robust performance and clear advantages over simpler models like decision trees.
