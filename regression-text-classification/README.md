## 📘 Overview

This project explores how linear regression, logistic regression, and multi-class logistic regression models perform on two classification tasks. All models were implemented from scratch to gain a deeper understanding of their mathematical foundations and performance behavior.

- **Binary Classification**: Breast Cancer Wisconsin dataset  
- **Multi-Class Classification**: Palmer Penguins dataset

We focus on:
- Data preprocessing
- Feature importance analysis
- Gradient checking for logistic models
- Evaluation using AUROC and accuracy
- Visualization with ROC curves and heatmaps

---

## 📂 Datasets

### 🧪 Breast Cancer Wisconsin (Binary Classification)
- Predicts whether a tumor is malignant or benign based on 30 numerical features.
- Used for testing classification models in high-dimensional spaces.
- Feature selection applied based on linear regression coefficients.

### 🐧 Palmer Penguins (Multi-Class Classification)
- Classifies penguins into 3 species: Adelie, Chinstrap, Gentoo.
- Uses 4 numerical features like culmen length and flipper length.
- Categorical features were removed; data is relatively balanced.

Both datasets were standardized to improve model stability.

---

## 🧠 Methods & Implementation

### Linear Regression (SLR & MLR)
- Implemented simple and multiple linear regression.
- Used as a baseline for both binary and multi-class tasks.
- Coefficients analyzed for feature importance.

### Logistic Regression (Binary & Multinomial)
- Implemented from scratch using gradient descent.
- **Gradient checking** validated correctness of gradient computations.
- Cross-entropy loss monitored during training to ensure proper convergence.

### Feature Importance
- For binary tasks: Coefficients from linear models and logistic regression were compared.
- For multi-class: One-vs-rest logistic regression and heatmaps used to show how features contribute to each class.

---

## 📊 Results

### Binary Classification (Breast Cancer Dataset)
| Model | Accuracy | AUROC |
|-------|----------|--------|
| Simple Linear Regression (SLR) | 92.40% | 0.92 |
| Multiple Linear Regression (MLR) | 97.08% | 0.97 |
| Binary Logistic Regression (BLR) | 97.66% | 0.97 |

- MLR and BLR significantly outperformed SLR.
- ROC curves confirm stronger separability with logistic models.

### Multi-Class Classification (Penguin Dataset)
| Model | Accuracy |
|-------|----------|
| Simple Linear Regression (SLR) | 93.69% |
| Multivariate Linear Regression (MVLR) | 100.00% |
| Multi-Class Logistic Regression (MCLR) | 100.00% |

- Both MVLR and MCLR performed perfectly on test data.
- Feature heatmaps reveal class-specific feature influence.

---

## 🔍 Key Functions & Techniques

- `gradient_check()`: Validates gradient computations.
- `sigmoid()` and `softmax()`: Used in logistic regression for binary and multi-class cases.
- `cross_entropy_loss()`: Monitors convergence during training.
- `mean_squared_error()`, `accuracy_score`, `roc_auc_score`: For evaluation.
- Heatmaps, bar charts, ROC plots: Visual interpretation of model behavior.

---

## 📌 Conclusions

- **Logistic regression outperforms linear regression** for classification tasks due to its probabilistic nature and ability to model decision boundaries.
- **Linear regression** is faster to train but not designed for classification.
- Feature importance rankings are similar across models but logistic regression places more emphasis on separability.
- Dataset structure strongly influences model performance.

