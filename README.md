# binary_classifier

---

# Neural Network for Binary Image Classification

This project implements a **fully-connected feedforward neural network** from scratch to classify images as **Cat** or **Dog**.
The implementation covers **forward propagation, loss computation, backpropagation, and parameter updates** — without relying on deep learning libraries.

---

## Project Overview

* Input: Preprocessed images flattened into **12,000 features** (pixel intensity values).
* Task: Binary classification →

  * **0 → Cat**
  * **1 → Dog**
* Framework: Implemented in **Python (NumPy)** inside a Jupyter Notebook (`binary_classifier.ipynb`).

---

## Network Architecture

**Input Layer**

* 12,000 features (flattened image pixels).

**Hidden Layer 1**

* 5 neurons
* Fully connected, **ReLU activation**
* Learns low-level patterns

**Hidden Layer 2**

* 7 neurons
* Fully connected, **ReLU activation**
* Learns higher-level patterns

**Output Layer**

* 1 neuron, **Sigmoid activation**
* Outputs probability:

  $$
  \hat{y} = \sigma(z) = \frac{1}{1 + e^{-z}}
  $$
* Interpretation:

  * **0 → Cat**
  * **1 → Dog**

---

## Loss Function

We use **Binary Cross-Entropy (Log Loss):**

$$
J = -\frac{1}{m} \sum_{i=1}^{m} \Big[ y^{(i)} \log(\hat{y}^{(i)}) + (1 - y^{(i)}) \log(1 - \hat{y}^{(i)}) \Big]
$$

Where:

* $m$ = number of training samples
* $y^{(i)}$ = actual label (0 or 1)
* $\hat{y}^{(i)}$ = predicted probability

---

## Training Workflow

1. **Forward Propagation** → compute activations layer by layer.
2. **Loss Computation** → Binary Cross-Entropy.
3. **Backward Propagation** → compute gradients with the chain rule.
4. **Parameter Update** → update weights & biases with Gradient Descent.
5. **Repeat** → until convergence (epochs).

---

## Forward & Backward Pass

* **Forward Pass:**

  * Input → Hidden Layer 1 (ReLU) → Hidden Layer 2 (ReLU) → Output (Sigmoid).
* **Backpropagation:**

  * Start from output error → propagate backward → compute gradients for each weight.

---

## License

This project is open-source under the **MIT License**.

---
