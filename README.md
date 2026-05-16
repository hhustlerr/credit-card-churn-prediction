# Credit Card Churn Prediction

## Overview

This project focuses on predicting whether a customer will leave a bank’s credit card service using Artificial Neural Networks (ANN) built with TensorFlow and Keras. The model is trained on customer demographic and banking-related features to classify customers as either retained or churned.

The project demonstrates the complete Machine Learning workflow:

* Data loading and preprocessing
* Feature engineering
* Data scaling
* ANN model building
* Model training and evaluation
* Performance visualization

---

# Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* TensorFlow / Keras
* Matplotlib

---

# Dataset

The dataset used in this project contains customer banking information such as:

* Credit Score
* Geography
* Gender
* Age
* Tenure
* Balance
* Number of Products
* Has Credit Card
* Is Active Member
* Estimated Salary

### Target Variable

* `Exited`

  * `1` → Customer churned
  * `0` → Customer retained

---

# Project Workflow

## 1. Data Preprocessing

### Steps Performed

* Removed unnecessary columns:

  * `RowNumber`
  * `CustomerId`
  * `Surname`

* Checked:

  * Missing values
  * Duplicate entries
  * Class distribution

* Converted categorical columns into numerical format using One-Hot Encoding:

  * Geography
  * Gender

---

## 2. Train-Test Split

The dataset was divided into:

* 80% Training Data
* 20% Testing Data

Using:

```python
train_test_split()
```

---

## 3. Feature Scaling

Feature scaling was performed using:

```python
StandardScaler
```

This helps improve ANN training efficiency and convergence.

---

# Artificial Neural Network (ANN)

## Model Architecture

The ANN model consists of:

### Input Layer

* 11 neurons
* Sigmoid activation

### Hidden Layer

* 11 neurons
* ReLU activation

### Output Layer

* 1 neuron
* Sigmoid activation

---

## Model Compilation

```python
model.compile(
    loss='binary_crossentropy',
    optimizer='Adam',
    metrics=['accuracy']
)
```

---

## Model Training

The model was trained using:

```python
model.fit(
    x_train_scaled,
    y_train,
    epochs=100,
    validation_split=0.2
)
```

---

# Model Evaluation

The model predictions were generated on test data and converted into binary outputs using a threshold of 0.5.

## Accuracy Evaluation

```python
accuracy_score(y_test, y_pred)
```

---

# Visualization

Training performance was visualized using Matplotlib:

* Training Loss
* Validation Loss
* Training Accuracy
* Validation Accuracy

These graphs help analyze:

* Overfitting
* Underfitting
* Model convergence

---

# Folder Structure

```bash
credit-card-churn-prediction/
│
├── credit-card-churn-prediction.ipynb
├── README.md
└── dataset/
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/credit-card-churn-prediction.git
cd credit-card-churn-prediction
```

---

## Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

---

# Run the Project

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Then run:

```bash
credit-card-churn-prediction.ipynb
```

---

# Future Improvements

Possible enhancements:

* Hyperparameter tuning
* Dropout layers to reduce overfitting
* Using advanced optimizers
* Trying different architectures
* Model deployment using Flask or Streamlit
* Adding ROC-AUC evaluation

---

# Learning Outcomes

This project helps in understanding:

* Data preprocessing for ML
* Feature scaling techniques
* ANN architecture design
* Binary classification problems
* Deep Learning workflow using TensorFlow/Keras

---

# Author

Prachi Mittal

---

# License

This project is open-source and available under the MIT License.
