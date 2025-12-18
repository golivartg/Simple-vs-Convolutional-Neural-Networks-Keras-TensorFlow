# Simple & Convolutional Neural Networks (MNIST) 🧠

This project explores image classification using the **MNIST dataset** (Handwritten Digits). It implements and compares two different Deep Learning approaches using **Keras** and **TensorFlow**: a simple Artificial Neural Network (ANN) versus a Convolutional Neural Network (CNN).

## 📋 Project Overview

The goal is to correctly classify grayscale images (28x28 pixels) of handwritten digits (0-9).

### 1. Simple ANN (Dense Network)
* **Approach:** Flattens the 2D image into a 1D vector (784 pixels) and passes it through fully connected layers.
* **Architecture:** `Flatten` -> `Dense (ReLU)` -> `Dense (Softmax)`.
* **Pros:** Fast to train, simple structure.
* **Cons:** Loses spatial information (doesn't "see" shapes/patterns).

### 2. CNN (Convolutional Neural Network)
* **Approach:** Treats the input as a 2D image, applying filters to detect visual patterns (edges, curves) before classification.
* **Architecture:** `Conv2D` -> `MaxPooling2D` -> `Flatten` -> `Dense`.
* **Pros:** Captures spatial hierarchies, achieves higher accuracy.

## 🛠️ Tech Stack

* **Python 3**
* **TensorFlow / Keras** (Deep Learning)
* **NumPy** (Data manipulation)
* **Matplotlib** (Visualization of predictions and errors)
* **Jupyter Notebook**

## 📈 Performance Analysis

We evaluated both models using the test dataset (10,000 unseen images).

| Model Architecture | Test Accuracy | Model Complexity | Training Speed |
| :--- | :---: | :---: | :---: |
| **Simple ANN** (Dense) | ~96.69% | 🟢 Low | ⚡ Very Fast |
| **CNN** (Conv2D) | **~98.62%** | 🟠 Medium | 🐢 Slower |

### Key Observations
1.  **Spatial Awareness:** The **Simple ANN** treats the image as a flat list of pixels (784 numbers), losing all spatial relationships. If a digit is shifted slightly to the left, the ANN might get confused.
2.  **Feature Extraction:** The **CNN** uses filters to detect shapes (edges, loops, curves) regardless of their position in the image. This makes it much more robust to variations in handwriting.
3.  **The "2%" Gap:** While 96% sounds high, in a dataset of 10,000 images, the ANN fails on ~250 images, whereas the CNN only fails on ~90. That's a **significant reduction in error rate**.

## 🏁 Conclusion

This project demonstrates the significant advantage of using **Convolutional Neural Networks (CNN)** for image classification tasks. While the simple Dense Network (ANN) performed surprisingly well (~96%), the CNN achieved superior accuracy (~98%) by leveraging spatial data through **filters and pooling layers**. 

This confirms that for visual data, preserving the 2D structure is crucial for minimizing error rates and building robust models.
