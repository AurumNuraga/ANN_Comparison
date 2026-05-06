
# ANN Model Comparison Before and After Image Preprocessing and Augmentation for Pneumonia Detection

This repository contains a Python notebook (`train_comparison.ipynb`) that compares various training strategies for Convolutional Neural Networks (CNN) to detect pneumonia from chest X-ray images.

## Table of Contents

- Dataset Description
- Data Preprocessing
- ANN Architecture Used
- Data Augmentation Techniques
- Training Strategies:
  - ANN Without preprocessing and augmentation
  - ANN With preprocessing and augmentation
  - Comparison with custom CNN
- Model Evaluation
- Performance Visualization
- Save and Load Models

---

## Dataset

The dataset used is `pneumonia_mnist`, a subset of MedMNIST, consisting of low-resolution grayscale images (28x28 pixels) classified as:
- **0**: Normal
- **1**: Pneumonia

Data split:
- **Training**: 800 data
- **Validation**: 200 data
- **Testing**: 100 data

---

## Installation

Make sure Python is installed, then install the following libraries:

```bash
pip install tensorflow tensorflow-datasets matplotlib
```

---

## How to Run

1. Open the `train_comparison.ipynb` file in Jupyter Notebook or VSCode.
2. Run all cells to process data, train, and evaluate models.
3. The best model will be automatically saved using `ModelCheckpoint`.

---

## Model Architecture

The ANN model used consists of:
- Flatten
- Dense
- ReLU and sigmoid activation functions for binary classification

Each experiment uses the same architecture but differs in the preprocessing and augmentation sections.

---

## Training Strategies

### 1. Without Preprocessing and Augmentation
Model is trained directly with raw data without any preprocessing and augmentation techniques.

### 2. Preprocessing
Adding preprocessing techniques such as:
- Black and White
- Central Crop

### 3. Light Augmentation
Adding light transformations such as:
- Horizontal flip
- Small translation
- Small zoom

---

## Evaluation & Visualization

Each model is evaluated using:
- Accuracy and loss on validation data
- Plot accuracy and loss curves during training

<img width="1222" height="605" alt="download (7)" src="https://github.com/user-attachments/assets/a05d9b9f-8e16-474c-b14a-8d052ef09869" />

---

## Saving & Loading Models

The best model from each strategy is saved in `.h5` format. The notebook also supports reloading these models for further evaluation or prediction.

---

## Results

The notebook displays a visual comparison between models based on accuracy and loss performance. The main objective is to find the best training strategy for accurate pneumonia classification on X-ray images.

---
