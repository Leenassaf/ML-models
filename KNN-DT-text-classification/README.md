## 🧠 Project Overview

The goal of this project is to:
- Preprocess and vectorize news articles or text samples.
- Train and evaluate classifiers using KNN and Decision Trees.
- Interpret model predictions and decision rules.
- Visualize data and performance metrics.

I used a simple, interpretable approach suitable for small to medium-sized text datasets. The dataset is tokenized, vectorized (using one-hot or TF-IDF), and fed into scikit-learn classifiers.

## 🧪 Methods Used

### 1. **Text Preprocessing**
- **Lowercasing**: Normalize text to lowercase.
- **Tokenization**: Split text into words.
- **Stopword Removal** (optional): Eliminate common words.
- **Vectorization**: Convert text to numeric form (e.g., TF-IDF or one-hot).

### 2. **K-Nearest Neighbors (KNN)**
- KNN is a **non-parametric**, instance-based learning method.
- I use **Gower distance** to handle mixed types of features.
- Classification is based on the majority class of the `k` nearest samples.

### 3. **Decision Tree (DT)**
- DT is a **supervised learning algorithm** that splits data based on features to make decisions.
- I used scikit-learn’s `DecisionTreeClassifier` and visualize the tree structure.
- The model’s interpretability allows me to trace how predictions are made.

### 4. **Evaluation**
- **Accuracy**: Proportion of correct predictions.
- **Confusion Matrix**: Visualizes correct and incorrect classifications.
- **Visualization**: Plotting trees, class distributions, and prediction outcomes.
