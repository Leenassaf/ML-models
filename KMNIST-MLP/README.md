**Multilayer Perceptron and CNN for Image Classification**  

## 📘 Overview

We implemented a **Multilayer Perceptron (MLP) from scratch** to classify images from the **Kuzushiji-MNIST (KMNIST)** dataset. We compared our custom-built MLP models with a **Convolutional Neural Network (CNN)** implemented using TensorFlow and Keras.

Our focus was on:
- Building and training MLPs with different architectures
- Experimenting with activation functions and L2 regularization
- Tuning hyperparameters such as learning rate and batch size
- Comparing results with a CNN baseline

---

## 🗃️ Dataset

### ✍️ Kuzushiji-MNIST (KMNIST)
- 70,000 grayscale images (28×28 pixels) of handwritten Japanese characters.
- 60,000 training samples, 10,000 test samples.
- 10 classes representing different Hiragana characters.
- Preprocessed by flattening to 784-dimensional vectors and standardizing features.

---

## ⚙️ Methods

### 🔸 MLP (Multilayer Perceptron)
- Implemented **from scratch** using NumPy.
- Architectures tested:
  - No hidden layer
  - Single hidden layer (256 units)
  - Two hidden layers (256 and 128 units)
- Activation functions tested:
  - ReLU, LeakyReLU in hidden layers
  - Softmax or Sigmoid in output
- L2 regularization tested with different λ values

### 🔸 CNN (TensorFlow/Keras)
- Used convolutional layers + fully connected layers
- Early stopping based on validation loss
- Best results with 256 hidden units in the dense layer

---

## 🧪 Key Functions

- `forward_pass()`, `backward_pass()`: Custom MLP training
- `train()`, `evaluate()`: Fit model and compute accuracy
- `plot_accuracy_curves()`: Compare training and validation trends
- `apply_l2_regularization()`: Adds L2 penalty to weights
- `build_cnn_model()`: CNN construction with Keras

---

## 📊 Results Summary

### 🔹 MLP Accuracy (Test Set)
| Architecture                 | Test Accuracy |
|-----------------------------|---------------|
| No hidden layer             | 66.96%        |
| Single hidden layer (256)   | 89.31%        |
| Two hidden layers (256,128) | 90.05%        |
| LeakyReLU + Sigmoid (2-layer) | 90.18%     |

### 🔹 CNN Accuracy (Test Set)
| CNN (256 FC units) | 94.78% |

### 🔹 Regularization Findings
| λ       | Test Accuracy |
|---------|----------------|
| 0.1     | 42.95%         |
| 0.001   | **90.25%**     |

- Best regularization strength: `λ = 0.001`
- Best MLP configuration: 2 layers (256, 128), batch size = 32, learning rate = 0.05

---

## 🔍 Insights

- MLPs benefit from deeper networks but show diminishing returns beyond 2 layers.
- Activation functions impact training stability — **LeakyReLU** outperformed ReLU.
- **Regularization** (L2) was essential to avoid overfitting and improve generalization.
- CNN outperformed all MLP models by a wide margin, highlighting the advantage of convolutional layers in image recognition.

---
