# 📧 Visual Analytics of Spam Detection Using BERT and Hybrid Deep Learning

## Overview

This project presents a comprehensive spam email detection framework that combines Natural Language Processing (NLP), Deep Learning, Machine Learning, and Visual Analytics techniques.

The system utilizes pre-trained BERT embeddings for textual feature extraction and combines them with numerical email features to build a hybrid spam classification model. Performance is evaluated against traditional machine learning approaches such as Support Vector Machines (SVM) and Logistic Regression.

In addition to classification, the project provides visual analytics for understanding spam behavior through word clouds, keyword frequency analysis, TF-IDF visualization, message length distributions, confusion matrices, and ROC curves.

---

## Objectives

* Detect spam emails with high accuracy.
* Extract semantic text representations using BERT.
* Combine textual and numerical features.
* Compare deep learning and traditional machine learning approaches.
* Analyze spam characteristics using visual analytics.
* Address class imbalance in spam datasets.

---

## Dataset

The project uses two datasets:

### Text Dataset

* Email message content
* Spam/Ham labels

### Numerical Dataset

* Engineered email features
* Metadata and frequency-based attributes

Target Label:

| Value | Class          |
| ----- | -------------- |
| 0     | Ham (Non-Spam) |
| 1     | Spam           |

---

## Methodology

### Data Preprocessing

* Missing value handling
* Dataset alignment
* Label extraction
* Numeric feature cleaning

### Text Embedding

Pre-trained BERT (`bert-base-uncased`) is used to generate contextual embeddings.

For each email:

1. Tokenization
2. Attention masking
3. CLS token extraction
4. 768-dimensional embedding generation

### Feature Fusion

The final feature vector is created by concatenating:

* BERT embeddings
* Numerical email features

This creates a hybrid representation containing semantic and statistical information.

---

## Hybrid MLP Architecture

Input Layer

↓

Dense Layer (512)

↓

ReLU Activation

↓

Dropout

↓

Dense Layer (128)

↓

ReLU Activation

↓

Dropout

↓

Output Layer

↓

Sigmoid Activation

---

## Handling Class Imbalance

The dataset exhibits class imbalance between spam and ham messages.

To mitigate this issue:

* BCEWithLogitsLoss is used.
* Positive class weighting is applied.
* Balanced Logistic Regression is evaluated.
* Balanced SVM configuration is used.

---

## Machine Learning Models Compared

### Hybrid MLP

* BERT + Numerical Features
* Deep Learning classifier

### Support Vector Machine (SVM)

* RBF Kernel
* Balanced class weights

### Logistic Regression

* Balanced class weights
* Maximum iterations = 2000

---

## Hyperparameter Tuning

Grid Search experiments were conducted using:

### Hidden Layer Sizes

* 256
* 512

### Second Layer Sizes

* 64
* 128

### Dropout Rates

* 0.2
* 0.3
* 0.5

Performance metrics:

* Accuracy
* F1 Score

---

## Evaluation Metrics

The following metrics are used:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC Score
* Confusion Matrix

---

## Visual Analytics

### 1. Spam vs Ham Distribution

Shows dataset imbalance and class proportions.

### 2. Message Length Analysis

Compares the distribution of message lengths between spam and legitimate emails.

### 3. Top Spam Keywords

Most frequently occurring terms in spam emails.

### 4. Word Clouds

Generated separately for:

* Spam Emails
* Ham Emails

### 5. TF-IDF Important Terms

Visualizes the most influential words across the dataset.

### 6. Confusion Matrix

Displays classification performance.

### 7. ROC Curve

Evaluates model discrimination capability.

### 8. Model Comparison

Compares:

* Hybrid MLP
* SVM
* Logistic Regression

---

## Technologies Used

* Python
* PyTorch
* Transformers (Hugging Face)
* Scikit-Learn
* Pandas
* NumPy
* Matplotlib
* WordCloud

---



## Results

The Hybrid MLP model demonstrated strong spam detection capability by leveraging:

* BERT semantic embeddings
* Numerical feature fusion
* Class imbalance correction

Comparative experiments show the effectiveness of deep contextual embeddings compared to traditional machine learning models.

---

This project is licensed under the MIT License.
