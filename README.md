# Student Performance Predictor

## Overview

A comprehensive machine learning project that predicts student math scores using demographic and academic features. The system implements a complete MLOps pipeline from data ingestion to model deployment with a user-friendly web interface.

## Features

- **End-to-End ML Pipeline**: Complete workflow from data ingestion to model deployment
- **Multiple Algorithm Comparison**: Tests 7 different regression algorithms with hyperparameter tuning
- **Real-time Predictions**: Flask web application for instant score predictions
- **Automated Model Selection**: Automatically selects the best performing model based on R² score
- **Data Preprocessing**: Handles categorical encoding and feature scaling
- **Modular Architecture**: Well-structured codebase with separate components for each pipeline stage

## Project Structure

student_performance/
├── artifacts/ # Stored models and preprocessors
├── src/
│ ├── components/ # Core ML components
│ │ ├── data_ingestion.py
│ │ ├── data_transformation.py
│ │ └── model_trainer.py
│ ├── pipeline/ # Prediction pipeline
│ │ └── predict_pipeline.py
│ ├── exception.py # Custom exception handling
│ ├── logger.py # Logging configuration
│ └── utils.py # Utility functions
├── templates/ # HTML templates for web app
├── app.py # Flask application
└── requirements.txt # Dependencies

## Machine Learning Pipeline

### Data Ingestion

- Loads student performance dataset
- Splits data into training (80%) and testing (20%) sets
- Saves processed datasets to artifacts folder

### Data Transformation

- Handles categorical variables (gender, ethnicity, education level, etc.)
- Applies feature scaling using StandardScaler
- Creates preprocessing pipeline for consistent data transformation

### Model Training

The system evaluates multiple regression algorithms:

- **Random Forest Regressor**
- **Decision Tree Regressor**
- **Gradient Boosting Regressor**
- **Linear Regression**
- **XGBoost Regressor**
- **CatBoost Regressor**
- **AdaBoost Regressor**

Each model undergoes hyperparameter tuning using GridSearchCV to find optimal parameters.

### Model Selection

- Automatically selects the best performing model based on R² score
- Requires minimum R² score of 0.6 for model acceptance
- Saves the best model for production use

## Input Features

- **Gender**: Male/Female
- **Race/Ethnicity**: Student's ethnic background
- **Parental Level of Education**: Education level of parents
- **Lunch**: Standard or free/reduced lunch
- **Test Preparation Course**: Completed or not completed
- **Reading Score**: Student's reading test score
- **Writing Score**: Student's writing test score

## Output

- **Math Score Prediction**: Predicted math test score (0-100)

## Technologies Used

- **Python 3.x**
- **Scikit-learn**: Machine learning algorithms and preprocessing
- **XGBoost & CatBoost**: Advanced boosting algorithms
- **Flask**: Web application framework
- **Pandas & NumPy**: Data manipulation and analysis
- **HTML/CSS**: Frontend interface

## Model Performance

The system automatically selects the best performing model based on R² score evaluation on test data, ensuring reliable predictions for student math performance.
