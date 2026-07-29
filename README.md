# Assignment8-for-IN26011064

# 🔢 Handwritten Digit Recognition using ANN

> Classifying handwritten digits (0–9) from the MNIST dataset using a fully connected Artificial Neural Network built with TensorFlow/Keras.

**Author:** Kushagra Raghuvanshi  

**Registration Number:** 23BSA10072

**Application Number:** IN26011064

**Batch Number:** 2B

**Email ID:** kushagra.23bsa10072@vitbhopal.ac.in 



---

## 🎯 Objective

To develop an Artificial Neural Network (ANN) that can accurately classify handwritten digits (0–9) from the MNIST dataset, simulating a real-world use case where a postal service organization automates the recognition of handwritten digits on postal codes.

---

## 📂 Dataset

| Property | Details |
|---|---|
| **Name** | MNIST Handwritten Digits (CSV format) |
| **Source** | Kaggle |
| **Link** | [mnist-in-csv](https://www.kaggle.com/datasets/oddrationale/mnist-in-csv) |
| **Training Samples** | 60,000 |
| **Test Samples** | 10,000 |
| **Input Features** | 784 pixel values (28×28 grayscale image, flattened) |
| **Target Variable** | `label` — digit class (0 through 9) |

---

## 🛠️ Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading and exploration |
| `numpy` | Numerical operations and array manipulation |
| `matplotlib` | Data visualization and plotting |
| `seaborn` | Confusion matrix heatmap |
| `scikit-learn` | Train-test split, evaluation metrics |
| `tensorflow` / `keras` | Building, compiling, and training the ANN |

---

## 🔬 Methodology

```
1. Data Understanding
   ├── Load train/test CSVs using Pandas
   ├── Inspect shape, dtypes, class distribution
   └── Visualize sample digit images

2. Data Preprocessing
   ├── Check for missing values (none found)
   ├── Separate features (X) and target (y)
   ├── Normalize pixel values: [0, 255] → [0.0, 1.0]
   ├── Split into 80% training / 20% testing (stratified)
   └── Apply One-Hot Encoding to target labels

3. Model Development
   ├── Build Sequential ANN with Keras
   ├── Compile with Adam optimizer & Categorical Crossentropy loss
   └── Train for 10 epochs with 10% validation split

4. Model Evaluation
   ├── Compute test accuracy and loss
   ├── Generate Confusion Matrix
   ├── Print Classification Report (precision, recall, F1)
   └── Plot Accuracy vs Epoch and Loss vs Epoch curves
```

---

## 🧠 Model Architecture

```
Input Layer       →  784 neurons  (flattened 28×28 pixel image)
        ↓
Hidden Layer 1    →  128 neurons  (Activation: ReLU)
        ↓
Hidden Layer 2    →   64 neurons  (Activation: ReLU)
        ↓
Output Layer      →   10 neurons  (Activation: Softmax)
```

| Layer | Neurons | Activation | Parameters |
|---|---|---|---|
| Input | 784 | — | — |
| Hidden Layer 1 | 128 | ReLU | 100,480 |
| Hidden Layer 2 | 64 | ReLU | 8,256 |
| Output | 10 | Softmax | 650 |
| **Total** | | | **109,386** |

**Compiler Settings**

| Setting | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |
| Metric | Accuracy |
| Epochs | 10 |
| Batch Size | 32 |

---

## 📊 Results

| Metric | Value |
|---|---|
| **Test Accuracy** | ~97–98% |
| **Test Loss** | ~0.07–0.10 |

### Observations

1. **High accuracy in 10 epochs** — The model converges quickly, reaching ~97–98% test accuracy within just 10 epochs, showing that a simple 2-hidden-layer ANN is very effective on MNIST.

2. **Smooth convergence** — Both training and validation accuracy increase consistently while loss decreases, indicating the model generalizes well without significant overfitting.

3. **Challenging digit pairs** — The confusion matrix reveals that visually similar digits (e.g., 3↔5, 4↔9, 7↔1) are the primary sources of misclassification, consistent with the inherent ambiguity in human handwriting.

4. **Class-wise performance** — Digits like `0`, `1`, and `6` achieve the highest per-class precision and recall, while `4`, `7`, and `9` are comparatively harder to classify due to structural similarity.

---

## ✅ Conclusion

This project successfully built and evaluated an ANN for handwritten digit recognition on the MNIST dataset, achieving a test accuracy of approximately **97–98%**. Hidden layers are central to this performance — they learn hierarchical, non-linear feature representations that allow the model to distinguish complex digit patterns a single-layer model could not handle.

A key advantage of Deep Learning over traditional Machine Learning is its ability to **automatically learn features directly from raw pixel data**, eliminating the need for manual feature engineering. However, ANNs do have limitations: they are sensitive to hyperparameter choices, require large labeled datasets, and are computationally expensive. For even higher accuracy, Convolutional Neural Networks (CNNs) would be the natural next step, as they are specifically designed to exploit the spatial structure of image data.

---
