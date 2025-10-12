# 🌦️ Weather Temperature Prediction using Linear Regression

This project demonstrates how to predict **Temperature (°C)** from historical weather data using both **manual Gradient Descent** and **Scikit-learn Linear Regression**.  
It combines **data preprocessing, feature selection, model building, and visualization** into one complete machine learning workflow.

---

## 📘 Project Overview

The goal of this project is to:
- Explore the **weatherHistory.csv** dataset
- Identify **key features** that affect temperature
- Build a **Linear Regression model** using:
  1. **Manual Gradient Descent**
  2. **Sklearn’s LinearRegression**
- Compare both models’ performance using **MSE** and **R² Score**
- Visualize convergence, feature relationships, and predictions
- Predict temperature for **new unseen data**

---

## 🧠 Key Concepts Covered

- Data Cleaning & Feature Engineering  
- Correlation Analysis  
- Gradient Descent Implementation  
- Linear Regression with Scikit-learn  
- Model Evaluation (MSE, R² Score)  
- Data Visualization (Heatmap, Scatter Plots)  

---

## 🧩 Steps in the Project

### 1️⃣ Data Loading & Cleaning
- Loaded dataset `weatherHistory.csv`
- Handled missing values in `'Precip Type'`
- Converted `'Formatted Date'` to datetime format
- Extracted **year, month, and day** from dates
- Dropped irrelevant columns (`Summary`, `Daily Summary`, `Loud Cover`)
- Encoded categorical variables using **LabelEncoder**
- Removed duplicates and reset indices

### 2️⃣ Exploratory Data Analysis
- Plotted **correlation matrix** to find relationships between features  
- Selected top correlated features with **Temperature (C)**  
- Created **scatter plots** to visualize feature-target relationships  

### 3️⃣ Linear Regression using Gradient Descent
- Standardized the data  
- Implemented Gradient Descent manually using NumPy  
- Tracked **Mean Squared Error (MSE)** across epochs  
- Optimized model parameters (`θ`)  

### 4️⃣ Linear Regression using Sklearn
- Trained `LinearRegression()` model  
- Compared parameters, predictions, and evaluation metrics with manual Gradient Descent  

### 5️⃣ Model Evaluation
- Compared both models using:
  - **Mean Squared Error (MSE)**
  - **R² Score**
- Plotted:
  - MSE vs Epochs (to show convergence)
  - Actual vs Predicted Temperature (for both methods)

### 6️⃣ Predicting New Data
Predicted temperature for a new input:  
`Apparent Temperature = 70`, `Visibility = 10`

Both models provide close predictions, validating correctness.

---

## 📊 Visualizations
- **Heatmap** of feature correlations  
- **Scatter plots** of selected features vs Temperature  
- **MSE convergence curve** (Gradient Descent vs Sklearn)  
- **Actual vs Predicted Temperature** plots  

---

## 🧮 Results Summary

| Model | Train MSE | Test MSE | Train R² | Test R² |
|:------|-----------:|----------:|----------:|---------:|
| Gradient Descent | *≈ small value* | *≈ small value* | *≈ high value* | *≈ high value* |
| Sklearn Linear Regression | *≈ same as GD* | *≈ same as GD* | *≈ same as GD* | *≈ same as GD* |

✅ Both models achieve **similar performance**, proving the correctness of the manual implementation.

---


