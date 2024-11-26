# 🧮 Loan Application Classification with PCA and Multiple Classifiers

**Course Project**: This project explores binary classification of loan applications using various classifiers and evaluates the impact of dimensionality reduction through PCA on classifier performance.

---

## 📋 Table of Contents
- [Overview](#overview)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Results](#results)
- [Discussion](#discussion)
- [How to Run the Code](#how-to-run-the-code)
- [Dependencies](#dependencies)

---

## 🌟 Overview

This project investigates the performance of four classifiers:
1. **Linear Discriminant Analysis (LDA)**  
2. **Decision Tree**  
3. **k-Nearest Neighbors (kNN)**  
4. **Support Vector Machine (SVM)**  

Additionally, it evaluates **kNN** and **SVM** performance on PCA-reduced datasets to analyze the effect of dimensionality reduction.

### Objectives:
1. Implement and evaluate classifiers on original features.
2. Use PCA to reduce dimensionality and re-evaluate kNN and SVM classifiers.
3. Compare performance metrics such as accuracy, Type 1 error, and Type 2 error.

---

## 📊 Dataset Description

Two datasets were used for this analysis:
- **TrainingData.csv**: 900 samples (450 approved, 450 denied applications)
- **TestingData.csv**: 400 samples (200 approved, 200 denied applications)

Each dataset contains **27 features**, with the target label indicating loan approval status:
- `0`: Approved
- `1`: Denied

Key preprocessing steps included:
- Handling missing values (if any).
- Splitting datasets into training and testing sets.
- Standardizing features for kNN and SVM classifiers.

---

## 🛠 Methodology

### **Classifiers**
1. **LDA**: Projects data onto a linear subspace for classification.  
2. **Decision Tree**: Employs CART with Gini impurity for decision-making.  
3. **kNN**: Tested with `k=1, 3, 5, 10`.  
4. **SVM**: Linear kernel with soft margin (C=1).

### **Dimensionality Reduction**
- **PCA**: Feature space reduced to 5, 10, and 15 principal components.
- Re-evaluated kNN (`k=5`) and SVM on PCA-transformed datasets.

### **Metrics**
1. **Accuracy**: Overall correctness of predictions.  
2. **Type 1 Error**: Misclassifying approved applications as denied.  
3. **Type 2 Error**: Misclassifying denied applications as approved.

---

## 📈 Results

### **Classifier Performance (Original Features)**
| Classifier       | Accuracy | Type 1 Error | Type 2 Error |
|-------------------|----------|--------------|--------------|
| **LDA**          | 91%      | 16%          | 3%           |
| **Decision Tree** | 82%      | 18%          | 17%          |
| **kNN (k=5)**     | 83%      | 20%          | 14%          |
| **SVM**           | 86%      | 20%          | 7%           |

### **PCA-Reduced Performance**
| PCA Components | Classifier | Accuracy | Type 1 Error | Type 2 Error |
|----------------|------------|----------|--------------|--------------|
| **5**          | kNN        | 84%      | 19%          | 12%          |
| **5**          | SVM        | 86%      | 19%          | 8%           |
| **10**         | kNN        | 83%      | 20%          | 14%          |
| **10**         | SVM        | 87%      | 17%          | 8%           |
| **15**         | kNN        | 83%      | 20%          | 14%          |
| **15**         | SVM        | 89%      | 17%          | 7%           |

---

## 🧐 Discussion

### **Insights**
1. **SVM with PCA**:  
   - Achieved the best balance of Type 1 and Type 2 errors.
   - Demonstrated PCA’s effectiveness in handling high-dimensional data.

2. **Impact of PCA**:  
   - Improved SVM performance significantly while reducing computational overhead.
   - Marginal improvement for kNN, indicating its lesser reliance on dimensionality reduction.

3. **Classifier Strengths**:  
   - **LDA**: Best for denied applications (low Type 2 error).  
   - **SVM**: Balanced performance across metrics.  
   - **Decision Tree**: High error rates due to overfitting.  
   - **kNN**: Sensitive to Type 1 errors (misclassifying approvals).

---

## 💻 How to Run the Code

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/loan-application-classification.git
