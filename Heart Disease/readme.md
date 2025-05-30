# Heart Disease Prediction Using Machine Learning

This project predicts heart disease presence based on clinical data from the UCI Heart Disease dataset using Random Forest and Logistic Regression classifiers.

---

## Dataset Overview

- Samples: 297
- Features: 13 clinical variables (age, sex, chest pain type, blood pressure, cholesterol, etc.)
- Target: `condition` (0 = No heart disease, 1 = Heart disease)

---

## Models and Results

### 1. Random Forest Classifier (Tuned)

- Parameters: `max_depth=7`, `min_samples_leaf=5`, `max_features='sqrt'`, `class_weight='balanced'`
- Training accuracy: ~89.5%
- Test accuracy: ~83.3%
- Good balance between precision and recall; recall for heart disease ~75%.

### 2. Logistic Regression

- Basic Logistic Regression:
  - Train accuracy: ~85.2%
  - Test accuracy: ~91.7%
  
- Tuned Logistic Regression (`solver='liblinear'`, `class_weight='balanced'`):
  - Train accuracy: ~85.2%
  - Test accuracy: ~88.3%
  - Precision (No disease): 0.84
  - Precision (Disease): 0.96
  - Recall (No disease): 0.97
  - Recall (Disease): 0.79
  - Overall accuracy: 88%

---

## Key Metrics Comparison

| Metric       | Random Forest | Basic Logistic Regression | Tuned Logistic Regression |
|--------------|---------------|---------------------------|---------------------------|
| Accuracy     | 83.3%         | 91.7%                     | 88.3%                     |
| Precision (Disease) | 0.88     | (Not Provided)            | 0.96                      |
| Recall (Disease)    | 0.75     | (Not Provided)            | 0.79                      |
| F1-score (Disease)  | 0.81     | (Not Provided)            | 0.86                      |
| ROC AUC     | (Not calculated) | (Not provided)           | (Not provided)            |

---

## Insights & Recommendations

- Basic Logistic Regression yields the highest test accuracy but may favor precision.
- Tuned Logistic Regression improves recall for the disease class, balancing clinical needs.
- Random Forest provides good interpretability with feature importance but slightly lower test accuracy.
- Recall (sensitivity) for disease detection remains a critical metric to reduce false negatives.
- Future work should include cross-validation, threshold tuning, and experimenting with advanced models.

---

## Usage

1. Preprocess the dataset as needed.
2. Train models using the provided parameters.
3. Evaluate models using accuracy, precision, recall, F1-score.
4. Tune classification thresholds to meet clinical sensitivity/specificity requirements.
5. Deploy with continuous monitoring and updates.
