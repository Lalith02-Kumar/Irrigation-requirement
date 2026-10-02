# 🌱 Irrigation Water Requirement Prediction Using Machine Learning

A machine learning-based application that predicts the **irrigation requirement of an agricultural field as Low, Medium, or High** using soil, weather, crop, and irrigation-related parameters.

## 📌 Project Overview

Agricultural irrigation requirements depend on soil properties, weather conditions, crop type, crop growth stage, and previous irrigation. This project uses machine learning to classify irrigation requirement into:

- 🟢 Low
- 🟡 Medium
- 🔴 High

The Streamlit application allows users to enter agricultural parameters and receive a predicted irrigation requirement along with class probabilities.

## 🎯 Objectives

1. Collect and understand an irrigation-related dataset.
2. Perform exploratory data analysis.
3. Identify numerical and categorical features.
4. Preprocess the dataset.
5. Encode categorical variables using One-Hot Encoding.
6. Train multiple machine learning classification models.
7. Evaluate the trained models.
8. Select and configure a suitable final model.
9. Save the trained model using Joblib.
10. Develop a Streamlit prediction interface.
11. Display prediction probabilities for all irrigation classes.
12. Deploy the application online.

## 📊 Dataset

**Irrigation Water Requirement Prediction Dataset**

| Property | Value |
|---|---:|
| Records | 10,000 |
| Columns | 20 |
| Input Features | 19 |
| Target | `Irrigation_Need` |
| Problem Type | Multiclass Classification |
| Classes | Low, Medium, High |

### Features

**Soil:** `Soil_Type`, `Soil_pH`, `Soil_Moisture`, `Organic_Carbon`, `Electrical_Conductivity`

**Weather:** `Temperature_C`, `Humidity`, `Rainfall_mm`, `Sunlight_Hours`, `Wind_Speed_kmh`

**Crop:** `Crop_Type`, `Crop_Growth_Stage`, `Season`

**Irrigation:** `Irrigation_Type`, `Water_Source`, `Field_Area_hectare`, `Mulching_Used`, `Previous_Irrigation_mm`, `Region`

### Target

```text
Irrigation_Need
```

Possible values:

```text
Low
Medium
High
```

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Exploratory Data Analysis
   ↓
Data Preprocessing
   ↓
Numerical + Categorical Features
   ↓
One-Hot Encoding
   ↓
Train-Test Split
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Random Forest Configuration
   ↓
Model Saving
   ↓
Streamlit Application
   ↓
User Input
   ↓
Prediction
   ↓
Low / Medium / High
   ↓
Prediction Probabilities
   ↓
Deployment
```

## 🧹 Data Preprocessing

The preprocessing workflow includes:

- Dataset structure and data type analysis
- Identification of numerical and categorical features
- Exploratory data analysis
- Separation of input features and target
- One-Hot Encoding of categorical features
- Train-test splitting
- `ColumnTransformer` and Scikit-learn `Pipeline`

## 🤖 Machine Learning Models

### Logistic Regression

Used as a baseline classification model.

**Test Accuracy: 82.60%**

### Decision Tree

A tree-based classification algorithm using a sequence of decision rules.

**Test Accuracy: 99.60%**

### Random Forest

An ensemble classification algorithm that combines multiple decision trees.

Final configured parameters:

```text
n_estimators = 200
max_depth = 15
min_samples_split = 5
random_state = 42
```

**Initial Random Forest Accuracy: 97.35%**

**Final Configured Random Forest Accuracy: 96.95%**

The Random Forest model is used in the final Streamlit application.

## 📈 Model Evaluation

Metrics used:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

| Model | Accuracy |
|---|---:|
| Logistic Regression | 82.60% |
| Decision Tree | 99.60% |
| Random Forest | 97.35% |
| Configured Random Forest | 96.95% |

## 🔍 Feature Importance

Feature importance was analyzed using the trained Random Forest model.

Important features include:

- Crop Growth Stage
- Soil Moisture
- Mulching Used
- Wind Speed
- Temperature
- Rainfall

## 💾 Model Saving

The trained machine learning pipeline is saved using **Joblib**:

```text
models/irrigation_model.pkl
```

The saved model contains the preprocessing and classification pipeline required for prediction.

## 🌐 Streamlit Application

Users can enter:

### Soil Information
- Soil Type
- Soil pH
- Soil Moisture
- Organic Carbon
- Electrical Conductivity

### Weather Information
- Temperature
- Humidity
- Rainfall
- Sunlight Hours
- Wind Speed

### Crop Information
- Crop Type
- Crop Growth Stage
- Season

### Irrigation Information
- Irrigation Type
- Water Source
- Field Area
- Mulching Used
- Previous Irrigation
- Region

## 🔮 Prediction Workflow

```text
User Input
    ↓
Pandas DataFrame
    ↓
Saved ML Pipeline
    ↓
Preprocessing
    ↓
Random Forest
    ↓
Prediction
```

Output:

```text
LOW
MEDIUM
HIGH
```

## 📊 Prediction Probabilities

The application uses:

```python
model.predict_proba(input_data)
```

Example:

```text
Low     : 15.20%
Medium  : 64.30%
High    : 20.50%
```

The exact probabilities depend on the user's input.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data processing |
| NumPy | Numerical operations |
| Scikit-learn | Machine learning |
| Joblib | Model saving/loading |
| Matplotlib | Data visualization |
| Seaborn | Data visualization |
| Streamlit | Web application |
| Git | Version control |
| GitHub | Source code repository |
| Streamlit Community Cloud | Deployment |
| Kaggle | Dataset / ML development |

## 📁 Project Structure

```text
Irrigation-Water-Requirement-Prediction-ML/
│
├── dataset/
│   └── irrigation_prediction.csv
│
├── models/
│   └── irrigation_model.pkl
│
├── app.py
├── prediction.py
├── irrigation_prediction.ipynb
├── requirements.txt
└── README.md
```

## ▶️ Run Locally

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### 2. Enter the project

```bash
cd Irrigation-Water-Requirement-Prediction-ML
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate it on Windows

```bash
venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the application

```bash
streamlit run app.py
```

Open:

```text
http://localhost:8501
```

## 📦 Requirements

```text
streamlit
pandas
numpy
scikit-learn
joblib
matplotlib
seaborn
```

## ☁️ Deployment

The application can be deployed using **Streamlit Community Cloud**:

```text
GitHub Repository
       ↓
Streamlit Community Cloud
       ↓
Select Repository
       ↓
Select app.py
       ↓
Install requirements.txt
       ↓
Deploy
```

## 🚀 Future Scope

- IoT-based soil moisture monitoring
- Real-time weather data
- GIS/location-based agricultural analysis
- Automated irrigation valve control
- Continuous model retraining
- Real-time agricultural monitoring
- Additional environmental sensors

## 📌 Conclusion

This project demonstrates a complete machine learning workflow for irrigation requirement classification. The system processes soil, weather, crop, and irrigation-related parameters and predicts whether the irrigation requirement is **Low, Medium, or High**.

The trained Random Forest pipeline is saved using Joblib and integrated with a Streamlit application, allowing users to interact with the machine learning model through a web interface.

## 👨‍💻 Project

**Irrigation Water Requirement Prediction Using Machine Learning**

Demonstrates:

```text
Data Analysis
     +
Data Preprocessing
     +
Machine Learning
     +
Model Evaluation
     +
Model Deployment
```

### Dataset Reference

Kaggle: Irrigation Water Requirement Prediction Dataset

https://www.kaggle.com/datasets/miadul/irrigation-water-requirement-prediction-dataset
