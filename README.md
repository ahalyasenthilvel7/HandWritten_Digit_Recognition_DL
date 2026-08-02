#  Handwritten Digit Recognition using Deep Learning

## 📌 Project Overview

This project develops a **Handwritten Digit Recognition System** using **Artificial Neural Networks (ANNs)** implemented with **TensorFlow/Keras**. The objective is to accurately classify handwritten digits (0–9) from the **MNIST dataset** by systematically designing, training, and evaluating multiple neural network architectures.

Rather than building a single model, this project follows an **experimental approach** in which several neural network configurations are developed and compared to understand how different hyperparameters and architectural choices influence classification performance.

The project begins with **data exploration**, followed by **data preprocessing**, including normalization, reshaping the images into feature vectors, and one-hot encoding of the target labels. The processed dataset is then used to train a series of neural network models.

A total of **14 ANN models (Model 0 to Model 13)** are implemented by progressively modifying important hyperparameters such as:

* Number of training epochs
* Batch size
* Optimizer strategy (Vanilla Gradient Descent and Stochastic Gradient Descent)
* Number of hidden layers
* Number of neurons
* Activation functions

Each model is evaluated using **training accuracy, validation accuracy, loss curves, execution time, and prediction performance**. The results of every experiment are analyzed to understand how each architectural modification affects learning and model generalization.

Based on the experimental comparison, **Model 10** is selected as the **best-performing model** because it achieved the highest validation accuracy while maintaining good generalization performance.

The selected model is then rebuilt and used to predict handwritten digits from both the original MNIST images and inverted images (white background with black digits), demonstrating the model's capability to classify handwritten digits under different input representations.

---

## 🎯 Objectives

* Develop an Artificial Neural Network (ANN) for handwritten digit recognition.
* Perform exploratory analysis of the MNIST dataset.
* Preprocess image data for neural network training.
* Compare multiple ANN architectures using different hyperparameters.
* Study the effect of epochs, batch size, optimizer, hidden layers, neurons, and activation functions.
* Evaluate model performance using training and validation metrics.
* Identify the best-performing neural network architecture.
* Predict handwritten digits using the trained model.

---

## 📂 Dataset

**Dataset:** MNIST Handwritten Digit Dataset

The dataset consists of grayscale handwritten digit images belonging to ten classes (0–9).

### Training Dataset

* **60,000 images**
* Image size: **28 × 28 pixels**

### Testing Dataset

* **10,000 images**
* Image size: **28 × 28 pixels**

Each image is converted into a **784-dimensional feature vector** before being used as input to the neural network.

---

## 🔍 Exploratory Data Analysis

The notebook performs the following analyses:

* Dataset overview
* Visualization of handwritten digit images
* Class distribution analysis
* Pixel value visualization
* Dataset shape inspection
* Image dimension analysis

The analysis confirms that the dataset contains balanced handwritten digit classes suitable for multi-class classification.

---

## 🧹 Data Preprocessing

The following preprocessing steps are performed before training:

* Normalize pixel values from **0–255** to **0–1**
* Reshape images from **28 × 28** to **784 features**
* One-hot encode target labels
* Split the data into training and validation datasets
* Prepare the data for ANN training

---

## 🧠 Model Development

The project progressively develops multiple ANN models to study the effect of different hyperparameters.

### Model 0

* No hidden layer
* Vanilla Gradient Descent
* 10 epochs

Purpose:

* Establish a baseline model.

---

### Model 1

* Increased number of epochs
* Vanilla Gradient Descent

Observation:

* Accuracy improved compared to the baseline model.

---

### Model 2

* Stochastic Gradient Descent
* Smaller batch size

Observation:

* Faster learning
* Significant improvement in accuracy

---

### Model 3

* Increased epochs
* SGD optimizer

Observation:

* Small improvement in accuracy
* Longer training time

---

### Model 4

* Increased batch size

Observation:

* Reduced training time
* Slight reduction in accuracy

---

### Model 5

* Added one hidden layer
* Sigmoid activation

Observation:

* Performance did not improve significantly.

---

### Model 6

* One hidden layer
* Smaller batch size
* SGD optimizer

Observation:

* Best performance achieved so far.
* Hidden layer becomes effective when combined with SGD.

---

### Model 7

* Increased hidden neurons

Observation:

* Minimal improvement.

---

### Model 8

* Hidden layer with **tanh** activation

Observation:

* Better performance than sigmoid.

---

### Model 9

* Hidden layer with **ReLU** activation

Observation:

* Slight improvement over previous models.

---

### Model 10 (Best Model)

Architecture:

* Hidden Layer 1 → **128 neurons (ReLU)**
* Hidden Layer 2 → **64 neurons (tanh)**
* Output Layer → **Softmax**

Training Parameters:

* Epochs: **50**
* Batch Size: **32**
* Optimizer: **SGD**

This model achieved the **highest validation accuracy** among all experiments.

---

### Model 11

* Reversed activation order
* tanh → ReLU

Observation:

* Very little difference in performance.

---

### Model 12

* Three hidden layers
* ReLU activation

Observation:

* Slight improvement.

---

### Model 13

* Increased training epochs to 100

Observation:

* Training accuracy reached nearly 100%.
* Validation accuracy showed only marginal improvement.
* Training time increased considerably.
* Signs of overfitting were observed.

---

## 📊 Hyperparameter Analysis

The project experimentally studies the influence of:

* Number of epochs
* Batch size
* Optimizer
* Hidden layers
* Hidden neurons
* Activation functions

instead of selecting them arbitrarily.

---

## 🏆 Best Performing Model

According to the validation accuracy, **Model 10** is selected as the final model.

### Model Architecture

* Hidden Layer 1 → 128 neurons (ReLU)
* Hidden Layer 2 → 64 neurons (tanh)
* Output Layer → Softmax

### Training Configuration

* Optimizer → SGD
* Epochs → 50
* Batch Size → 32

This configuration provides the best balance between learning capability and generalization.

---

## 🔢 Prediction

The final model is used to predict:

* Random handwritten digits from the MNIST test dataset.
* Inverted handwritten digit images (white background with black digits).

The notebook also displays:

* Original image
* Pixel values
* Predicted digit
* Actual digit

to verify prediction performance.

---

## 📈 Key Findings

The experimental analysis leads to the following observations:

* Increasing the number of epochs improves learning up to a certain point, after which improvements become marginal while training time increases.
* Stochastic Gradient Descent (SGD) performs better than Vanilla Gradient Descent because model parameters are updated more frequently.
* Reducing the batch size improves learning efficiency and classification accuracy.
* Simply adding hidden layers does not guarantee better performance; the choice of optimizer and batch size also plays a significant role.
* ReLU and tanh activation functions outperform sigmoid for this classification problem.
* Increasing the number of neurons beyond an optimal level provides only limited improvement.
* Excessive training epochs can lead to overfitting without meaningful gains in validation accuracy.
* The combination of **two hidden layers, ReLU and tanh activations, SGD optimizer, 50 epochs, and batch size 32** provides the best overall performance.

---

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

---

## 📌 Conclusion

This project presents a systematic study of **Artificial Neural Networks for handwritten digit recognition** rather than focusing on a single model. Through a series of controlled experiments, different neural network architectures and hyperparameters are compared to understand their impact on model performance.

The experimental results demonstrate that **network architecture, optimizer selection, batch size, activation functions, and training epochs collectively influence classification accuracy**. Among all the evaluated models, **Model 10** provides the best balance between learning capability, validation accuracy, and generalization, making it the most suitable architecture for handwritten digit recognition on the MNIST dataset.
