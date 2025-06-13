# 📧 Email Spam Classification using Logistic Regression

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Logistic Regression](https://img.shields.io/badge/Model-Logistic%20Regression-brightgreen)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A machine learning project to classify emails as **Spam** or **Ham (Not Spam)** using a Logistic Regression model with Sci-kit Learn.

---

## 📅 Table of Contents

* 🌎 [Project Overview](#project-overview)
* 📋 [Dataset](#dataset)
* 🛠️ [Workflow](#workflow)
* 🧠 [Model and Tuning](#model-and-tuning)
* 🎯 [Evaluation Metrics](#evaluation-metrics)
* 📈 [Visualizations](#visualizations)
* 🍿 [How to Run](#how-to-run)
* ✅ [License](#license)


---

## 🌎 Project Overview

This project implements a supervised classification system to identify spam emails using a logistic regression model. Key ML techniques like **feature scaling**, **train-test splitting**, and **hyperparameter tuning** have been applied.

---

## 📋 Dataset

* Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/spambase)
* Contains **57 numerical features** per email.
* Target label: `1` = Spam, `0` = Ham

---

## 🛠️ Workflow

1. **Exploratory Data Analysis** – Analysed the dataset.
2. **Train-Test Splitting** – Stratified splitted the dataset into training and testing parts to maintain spam/ham ratio.
3. **Pipelining** – Scaling + LogisticRegression.
4. **Hyperparameter Tuning** – Via GridSearchCV.
5. **Evaluation** – Priority was given to Ham precision, making sure no Ham email lands in spam.

---

## 🧠 Model and Tuning

* **Model Used**: Logistic Regression
* **Penalty**: L2 
* **Solver**: `saga`
* **Hyperparameters Tuned**:

  * `class_weight` to prioritise Ham precision
  * `C` (inverse of regularization strength)

```python
param_grid = {
    'model__class_weight': [{0:v, 1:1} for v in [1,2,3,5]],
    'model__C': [0.01, 0.1, 1, 10, 100]
}
```

* **Scoring**: Custom based on `precision` for ham.

---

## 🎯 Evaluation Metrics

```text
Classification Report on test set:

              precision    recall  f1-score   support

         0.0       0.91      0.95      0.93       558
         1.0       0.92      0.85      0.88       362

    accuracy                           0.91       920
   macro avg       0.91      0.90      0.91       920
weighted avg       0.91      0.91      0.91       920
```

---

## 📈 Visualizations

![Confusion Matrix](images/Confusion%20Matrix.png)


![ROC Curve](images/ROC%20Curve.png)

---

## 🍿 How to Run

```bash
# Clone this repo
$ git clone https://github.com/ApurvSardana/Email-Spam-Classifier.git
$ cd Email-Spam-Classifier

```

---

## ✅ License

This project is licensed under the MIT License. Feel free to use, modify, and share.

---

<h2 align="center">Created with ❤️ by Apurv Sardana. See You Again 😊</h2>

