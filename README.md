Project made by me for my AI class during the 3rd course in university. 

# Human Activity Recognition using Machine Learning
## Project overview

This project focuses on **Human Activity Recognition (HAR)** using data from smartphone sensors (accelerometer and gyroscope).

The goal is to classify human activity into one of six classes:

* Walking
* Walking Upstairs
* Walking Downstairs
* Sitting
* Standing
* Laying

The project compares different machine learning approaches and analyzes their performance.

---

## Dataset

The dataset contains sensor signals collected from **30 participants** using smartphones at a frequency of **50 Hz**.

Features were extracted from:

* Accelerometer (tAcc-XYZ)
* Gyroscope (tGyro-XYZ)

Signal processing steps include:

* Noise filtering (median + Butterworth filter)
* Separation of body and gravity acceleration
* Feature extraction (mean, std, energy, entropy, etc.)
* Frequency domain transformation (FFT)

---

## Methods

### k-Nearest Neighbors (kNN)

* Metrics tested:

  * Euclidean
  * Manhattan
  * Chebyshev
* Hyperparameters:

  * Number of neighbors (k = 1…30)
  * Algorithm: brute, kd_tree

### Support Vector Machine (SVM)

* Strategies:

  * One-vs-One (OvO)
  * One-vs-Rest (OvR)

* Kernels:

  * Linear
  * RBF
  * Polynomial

### Hyperparameter Optimization

* GridSearchCV used for automatic tuning
* Evaluation metric: F1-score (weighted)

---

## Results

### ✅ Best kNN model:

* Metric: Manhattan
* Neighbors: k = 14
* F1-score: 0.91
* Accuracy: 0.91

### ✅ Best SVM model:

* Strategy: One-vs-One
* Kernel: Linear
* F1-score: 0.96
* Accuracy: 0.96

SVM outperformed kNN, likely due to better handling of high-dimensional data.

---

## Evaluation

Models were evaluated using:

* Accuracy
* F1-score (weighted)
* Precision / Recall
* Confusion Matrix

---

## Tech Stack

* Python
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

---

## Project Structure

```id="proj123"
.
├── notebooks/
│   └── activity_recognition.ipynb
├── data/
├── README.md
└── requirements.txt
```

---



## Key insights

* Feature scaling is critical for kNN performance
* Manhattan distance performed better than Euclidean
* SVM with linear kernel achieved the best overall results
* Data is close to linearly separable

---

Future improvements: try deep learning models (LSTM, CNN), perform feature selection, use raw time-series instead of engineered features, deploy as a real-time mobile application.
