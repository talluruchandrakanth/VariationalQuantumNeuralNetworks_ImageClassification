# ⚛️ Hybrid Quantum-Classical Neural Network (QNN) for Image Classification

## 📖 Project Overview

In the era of Noisy Intermediate-Scale Quantum (NISQ) hardware, deploying deep learning models on quantum processors presents severe challenges due to strict qubit constraints and high noise rates. To address this computational bottleneck, this deep-tech research project designs, implements, and evaluates a **Hybrid Quantum-Classical Neural Network (QNN)** built using **Python, PyTorch, and PennyLane**.

The project bridges classical machine learning preprocessing with quantum variational circuits to achieve high-accuracy image classification while drastically reducing spatial complexity.

---

## 🚀 Key Achievements & Performance

- **Massive Spatial Efficiency:** Achieved **94.00%** binary classification accuracy on the Fashion-MNIST dataset with just **34 trainable parameters**, compared to **1,610 parameters** required by a classical Convolutional Neural Network (CNN) baseline.
- **High-Dimensional Generalization:** Extended the core 4-qubit variational architecture to process dense RGB color images from the CIFAR-100 dataset.
- **Stable Training Dynamics:** Demonstrated rapid convergence and stable gradient descent across training epochs using PennyLane's automatic differentiation (parameter-shift rule) paired with the Adam optimizer.

---

## 🧠 Architecture & Algorithm Pipeline

The pipeline bridges classical preprocessing and quantum machine learning through an end-to-end, multi-step architecture:

1. **Dataset & Filtering:** Processes binary image classification tasks, specifically:
   - T-shirt/top vs. Trouser (Fashion-MNIST)
   - Apple vs. Aquarium Fish (CIFAR-100)
2. **Classical Dimensionality Reduction (PCA):** Current quantum simulators cannot efficiently process raw high-dimensional inputs (784 features for grayscale, 3,072 for RGB). Principal Component Analysis (PCA) compresses the feature space down to **4 essential components**.
3. **Quantum Angle Encoding:** Maps the continuous classical PCA features into a **4-qubit** quantum state via parameterized $R_y$ rotation gates.
4. **Variational Quantum Circuit (VQC):** The core learning engine uses **Strongly Entangling Layers** (sequences of single-qubit rotations $R_x, R_y, R_z$ and CNOT cascades) as the hidden weights of the network to capture complex, non-linear feature correlations.
5. **Measurement & Output:** Measures Pauli-Z expectation values across all qubits, then passes the resulting continuous values into a classical PyTorch `Linear` layer to output the final class probabilities.

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Quantum Framework | PennyLane (Xanadu) |
| Deep Learning | PyTorch |
| ML & Preprocessing | Scikit-learn (PCA) |
| Data Visualization | Matplotlib, Seaborn |

---

## 📊 Evaluation Metrics Summary

| Metric | Classical CNN Baseline | Proposed Hybrid QNN |
|---|:---:|:---:|
| Accuracy | 99.10% | 94.00% |
| Precision (Class 0) | 0.98 | 0.99 |
| Recall (Class 0) | 1.00 | 0.89 |
| F1-Score (Class 0) | 0.99 | 0.94 |
| Trainable Parameters | 1,610 | **34** |

---

## 💻 Installation & Setup

Follow these steps to set up your local environment.

### 1. Clone the Repository

```bash
git clone https://github.com/talluruchandrakanth/VariationalQuantumNeuralNetworks_ImageClassification
cd VariationalQuantumNeuralNetworks_ImageClassification
```

### 2. Create and Activate a Virtual Environment

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows (Command Prompt):**

```bat
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install torch torchvision pennylane scikit-learn matplotlib seaborn jupyter
```

---

## 🚀 How to Run

1. Launch the Jupyter environment:

   ```bash
   jupyter notebook
   ```

2. Open the notebook file: `Quantum Neural Networks (QNNs) for Image Classification.ipynb`.
3. Ensure your Jupyter kernel is linked to your active `.venv` environment.
4. Run the cells sequentially to execute data loading, PCA reduction, hybrid QNN training, classical CNN benchmarking, and metric visualization.

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.
