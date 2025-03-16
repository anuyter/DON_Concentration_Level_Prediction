DON Concentration Prediction Model


This project is designed to predict DON (Deoxynivalenol) concentration in corn samples using hyperspectral imaging data. The workflow includes data preprocessing, model training and evaluation, FastAPI for prediction API, and Streamlit for a user-friendly interactive interface for real-time predictions. Additionally, unit tests are implemented to ensure the robustness of the model.


Table of Contents:
Project Overview
Installation
Folder Structure
Data Preprocessing
Model Training and Evaluation
Prediction API with FastAPI
Interactive Streamlit App
Unit Testing
Running the Application
GitHub Integration with VS Code

Installation
Create a virtual environment:

python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt

Folder Structure:

mycotoxin_prediction/
│── mycotoxin_prediction/
│   ├── 1_data_preprocessing.ipynb     # Data Cleaning, Feature Engineering, Normalization
│   ├── 2_model_training_evaluation.ipynb  # Model Training and Evaluation
│── streamlit_app.py                   # Streamlit App for User Interaction
│── app.py                             # FastAPI for Model Deployment
│── test_model.py                      # Unit Testing for the Prediction Pipeline
│── README.md                          # Documentation
│── requirements.txt                   # Dependencies

Data Preprocessing
This step involves loading the dataset, handling missing values, normalizing the spectral features, and splitting the data into train and test sets.

File: 1_data_preprocessing.ipynb
Key steps:
Load dataset
Handle missing values (imputation)
Normalize spectral features
Save processed data as .npy files for model training

Model Training and Evaluation
The trained model is a neural network designed to predict the DON concentration. The evaluation includes metrics such as RMSE, MAE, and R² score. Model performance is visualized through plots like residuals and prediction vs. actual values.
File: 2_model_training_evaluation.ipynb
Key steps:
Load preprocessed data
Train a baseline model (neural network)
Evaluate model performance
Save the trained model (mycotoxin_model.h5)

Prediction API with FastAPI
This step exposes the trained model as an API using FastAPI. Users can send input data and receive predictions through this API.

File: app.py
Key steps:
Load the trained model
Create FastAPI endpoints for receiving spectral data and returning predictions
Launch FastAPI app for real-time predictions


Interactive Streamlit App
An interactive Streamlit app is created to allow users to upload spectral data and receive predictions in real-time.

File: streamlit_app.py
Key steps:
Build a simple UI for uploading spectral data
Display predictions in real-time
Visualize results for better user understanding



Unit Testing
Unit tests are implemented to ensure the robustness of the model and prediction pipeline. Tests are created for checking data processing functions and model inference.

File: test_model.py
Key steps:
Test data processing functions
Test model inference with sample inputs
Validate predictions and check for edge cases


Running the Application
To run the FastAPI application locally:

Start the FastAPI server:

uvicorn app:app --reload

Access the API at http://127.0.0.1:8000

To run the Streamlit app:
Run the Streamlit app:

streamlit run streamlit_app.py
Access the app at http://localhost:8501

GitHub Integration with VS Code
If you have already connected VS Code to your GitHub account (instead of cloning the repo), follow these steps to push your code to GitHub:

Initialize Git (if not already done):

git init
git remote add origin <your_repo_url>
git add .
git commit -m "Initial commit"
git push -u origin main

VS Code will handle your GitHub authentication and allow you to easily push updates to your repository whenever you make changes.