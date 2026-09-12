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


🤖 Machine Learning Models

This project implements and compares 13 regression algorithms.

1. Linear Regression

Linear Regression models the relationship between input features and the target using a linear equation.

Use: Good baseline model for approximately linear relationships.

2. Robust Regression

The project uses HuberRegressor.

Robust Regression is designed to reduce the influence of outliers.

Use: Useful when unusual observations may affect ordinary regression.

3. Ridge Regression

Ridge Regression is Linear Regression with L2 regularization.

Use: Helps reduce overfitting and handles correlated features better than ordinary Linear Regression.

4. Lasso Regression

Lasso Regression uses L1 regularization.

Use: Helps control model complexity and can reduce some feature coefficients toward zero.

🏆 Best Overall Model in Current Experiment

Lasso Regression

R² ≈ 0.9146

5. ElasticNet

ElasticNet combines the ideas of L1 and L2 regularization.

Use: Useful when a balance between Lasso and Ridge regularization is desired.

6. Polynomial Regression

Polynomial Regression extends linear regression by creating polynomial features.

The current implementation uses:

PolynomialFeatures(degree=4)

Use: Helps capture non-linear relationships between features and target.

7. SGD Regressor

SGD Regressor uses Stochastic Gradient Descent for optimization.

Use: Can be useful for large-scale datasets and iterative optimization.

8. Artificial Neural Network

The project uses:

MLPRegressor(
    hidden_layer_sizes=(100,),
    max_iter=1000
)

Use: Neural networks can learn complex non-linear relationships.

9. Random Forest

Random Forest combines predictions from multiple decision trees.

Use: Powerful general-purpose algorithm for structured/tabular data.

10. Support Vector Regression

The project uses SVR.

SVR applies the Support Vector Machine concept to regression problems.

Use: Can model complex relationships between input variables and continuous targets.

11. LightGBM

LightGBM is a gradient boosting algorithm based on decision trees.

Use: Efficient and powerful for structured/tabular datasets.

12. XGBoost

XGBoost is another gradient boosting algorithm that builds trees sequentially to improve previous predictions.

Use: Frequently used for high-performance tabular Machine Learning.

13. KNN Regression

KNN Regression predicts a target using nearby observations.

Use: Useful when similar observations tend to have similar target values.

📈 Model Evaluation

Every model is evaluated using three metrics:

MAE — Mean Absolute Error

Measures the average absolute difference between actual and predicted values.

Lower MAE = Better

MSE — Mean Squared Error

Measures the average squared prediction error.

Lower MSE = Better

Large errors receive more penalty because the errors are squared.

R² — R-Squared

Measures how well the model explains the variation in the target variable.

Higher R² = Better

🏆 Model Comparison

Current evaluation results:

Model	R²	Performance
Lasso Regression	~0.9146	🏆 Best Overall
Linear Regression	~0.9146	Excellent
Ridge Regression	~0.9146	Excellent
LightGBM	~0.8940	Very Good
Random Forest	~0.8789	Very Good
ElasticNet	~0.8780	Good
XGBoost	~0.8710	Good
Polynomial Regression	~0.8710	Good
KNN	~0.5114	Moderate
ANN	~0.5033	Moderate
Robust Regression	~0.5011	Moderate
SVR	~0.0004	Poor
SGD Regressor	~-1.2223	Poor
Best Model

Lasso Regression

R² ≈ 0.9146

The result demonstrates an important Machine Learning principle:

A more complex algorithm is not automatically better. Model selection should be based on evaluation results.

🧠 Key Learning from Model Comparison

One of the interesting observations from this project was that the simpler linear and regularized regression models performed better than several more complex algorithms.

Lasso, Linear Regression, and Ridge Regression achieved the strongest results on this particular dataset and train-test split.

This demonstrates why Machine Learning practitioners should:

Compare multiple algorithms
Use appropriate evaluation metrics
Avoid assuming complex models are always superior
Select models based on validation performance
🌐 Flask Deployment

The project includes a Flask web application.

The application loads the trained Pickle models and allows users to select a model and provide housing information.

User Inputs
Average Area Income
Average Area House Age
Average Area Number of Rooms
Average Area Number of Bedrooms
Area Population

The Flask backend converts the submitted values into a Pandas DataFrame and passes them to the selected trained model.

The predicted house price is then displayed to the user.

💾 Model Serialization

After training, every model is saved using Pickle.

Example:

with open(f'{name}.pkl', 'wb') as f:
    pickle.dump(model, f)

This allows the trained models to be reused without retraining them every time the Flask application starts.

🗂️ Project Structure
MLPROJECT/
│
├── app.py
├── models.py
├── model_evaluation_results.csv
│
├── LinearRegression.pkl
├── RobustRegression.pkl
├── RidgeRegression.pkl
├── LassoRegression.pkl
├── ElasticNet.pkl
├── PolynomialRegression.pkl
├── SGDRegressor.pkl
├── ANN.pkl
├── RandomForest.pkl
├── SVM.pkl
├── LGBM.pkl
├── XGBoost.pkl
├── KNN.pkl
│
├── templates/
│   ├── index.html
│   ├── model.html
│   └── results.html
│
└── README.md
🛠️ Technologies Used
Programming Language
Python
Data Processing
Pandas
Machine Learning
Scikit-learn
LightGBM
XGBoost
Model Evaluation
MAE
MSE
R²
Deployment
Flask
Model Persistence
Pickle
Frontend
HTML
Flask Templates
📦 Installation

Clone the repository:

git clone YOUR_GITHUB_REPOSITORY_URL

Move into the project directory:

cd MLPROJECT

Create a virtual environment:

python -m venv venv

Activate the virtual environment on Windows:

venv\Scripts\activate

Install the required packages:

pip install pandas scikit-learn flask lightgbm xgboost
▶️ Running the Project
Step 1 — Train the models

Run:

python models.py

This will:

Load the dataset
Prepare the features and target
Split the dataset
Train all 13 models
Generate predictions
Calculate MAE, MSE and R²
Save the trained models as .pkl
Save evaluation results to model_evaluation_results.csv
Step 2 — Start Flask

Run:

python app.py

The Flask application will start locally.

Open the local Flask address shown in the terminal, usually:

http://127.0.0.1:5000/
💡 Example Prediction Workflow
User enters:

Average Area Income
Average Area House Age
Average Area Number of Rooms
Average Area Number of Bedrooms
Area Population

        ↓

Select ML Model

        ↓

Flask Backend

        ↓

Selected Pickle Model

        ↓

Prediction

        ↓

Estimated House Price


📌 Project Highlights

✅ End-to-end Machine Learning project

✅ Regression-based housing price prediction

✅ 13 different ML algorithms compared

✅ MAE, MSE and R² evaluation

✅ Best model identified from actual evaluation results

✅ Model serialization using Pickle

✅ Flask-based prediction application

✅ Multiple model selection through web interface

✅ Clear separation between model training and application deployment

🔮 Future Improvements

The project can be further improved by adding:

Feature scaling using StandardScaler for scale-sensitive models
K-Fold Cross-Validation
Hyperparameter tuning
Automated best-model selection
Feature importance analysis
Prediction confidence / uncertainty analysis
Data visualization dashboard
Improved input validation
Model versioning
Cloud deployment
REST API endpoint
Automated retraining pipeline


🎓 Key Skills Demonstrated

Through this project, I practiced:

Python | Pandas | Scikit-learn | Regression | Model Evaluation | Ensemble Learning | Neural Networks | XGBoost | LightGBM | Flask | Pickle | Machine Learning Deployment

👨‍💻 Author

Pavan Kumar Torlapati

Python Developer | Machine Learning | Generative AI | Agentic AI
