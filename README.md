# Heart Disease Prediction System

A full-stack Machine Learning web application that predicts heart disease risk using a trained scikit-learn model. The system includes a FastAPI backend, React frontend, PostgreSQL database, and ML model integration. Every prediction is stored in the database for tracking, analytics, and real-world production simulation.

This project demonstrates complete end-to-end Machine Learning deployment using modern full-stack architecture.

---

# Live Architecture Overview

React Frontend (Vite)  
http://localhost:5173  

↓  

FastAPI Backend  
http://127.0.0.1:8000  

↓  

Machine Learning Model (scikit-learn model.pkl)

↓  

PostgreSQL Database (heart_predictions table)

---

# Features

• End-to-end Machine Learning deployment  
• FastAPI production-ready backend  
• React frontend with live prediction UI  
• PostgreSQL database integration  
• SQLAlchemy ORM for clean database management  
• Automatic Swagger API documentation  
• Real-time prediction storage in database  
• Modular, scalable, production-grade architecture  

---

# Tech Stack

Backend  
Python  
FastAPI  
Uvicorn  
SQLAlchemy  
PostgreSQL  
psycopg2  

Machine Learning  
pandas  
numpy  
scikit-learn  

Frontend  
React  
Vite  
JavaScript  
Fetch API  

Database  
PostgreSQL  

Tools  
Git  
VS Code  
Terminal  

---

# Project Structure

```
Heart_Disease_Prediction_System/

backend/
│
├── app/
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   └── routes/
│       └── predict.py
│
├── ml_model/
│   ├── train.py
│   └── model.pkl
│
└── data/
    └── heart.csv

frontend/
│
├── src/
├── package.json
├── vite.config.js
└── index.html

README.md
```

---

# Complete Setup Guide (End-to-End)

Follow every step exactly.

---

# Step 1: Clone Repository

```
git clone https://github.com/YOUR_USERNAME/Heart_Disease_Prediction_System.git

cd Heart_Disease_Prediction_System
```

---

# Step 2: Create Python Virtual Environment

Mac/Linux

```
python3 -m venv .venv

source .venv/bin/activate
```

Windows

```
python -m venv .venv

.venv\Scripts\activate
```

---

# Step 3: Install Backend Dependencies

```
pip install fastapi uvicorn sqlalchemy psycopg2-binary pandas numpy scikit-learn
```

Verify

```
pip list
```

---

# Step 4: Install PostgreSQL

Mac (Homebrew)

```
brew install postgresql

brew services start postgresql
```

Verify PostgreSQL running

```
brew services list
```

Status should be:

```
postgresql started
```

---

# Step 5: Create Database

Open PostgreSQL

```
psql postgres
```

Create database

```
CREATE DATABASE heartdb;
```

Exit

```
\q
```

---

# Step 6: Configure Database Connection

Open file

```
backend/app/database.py
```

Set your username

```
DATABASE_URL = "postgresql://YOUR_USERNAME@localhost:5432/heartdb"
```

Example

```
DATABASE_URL = "postgresql://kalyanreddy@localhost:5432/heartdb"
```

---

# Step 7: Add Dataset

Place dataset file here

```
backend/data/heart.csv
```

Verify

```
ls backend/data
```

Expected output

```
heart.csv
```

---

# Step 8: Train Machine Learning Model

Run

```
python backend/ml_model/train.py
```

This creates

```
backend/ml_model/model.pkl
```

Verify model file

```
ls -lh backend/ml_model/model.pkl
```

File size must NOT be 0 bytes.

---

# Step 9: Start FastAPI Backend

Run

```
uvicorn backend.app.main:app --reload
```

Backend running at

```
http://127.0.0.1:8000
```

Swagger API Docs

```
http://127.0.0.1:8000/docs
```

---

# Step 10: Start React Frontend

Open new terminal

```
cd frontend

npm install

npm run dev
```

Frontend running at

```
http://localhost:5173
```

---

# Step 11: Use the Application

Open browser

```
http://localhost:5173
```

Enter values and click Predict.

You will see prediction result.

---

# API Endpoint

POST

```
/predict
```

Example Request

```
{
  "age": 52,
  "sex": 1,
  "cp": 0,
  "trestbps": 125,
  "chol": 212,
  "fbs": 0,
  "restecg": 1,
  "thalach": 168,
  "exang": 0,
  "oldpeak": 1.0,
  "slope": 2,
  "ca": 2,
  "thal": 3
}
```

Example Response

```
{
  "prediction": 0
}
```

0 = Lower Risk  
1 = Higher Risk  

---

# Database Storage Verification

Open PostgreSQL

```
psql heartdb
```

Run

```
SELECT * FROM heart_predictions ORDER BY id DESC LIMIT 5;
```

All predictions will be stored here.

---

# Common Errors and Fixes

Model file empty

```
rm backend/ml_model/model.pkl

python backend/ml_model/train.py
```

PostgreSQL connection error

Verify service running

```
brew services list
```

CORS error

Ensure CORSMiddleware added in

```
backend/app/main.py
```

---

# Development Workflow

Start backend

```
uvicorn backend.app.main:app --reload
```

Start frontend

```
cd frontend

npm run dev
```

---

# Future Improvements

• Docker containerization  
• Cloud deployment (AWS / GCP / Azure)  
• Model performance metrics dashboard  
• User authentication  
• Prediction history UI  
• Model retraining pipeline  

---

# Author

Kalyan Reddy  
AI/ML Engineer  
Full-Stack Developer  

---

# License

MIT License

Free to use and modify.
