# 🏠 USA Housing Price Prediction — Multi-Model Machine Learning

An end-to-end Machine Learning project that predicts USA housing prices using multiple regression algorithms and provides a Flask-based web application for real-time prediction.

The project benchmarks 13 different regression models and compares their performance using MAE, MSE, and R².

---

## 🚀 Project Overview

The goal of this project is to predict the price of a house based on important housing and population-related features.

Instead of relying on a single Machine Learning algorithm, this project trains and evaluates 13 regression models and compares their performance.

The best-performing model in the current experiment is **Lasso Regression**, achieving an R² score of approximately **0.915**.

The trained models are serialized using Pickle and integrated into a Flask web application, allowing users to select a model and generate a housing-price prediction.

---

## 🎯 Problem Statement

Housing prices depend on multiple factors such as income, house age, number of rooms, number of bedrooms, and population.

The objective is to build a Machine Learning system that can learn the relationship between these features and house prices and provide predictions for new input data.

This is a:

**Supervised Learning → Regression Problem**

because the target variable, house price, is a continuous numerical value.

---

## 📊 Dataset

Dataset:

**USA Housing Dataset**

### Input Features

| Feature | Description |
|---|---|
| Avg. Area Income | Average income of the area |
| Avg. Area House Age | Average age of houses in the area |
| Avg. Area Number of Rooms | Average number of rooms |
| Avg. Area Number of Bedrooms | Average number of bedrooms |
| Area Population | Population of the area |

### Target

**Price**

The `Address` column is excluded from model training.

---

# 🔬 Machine Learning Workflow

```text
USA Housing Dataset
        ↓
Data Loading
        ↓
Data Preprocessing
        ↓
Feature / Target Separation
        ↓
Train-Test Split
        ↓
Train 13 Regression Models
        ↓
Generate Predictions
        ↓
Evaluate Models
        ↓
MAE / MSE / R²
        ↓
Compare Models
        ↓
Select Best Model
        ↓
Save Models using Pickle
        ↓
Flask Deployment
        ↓
User Input
        ↓
Housing Price Prediction
