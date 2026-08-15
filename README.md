# Neural Network Performance Analysis for Handwritten Digit Classification

## Overview

The objective of this analysis is to introduce and demonstrate the working of neural networks using the MNIST handwritten digit dataset.

MNIST contains **70,000 grayscale images** of digits 0–9, with each image having a resolution of **28 × 28 pixels**. The analysis focuses on understanding how different neural network configurations and hyperparameters affect **model learning, accuracy, and training time**.

## Dataset

The data is divided into **training, validation, and test sets**.

* **Dataset:** MNIST
* **Total Images:** 70,000
* **Image Type:** Grayscale
* **Image Resolution:** 28 × 28 pixels
* **Classes:** 10 (digits 0–9)

## Data Preprocessing

The following preprocessing steps are performed:

1. The data is divided into training, validation, and test sets.
2. Images are normalized from the original **0–255 pixel range to 0–1**.
3. Images are reshaped from **28 × 28 images into 784-dimensional vectors**.
4. Target labels are converted into **one-hot encoded representations** for the ten digit classes.

## Model Development

A sequence of neural network models is developed by varying:

* Number of epochs
* Batch size
* Number of hidden layers
* Number of neurons
* Activation functions
* Gradient descent methods

## Experiments and Observations

### 1. Baseline Model

The baseline model contains **no hidden layer** and uses **vanilla gradient descent**.

With **10 epochs**, it achieves only about **15% accuracy**.

### 2. Effect of Epochs

Increasing the number of epochs substantially improves model performance.

### 3. Effect of Batch Size

Using smaller batch sizes through **stochastic gradient descent** produces much faster learning.

### 4. Effect of Hidden Layers

Adding a hidden layer further improves performance when combined with an appropriate batch size.

### 5. Effect of Activation Functions

Experiments are conducted using:

* Sigmoid
* Tanh
* ReLU

The results show that **tanh and ReLU perform better than sigmoid** for this analysis.

### 6. Multiple Hidden Layers

Further experiments with additional hidden layers provide small improvements in performance.

## Final Results

The final **three-hidden-layer model using ReLU** achieves approximately **97–98% validation accuracy**.

However, increasing the epochs to **100** raises training accuracy to **100%** without significant improvement in validation accuracy.

This demonstrates the importance of balancing:

* Model complexity
* Training duration
* Generalization

## Conclusion

Overall, the analysis provides a practical understanding of how **neural network architecture and hyperparameters influence learning performance**.

The experiments demonstrate how changes in epochs, batch size, hidden layers, neurons, activation functions, and optimization approaches can affect the learning, accuracy, and training behavior of a neural network.

## Key Learnings

* Understanding the working of neural networks using the MNIST dataset.
* Understanding data normalization and reshaping.
* Understanding one-hot encoding for multi-class classification.
* Analyzing the effect of epochs and batch size.
* Comparing different activation functions.
* Understanding the effect of hidden layers and neurons.
* Analyzing training accuracy versus validation accuracy.
* Understanding the importance of model complexity and generalization.
