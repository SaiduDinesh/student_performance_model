# student_performance_model
AI-Based Student Performance Prediction System
This project uses machine learning techniques to predict student performance based on various factors including gender, parental education level, lunch type, test preparation, and subject scores. The dataset used is the "Students Performance in Exams" dataset from Kaggle.

# Dataset
Source: Students Performance in Exams - Kaggle

Size: 1000 records

Features:

Categorical: gender, race/ethnicity, parental level of education, lunch, test preparation course

Numerical: math score, reading score, writing score

Objective
The goal is to predict whether a student will pass or fail based on demographic and academic features. A "Passed" label is created by averaging the math, reading, and writing scores. If the average score is 60 or more, the student is labeled as passed.

Installation
Clone the repository:

git clone https://github.com/SaiduDinesh/student_performance_model.git
cd student-performance-prediction
Install dependencies:

pip install -r requirements.txt
Download the dataset:

from kaggle.api.kaggle_api_extended import KaggleApi

api = KaggleApi()
api.authenticate()
api.dataset_download_files("spscientist/students-performance-in-exams", path="./data", unzip=True)
Data Preprocessing
Created a new column Mean_Score as the average of math, reading, and writing scores.

Created a binary label Passed where 1 means average score ≥ 60, otherwise 0.

One-hot encoded categorical variables.

# Exploratory Data Analysis
Visualizations include:

Gender and parental education distributions

Score distributions per subject

Score trends based on lunch and test preparation

Correlation matrix among scores

Box plots by gender, parental education, and test preparation

# Models Evaluated
Model	Accuracy	Precision	Recall	F1 Score
Logistic Regression	0.72	0.74	0.90	0.81
Random Forest	0.70	0.73	0.90	0.81
Gradient Boosting	0.68	0.74	0.82	0.78
KNN	0.67	0.72	0.84	0.78

# Results
Logistic Regression and Random Forest performed the best with an F1 Score of 0.81.

Test preparation and parental education significantly influenced performance.

# File Structure
.
├── data/                         # Contains StudentsPerformance.csv
├── eda_visualizations.ipynb     # Notebook for EDA and plots
├── model_training.ipynb         # Model building and evaluation
├── requirements.txt             # List of required Python packages
├── README.md                    # Project documentation
License
This project is licensed under the MIT License.

# Credits
Dataset by Kaggle user spscientist

Built using Python, Pandas, Seaborn, Matplotlib, and Scikit-learn
