# Visceral-Fat-Risk-level-Prediction (Female Visceral Fat Dataset)
Visceral fat intervention prediction using machine learning. Includes full preprocessing (outliers, missing values, scaling), SMOTE oversampling, and evaluation of four ML models with KNN as the best performer.

A machine-learning project to predict whether **intervention is required** based on visceral fat levels in female participants.

##  Project Overview
- **Problem Type:** Classification  
- **Goal:** Predict “Intervention Required: YES/NO” based on clinical & lifestyle features.  
- **Dataset Issues Addressed:** outliers, missing values, incorrect data types, invalid values, class imbalance, and scaling.

## 🛠 Workflow Summary
1. **Data Cleaning**
   - Removed unnecessary columns (`SUBJECT_ID`, `SEX`, `DISCONTINUED_NO_`)
   - Removed outliers (Age, Height, Computer use)
   - Handled missing values (BP → mean; cigarettes → 0)
   - Converted smoking status to integer

2. **Feature Engineering**
   - Created class label from visceral fat volume  
   - MinMax normalization applied  
   - SMOTE used to balance classes  

3. **Models Trained**
   - Gaussian Naive Bayes  
   - Decision Tree  
   - KNN  
   - MLP (Neural Network)  

4. **Evaluation Metrics**
   - Focused on **Recall**, **Precision**, **F1-score**
   - Accuracy & AUC not prioritized due to class imbalance
     
**Best Model: KNN Classifier**

| Metric | Score |
|-------|-------|
| Recall | **0.78** |
| Precision | 0.81 |
| F1-score | 0.77 |

After tuning (`n_neighbors=3`, `weights='distance'`), recall = **0.71**.

**Why KNN?**  
Consistently identifies the majority of high/moderate-risk patients, aligning with healthcare intervention goals.

