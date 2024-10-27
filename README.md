Credit Risk Modeling using Machine Learning in Python

Aim
The primary goal of this project is to explore the Lending Club dataset, derive insightful observations through data visualizations, and build machine learning models to predict the Probability of Default (PD), Loss Given Default (LGD), and Exposure at Default (EAD) based on various features using supervised learning techniques.
This project aims to support lenders in assessing credit risk, enhancing loan portfolio performance, and meeting regulatory standards.

Key Insights
Higher annual incomes are correlated with a lower Probability of Default (PD), whereas higher debt-to-income ratios show a positive correlation with PD.
Data skewness was identified in key features, necessitating transformations to enhance model performance.
Missing values were addressed through imputation based on feature correlations, improving model accuracy and consistency.

Project Structure
├── data
│    ├── loan_data_2007_2014.csv                  # Main CSV file with raw data
│    ├── loan_data_2007_2014_preprocessed.csv     # Data file after preprocessing
│    ├── df_scorecard.csv                         # Contains coefficients for the scorecard
├── Models
│    ├── PD Model
│    │   ├── pd_model.sav                         # Saved model for Probability of Default
│    ├── LGD
│    │   ├── lgd_model_stage_1.sav                # Stage 1 model for Loss Given Default
│    │   ├── lgd_model_stage_2.sav                # Stage 2 model for Loss Given Default
├── Notebooks
│    ├── Step_1) Credit Risk Modeling_General Preprocessing.ipynb       # Exploratory Data Analysis and general preprocessing
│    ├── Step_2) PD model Data Preparation.ipynb                        # Data preparation specifically for PD model
│    ├── Step_3) PD model Estimation.ipynb                              # PD model estimation and tuning
│    ├── Step_4) Credit Risk Modeling and Scorecard Development for Probability of Default (PD).ipynb  # PD model training and scorecard creation
│    ├── Step_5) Credit Risk Model Monitoring and Population Stability Index (PSI) Analysis for Loan Data.ipynb  # Model monitoring and stability analysis using PSI
│    ├── Step_6) Expected Loss Estimation and Credit Risk Analysis Using PD, LGD, and EAD Modeling for Consumer Loan Portfolio.ipynb # Modeling LGD and EAD, followed by expected loss calculation based on PD, LGD, and EAD values

Dataset
The dataset contains information on over 800,000 consumer loans issued from 2007 to 2015 by Lending Club, a large US peer-to-peer lending company. We use a version that includes various borrower attributes and loan characteristics. This dataset was previously available on Kaggle. An alternative Lending Club dataset can be explored here: Kaggle Lending Club Dataset.
https://www.kaggle.com/code/ianolmstead/credit-risk/input?select=loan_data_2007_2014.csv

Modeling Approach
PD Model: Logistic Regression was used to predict the Probability of Default, evaluated using metrics like Area Under the Curve (AUC) and F1 score.
LGD Model: A two-stage approach involving Logistic Regression for the initial stage and Linear Regression for the second stage, evaluated using Mean Absolute Error (MAE) for model accuracy.
EAD Model: Linear Regression with R-squared as the evaluation metric is used to estimate the Exposure at Default.

Tools and Libraries
The project utilizes the following libraries and tools:
pandas for data loading, cleaning, and transformation
scikit-learn for building and training the logistic and linear regression models
plotly for interactive visualizations to uncover patterns and insights in the data
Flask for creating a simple web application to deploy the model and demonstrate real-time predictions

Additional Libraries:
numpy for numerical operations
matplotlib for supplementary plotting
scipy for statistical functions and calculations

Score Card (FICO Score 300-850)
The project includes the development of a scorecard aligned with the FICO scoring system. This scorecard provides an intuitive and standardized risk assessment for each loan, 
making it easier for lenders to interpret the creditworthiness of borrowers.

Credits
This project is based on knowledge gained from the following course: Credit Risk Modeling in Python https://learn.365datascience.com/courses/credit-risk-modeling-in-python.
