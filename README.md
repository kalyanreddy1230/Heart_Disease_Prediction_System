# ❤️ Heart Disease Prediction System

## 📌 Overview

The Heart Disease Prediction System is a full-stack machine learning application that predicts the likelihood of heart disease using clinical and demographic patient data.

This project demonstrates:

- End-to-end ML lifecycle
- Model training & evaluation
- REST API development
- Database integration
- Frontend integration
- Production-ready architecture

---

## 🏗️ System Architecture

Frontend (React)
        ↓
Backend API (FastAPI)
        ↓
Machine Learning Model (.pkl)
        ↓
PostgreSQL Database

---

## 🛠️ Tech Stack

### Machine Learning
- Python 3.11+
- Pandas
- NumPy
- Scikit-learn
- Joblib

### Backend
- FastAPI
- Uvicorn
- SQLAlchemy
- Pydantic
- PostgreSQL

### Frontend
- React (Vite)
- Axios
- TailwindCSS / Bootstrap

### DevOps (Optional)
- Docker
- Docker Compose

---

## 📂 Project Structure

heart-disease-prediction/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── database.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── routes/
│   │   │   └── predict.py
│   │   └── ml_model/
│   │       ├── train.py
│   │       └── model.pkl
│   ├── requirements.txt
│
├── frontend/
│   ├── src/
│   ├── package.json
│
├── data/
│   └── heart.csv
│
├── docker-compose.yml
└── README.md

---

## 📊 Dataset

Dataset: `heart.csv`

Common Features:
- age
- sex
- cp (chest pain type)
- trestbps
- chol
- fbs
- restecg
- thalach
- exang
- oldpeak
- slope
- ca
- thal
- target (0 = No Disease, 1 = Disease)

---

# 🧠 Machine Learning Pipeline

1. Load dataset
2. Perform EDA
3. Handle missing values
4. Feature scaling
5. Train multiple models
6. Evaluate accuracy
7. Save best model as `model.pkl`

---

# 🚀 Setup Instructions

---

## 🔹 1. Clone Repository

```bash
git clone <your-repo-url>
cd heart-disease-prediction
```

---

## 🔹 2. Backend Setup

### Create Virtual Environment

```bash
cd backend
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔹 3. Train ML Model

```bash
python app/ml_model/train.py
```

This generates:

```
model.pkl
```

---

## 🔹 4. Setup PostgreSQL

Create a database:

```sql
CREATE DATABASE heartdb;
```

Update your database credentials inside:

```
backend/app/database.py
```

---

## 🔹 5. Run Backend API

```bash
uvicorn app.main:app --reload
```

Open Swagger UI:

```
http://127.0.0.1:8000/docs
```

---

## 🔹 6. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Open:

```
http://localhost:5173
```

---

# 📡 API Endpoints

## POST /predict

### Request Body

```json
{
  "age": 52,
  "sex": 1,
  "cp": 2,
  "trestbps": 125,
  "chol": 212,
  "fbs": 0,
  "restecg": 1,
  "thalach": 168,
  "exang": 0,
  "oldpeak": 1.0,
  "slope": 2,
  "ca": 0,
  "thal": 2
}
```

### Response

```json
{
  "prediction": 1,
  "probability": 0.87
}
```

---

# 🗄️ Database Schema

Table: predictions

| Column | Type |
|--------|------|
| id | Integer (PK) |
| age | Integer |
| sex | Integer |
| ... | ... |
| prediction | Integer |
| probability | Float |
| created_at | Timestamp |

---

# 🐳 Docker (Optional)

Run full system:

```bash
docker-compose up --build
```

---

# 📈 Model Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

# 🔒 Future Improvements

- Model versioning
- Authentication (JWT)
- CI/CD pipeline
- AWS deployment
- Model monitoring
- Logging & observability

---

# 🎯 Resume Value

This project demonstrates:

- Production-grade ML system design
- API development with FastAPI
- Database integration
- Full-stack development
- Real-world deployment readiness

---

# 👨‍💻 Author

Kalyan Reddy  
AI / ML Engineer  

---
