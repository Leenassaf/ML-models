**BERT Probing vs Fine-Tuning for AG News Classification**  

## 📘 Overview

This project investigates two strategies for applying `bert-base-uncased` to the **AG News** classification task:
1. **Probing with frozen BERT** embeddings using lightweight classifiers.
2. **End-to-end fine-tuning** of BERT with supervised training.

Additionally, we include **attention matrix visualizations** to interpret model behavior and compare the effectiveness of embedding strategies.

---

## 🗃️ Dataset

### 📰 AG News Corpus
- 120,000 training samples and 7,600 test samples.
- Each sample includes a news headline + short description.
- 4 balanced classes: **World**, **Sports**, **Business**, **Sci/Tech**.
- Loaded via Hugging Face’s `datasets` library.
- Tokenized using `bert-base-uncased` with max length of 128.

---

## ⚙️ Methods

### 🔹 Probing (Frozen BERT)
- BERT is used only as a **feature extractor**, no weights updated.
- **Sentence embeddings** are generated using:
  - `[CLS]` token
  - First token
  - Last token
  - **Mean pooling** (best performer)
- Classifiers used:
  - **Logistic Regression** (`scikit-learn`)
  - **K-Nearest Neighbors (KNN)`** with optimized K.

### 🔹 Fine-Tuning BERT
- Full BERT model is trained with a classification head.
- Reduced training set (20,000 examples) due to resource constraints.
- Managed with Hugging Face’s `Trainer` class.
- Training: 3 epochs with early stopping and validation monitoring.

---

## 🧪 Key Functions and Tools

- `transformers.BertTokenizer`, `BertModel`, `Trainer`
- `datasets.load_dataset()` for AG News
- `bertviz` for attention visualization
- `mean_pooling()`, `extract_cls_token()`: embedding strategies
- Evaluation metrics: `accuracy_score`, attention heatmaps

---

## 📊 Results Summary

### 🧩 Probing (Frozen BERT Embeddings)

| Embedding      | Classifier         | Accuracy |
|----------------|--------------------|----------|
| [CLS] token    | Logistic Regression | 85.20%   |
| Mean pooling   | Logistic Regression | 86.70%   |
| Mean pooling   | KNN (K=10)          | 88.90%   |

- **Best probing result**: 88.90% with KNN + mean pooling.

### 🧠 Fine-Tuned BERT

| Epoch | Validation Accuracy | Test Accuracy |
|-------|----------------------|----------------|
| 3     | 92.55%              | **93.12%**     |

- Fine-tuned model outperforms probing methods by ~4%.
- Highlights benefits of end-to-end training.

---

## 🎯 Attention Visualization

- Attention weights from final layer's [CLS] token visualized.
- Correct predictions show high attention on key domain terms (e.g. "gold", "space").
- Misclassifications often involve overlapping or ambiguous vocabulary.
- `bertviz` used to plot attention heatmaps for each label.

---

## 🔍 Insights

- **Mean pooling** outperforms `[CLS]` and single-token strategies.
- Fine-tuning BERT provides **best performance** but is more computationally expensive.
- Attention matrices reveal how tokens influence predictions — useful for interpretability.
- Results support the use of frozen BERT embeddings for lightweight applications, and fine-tuning for higher accuracy.

---
