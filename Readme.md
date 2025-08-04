# AI-Powered Fault Detection in Power Distribution Systems

This project demonstrates the use of machine learning to automatically detect and classify different types of faults in a power distribution system. By analyzing electrical measurement data, the model can distinguish between normal operating conditions and various fault types, enabling rapid response and improving grid reliability.

The model was developed using the AutoAI capabilities of IBM Watson Studio and is deployed as a scalable API on IBM Cloud.

---

## Table of Contents

* [Project Overview](#project-overview)
* [Dataset](#dataset)
* [Methodology](#methodology)
* [Deployment](#deployment)
* [Future Scope](#future-scope)
* [How to Use](#how-to-use)

---

## Project Overview

The objective is to build a robust classification model that takes real-time electrical data (voltage, current, etc.) as input and outputs a prediction of the grid's status. The model can identify the following conditions:

* Line Breakage
* Transformer Failure
* Overheating
* Normal Conditions

This automated identification is critical for minimizing power outage duration and preventing cascading failures in the grid.

---

## Dataset

The model was trained on the **Power System Faults Dataset**.

**Source:** Kaggle

**Features Include:**

* Voltage (V)
* Current (A)
* Power Load (MW)
* Temperature (°C)
* Wind Speed (km/h)
* Weather Condition
* Component Health

The notebook in the `/notebooks` directory contains the full data exploration and preprocessing steps.

---

## Methodology

### Data Preprocessing

* Raw data cleaned
* Categorical features (e.g., Weather Condition) encoded using Label Encoding

### Feature Engineering

* Fault Location string parsed into Latitude and Longitude features

### Model Training

* IBM AutoAI evaluated multiple models
* **Random Forest Classifier** selected as best performer
* Trained on 80% of the dataset

### Evaluation

* Evaluated on 20% test set
* High classification accuracy
* Detailed classification report and confusion matrix included in the notebook

---

## Deployment

The trained model is deployed on **IBM Cloud** using a **serverless architecture**:

### Model Hosting

* Hosted via **IBM Watson Machine Learning**

### API Endpoint

* Deployed using **IBM Cloud Functions**
* REST API endpoint handles data preprocessing and model invocation

This ensures a scalable, cost-effective solution easily integrable with other applications like monitoring dashboards.

---

## Future Scope

* **Real-Time Integration**: Connect the API to live SCADA data streams
* **Predictive Maintenance**: Extend to forecast failures before they occur
* **Advanced Models**: Explore Deep Learning or Gradient Boosting for improved accuracy

---

## How to Use

### Explore the Analysis

* Open the notebook in the `/notebooks` directory to review data preprocessing and model training

### Use the Deployed API

* Send a JSON payload to the API endpoint
* Receive real-time fault classification as a response

---

**Note:** Ensure valid credentials and permissions when accessing the IBM Cloud services and deployed model.
