## 📘 Overview

I implemented and evaluated two fundamental machine learning models: **K-Nearest Neighbors (KNN)** and **Decision Trees (DT)**. I explored their performance on two datasets: one for binary classification (Heart Disease) and one for multi-class classification (Penguin Species).

Our pipeline included:
- Data cleaning, encoding, and scaling
- Feature selection using statistical measures
- Model implementation from scratch using Python classes
- Hyperparameter tuning (K for KNN, depth for DT)
- Evaluation using accuracy and AUROC

---

## 📊 Datasets

### ❤️ Heart Disease Dataset
- Predicts presence of heart disease based on mixed features (numerical, categorical, binary).
- Converted target into binary values (0 = no disease, 1 = presence of disease).
- Used Gower distance in KNN to handle mixed data types.
- Feature selection based on squared mean difference, correlation filtering, and multicollinearity checks.

### 🐧 Penguin Dataset
- Classifies penguins into three species based on physical measurements (e.g., culmen length, flipper length).
- Only numerical features retained (4 total), plus one binary feature (sex).
- Feature selection based on squared mean differences in class means.

---

## ⚙️ Methods

### 🔍 Weighted K-Nearest Neighbors (KNN)
- Uses **Euclidean**, **Manhattan**, or **Gower** distance.
- Weighted based on inverse of distance to neighbors.
- Closest neighbors have more influence on prediction.
- Implemented as a custom Python class with `fit`, `predict`, and `evaluate` methods.

### 🌳 Decision Trees (DT)
- Tree structure with nodes splitting data based on optimal thresholds.
- Tested three cost functions: **Gini Index**, **Entropy**, and **Misclassification**.
- Hyperparameter tuning on max tree depth.
- Implemented from scratch, including tree-building and prediction logic.

---

## 🧪 Functions & Techniques

- `gower_distance()`: Custom function for handling mixed data types.
- `calculate_accuracy()`, `calculate_auroc()`: Evaluation metrics.
- `feature_selection()`: Removes redundant or low-impact variables.
- `train_test_split()`, `StandardScaler()`, `OneHotEncoder()`: Data preparation.

---

## 📈 Results

### 🔹 Penguin Dataset
| Model       | Distance/Cost | Param     | Accuracy | AUROC |
|-------------|----------------|-----------|----------|--------|
| KNN         | Euclidean      | K = 3     | 98.5%    | 0.98   |
| KNN         | Manhattan      | K = 3     | 98.5%    | 0.98   |
| Decision Tree | Gini Index   | Depth = 2 | 94.0%    | 0.95   |
| Decision Tree | Entropy      | Depth = 2 | 94.3%    | 0.96   |
| Decision Tree | Misclassification | Depth = 2 | 95.2% | 0.96   |

### 🔹 Heart Disease Dataset
| Model       | Distance/Cost | Param     | Accuracy | AUROC |
|-------------|----------------|-----------|----------|--------|
| KNN         | Gower          | K = 7     | 85.0%    | 0.91   |
| Decision Tree | Gini Index   | Depth = 5 | 78.3%    | 0.78   |
| Decision Tree | Entropy      | Depth = 5 | 80.0%    | 0.77   |
| Decision Tree | Misclassification | Depth = 1 | 78.3% | 0.84   |

- **Best Penguin Model**: KNN (K=3), 98.5% accuracy, 0.98 AUROC
- **Best Heart Model**: KNN (K=7), 85% accuracy, 0.91 AUROC
- Decision Tree performance was slightly lower for heart disease.

---

## 🧠 Feature Importance Insights

- Feature rankings differed between squared mean difference and Decision Tree-based importance.
- In the Penguin dataset, culmen length and depth were most influential.
- In the Heart Disease dataset, `oldpeak` and `age` emerged as key features.
- Differences in rankings arose due to how each method defines “importance” (variance vs. decision boundaries).

---

## 📌 Conclusion

- KNN outperformed Decision Trees on the Heart Disease dataset, particularly due to Gower distance handling.
- Both models performed exceptionally well on the Penguin dataset.
- Feature selection and proper distance/cost functions greatly influenced results.
- Further refinement of feature selection could improve accuracy for complex datasets like Heart Disease.
