AI-Powered Fault Detection in Power Distribution Systems
This project demonstrates the use of machine learning to automatically detect and classify different types of faults in a power distribution system. By analyzing electrical measurement data, the model can distinguish between normal operating conditions and various fault types, enabling rapid response and improving grid reliability.

The model was developed using the AutoAI capabilities of IBM Watson Studio and is deployed as a scalable API on IBM Cloud.

Table of Contents
Project Overview

Dataset

Methodology

Deployment

Future Scope

How to Use

Project Overview
The objective is to build a robust classification model that takes real-time electrical data (voltage, current, etc.) as input and outputs a prediction of the grid's status. The model can identify the following conditions:

Line Breakage

Transformer Failure

Overheating

Normal Conditions

This automated identification is critical for minimizing power outage duration and preventing cascading failures in the grid.

Dataset
The model was trained on the Power System Faults Dataset.

Source: Kaggle

Features Include:

Voltage (V)

Current (A)

Power Load (MW)

Temperature (°C)

Wind Speed (km/h)

Weather Condition

Component Health

The notebook in the /notebooks directory contains the full data exploration and preprocessing steps.

Methodology
Data Preprocessing: The raw data was cleaned, and categorical features (e.g., Weather Condition) were converted into a numerical format using label encoding.

Feature Engineering: The Fault Location string was parsed to create separate Latitude and Longitude features.

Model Training: A Random Forest Classifier was selected as the best-performing algorithm after an automated evaluation of multiple models by IBM's AutoAI. The model was trained on 80% of the dataset.

Evaluation: The model was evaluated on a 20% hold-out test set, achieving high accuracy in classifying all fault types. The generated notebook provides a detailed classification report and a confusion matrix.

Deployment
The trained model is deployed on IBM Cloud using a serverless architecture:

Model Hosting: The model is stored and served via IBM Watson Machine Learning.

API Endpoint: An IBM Cloud Function provides a REST API endpoint. This function handles data preprocessing and invokes the model to return a real-time prediction.

This architecture ensures the solution is scalable, cost-effective, and easy to integrate with other applications like monitoring dashboards.

Future Scope
Real-Time Integration: Connect the API to live SCADA system data streams.

Predictive Maintenance: Evolve the model to predict component failures before they occur.

Advanced Models: Experiment with Deep Learning or Gradient Boosting models for potentially higher accuracy.

How to Use
Explore the Analysis: Open the notebook in the /notebooks directory to review the data analysis, preprocessing, and model training process.

Use the Deployed API: The deployed model can be called via its API endpoint. Send a JSON payload with the required features to receive a fault classification."# IBM-Project" 
