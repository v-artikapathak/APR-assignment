# 🧠 Classification and Prediction of Dementia using Logistic Regression (OASIS Dataset)

## 1. Introduction
Dementia is a progressive neurological condition affecting memory, thinking, and behavior. Early detection is crucial for timely intervention.  
This study applies **Logistic Regression** to classify patients into three groups based on neuropsychological and MRI-derived biomarkers from the **OASIS dataset**.  

**Target Classes:**  
| Label | Group Description |
|-------|-----------------|
| 0     | Converted (patients who transitioned from nondemented to demented) |
| 1     | Demented |
| 2     | Nondemented |

---

## 2. Dataset
**Source:** [OASIS – Open Access Series of Imaging Studies](https://datasetsearch.research.google.com/search?src=0&query=svm&docid=L2cvMTFqbnltNjduMQ%3D%3D)  

**Features Used:**  
- Age  
- Education (EDUC)  
- Socioeconomic Status (SES)  
- MMSE (Mini-Mental State Examination)  
- CDR (Clinical Dementia Rating)  
- eTIV (Estimated Total Intracranial Volume)  
- nWBV (Normalized Whole Brain Volume)  
- ASF (Atlas Scaling Factor)  

**Target Variable:** `Group` (Converted, Demented, Nondemented)

---

## 3. Methodology

### 3.1 Preprocessing
- Handled missing values  
- Encoded categorical variables numerically  
- Normalized features for logistic regression  

### 3.2 Model
- **Algorithm:** Logistic Regression  
- **Multiclass Strategy:** One-vs-Rest (OVR)  

### 3.3 Evaluation Metrics
- Confusion Matrix  
- ROC Curve & AUC  
- Accuracy, Precision, Recall, F1-score  

---

## 4. Results

- **Accuracy:** 0.90  
- **Precision:** 0.916  
- **Recall:** 0.90  
- **F1-score:** 0.873  

### 4.1 Confusion Matrix
| True \ Pred | Converted (0) | Demented (1) | Nondemented (2) |
|-------------|---------------|--------------|----------------|
| Converted (0) | 0             | 0            | 8              |
| Demented (1)  | 0             | 25           | 4              |
| Nondemented (2)| 0             | 0            | 38             |

**Interpretation:**  
- Converted (0): All misclassified as Nondemented  
- Demented (1): Mostly correct, minor misclassification  
- Nondemented (2): Correctly classified  

### 4.2 ROC Curve (OVR)
**AUC Scores:**  
- Converted (0): 0.66 (weak separation)  
- Demented (1): 0.99 (perfect classification)  
- Nondemented (2): 0.98 (excellent classification)  

### 4.3 Performance Summary
- **Overall Accuracy:** ~90%  
- **Strengths:** Excellent detection of Demented and Nondemented groups  
- **Weaknesses:** Poor detection of Converted patients  

---

## 5. Discussion
Logistic Regression effectively distinguishes Demented and Nondemented groups.  
**Challenges:**  
- Converted class overlaps with Nondemented  
- Class imbalance (few Converted cases)  
- Feature similarity between Converted and Nondemented patients  

---

## 6. Conclusion & Future Work
- Logistic Regression shows strong predictive power for dementia classification.  
- Excellent for Demented and Nondemented, weak for Converted cases.  

**Future Improvements:**  
- Apply class balancing (SMOTE, class weights)  
- Feature selection/dimensionality reduction to separate Converted cases  
- Compare with ensemble models (Random Forest, XGBoost)  
- Expand dataset size for robust generalization  

---

## 📈 Visualizations
**Confusion Matrix:**  
![Confusion Matrix](path_to_confusion_matrix_image.png)  

**ROC Curves:**  
![ROC Curve](path_to_roc_curve_image.png)
