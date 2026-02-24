# 🧠 NeuroAid
### AI-Powered Early Cognitive Risk Screening System

> ⚠️ **Disclaimer:** NeuroAid is a non-diagnostic awareness tool. It does NOT diagnose dementia, Alzheimer’s, or any medical condition. It provides an AI-generated cognitive risk score to encourage early consultation with healthcare professionals.

---

## 🌍 Problem Statement:

Early signs of cognitive decline (e.g., memory impairment, slowed reaction time, speech irregularities) often go unnoticed because:

- Symptoms are subtle  
- People avoid clinical testing  
- Rural areas lack specialists  
- Screening tools are expensive or inaccessible  

Traditional tools like the [Mini-Mental State Examination](https://en.wikipedia.org/wiki/Mini%E2%80%93Mental_State_Examination) and [Montreal Cognitive Assessment](https://en.wikipedia.org/wiki/Montreal_Cognitive_Assessment) require trained professionals.  

**NeuroAid bridges this gap** by offering a non-invasive, AI-powered early risk screening system accessible via web.

---

## 🚀 What NeuroAid Does

NeuroAid analyzes three key cognitive indicators:

1. 🗣 **Speech Patterns**  
2. 🧠 **Memory Recall Performance**  
3. ⚡ **Reaction Time Consistency**

It converts behavioral signals into structured metrics and computes a weighted **Cognitive Risk Score (0–100)**.

---

## 🧩 Core Features (Hackathon MVP)

### 1️⃣ Speech Analysis Module
User reads a paragraph aloud.  

AI extracts:
- Words per minute (speech rate)  
- Pause frequency  
- Repetition patterns  
- Filler word frequency  
- Sentence coherence  

Output: `Speech Score (0–100)`

---

### 2️⃣ Memory Micro-Tests
- 5-word delayed recall  
- Pattern matching  
- Sequence repetition  

Measured:
- Accuracy  
- Recall latency  

Output: `Memory Score (0–100)`

---

### 3️⃣ Reaction Time Test
User taps when the screen color changes.  

Measured:
- Average delay  
- Variability  
- False triggers  

Output: `Reaction Score (0–100)`

---

### 4️⃣ Risk Score Engine

Weighted scoring model:

Risk Score = (0.4 × Speech Score) + (0.4 × Memory Score) + (0.2 × Reaction Score)
Risk Categories:

0–40   → Low Risk
41–70  → Moderate Risk
71–100 → High Risk


### 5️⃣ Recommendation Engine

Based on risk level:

Low Risk      → Maintain mental activity & preventive exercises
Moderate Risk → Suggest consultation with a physician
High Risk     → Strong recommendation to consult a neurologist


### 🏗 System Architecture

User
  ↓
Frontend (React / Next.js)
  ↓
Backend API (Node.js + Express)
  ↓
AI Microservice (Python + FastAPI)
  ↓
Feature Extraction + Risk Engine
  ↓
Database (Firebase Firestore)
  ↓
Return Risk Report + Visualization


### 🛠 Tech Stack

## Frontend

React / Next.js

Tailwind CSS

Chart.js

Web Speech API


## Backend

Python 3.11+

FastAPI → Modern, async-ready, auto docs (/docs)

Pydantic → Data validation & type hints


## AI Microservice

Python

FastAPI

HuggingFace Transformers

Whisper (Speech-to-Text)


## Database

Firebase Firestore


## Deployment

Vercel (Frontend)

Render (Backend + AI Service)


## 🧠 AI & Feature Engineering
Speech → text using Whisper

Extract behavioral features

Normalize features

Weighted risk computation

Generates interpretable risk report


## Example API Payload:
```
POST /api/analyze
{
  "speech_audio": "base64-encoded-audio",
  "memory_results": {
    "word_recall_accuracy": 80,
    "pattern_accuracy": 70
  },
  "reaction_times": [300, 280, 350, 310]
}
```
Example Response:
```
{
  "speech_score": 72,
  "memory_score": 65,
  "reaction_score": 81,
  "risk_score": 71.2,
  "risk_level": "Moderate"
}
```
---
```
📁 GitHub Folder Structure
neuroaid/
│
├── frontend/                         # React + Vite frontend
│   ├── public/                       # Static assets
│   ├── src/
│   │   ├── components/               # All UI components
│   │   │   ├── SpeechTest.jsx
│   │   │   ├── MemoryTest.jsx
│   │   │   ├── ReactionTest.jsx
│   │   │   └── RiskDashboard.jsx
│   │   ├── pages/                    # Screens / pages
│   │   │   ├── Home.jsx
│   │   │   └── Results.jsx
│   │   ├── services/                 # API calls
│   │   │   └── api.js
│   │   ├── hooks/
│   │   │   └── useFormState.js
│   │   ├── utils/
│   │   │   └── helpers.js
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css                 # Tailwind import
│   ├── package.json
│   ├── tailwind.config.js
│   └── vite.config.js
│
├── backend/                          # FastAPI backend
│   ├── main.py                       # FastAPI app entrypoint
│   ├── routers/
│   │   └── analyze.py                # /api/analyze endpoint
│   ├── services/
│   │   └── ai_service.py             # Feature extraction + scoring engine
│   ├── utils/
│   │   └── logger.py                 # Request/error logging
│   ├── models/                        # Optional Pydantic models
│   ├── config.py                     # Weights, thresholds, model paths
│   ├── db.py                         # Firestore integration
│   ├── requirements.txt
│   └── README.md                     # How to run backend
│
├── ai-service/                        # Optional separate AI microservice
│   ├── app.py                         # FastAPI or module for AI
│   ├── feature_extractor.py
│   ├── scoring_engine.py
│   ├── models/                        # Whisper / transformer models
│   ├── utils/
│   │   ├── audio_utils.py
│   │   ├── text_utils.py
│   │   └── data_processing.py
│   ├── config.py
│   ├── requirements.txt
│   └── README.md
│
├── docs/
│   ├── architecture.md
│   ├── api-spec.md
│   └── research-notes.md
│
├── .env.example                       # Environment variables (PORT, Firestore credentials)
├── docker-compose.yml                  # Optional: containerize frontend + backend + AI
├── README.md                           # Project overview, hackathon instructions
└── LICENSE
```
---
### 🌟 Future Enhancements
Longitudinal cognitive tracking

Emotional tone analysis

Doctor dashboard

PDF medical-style report export

Low-bandwidth rural mode

---

### 📌 Why NeuroAid Matters
Accessible AI-assisted cognitive screening can significantly improve early awareness, preventive action, and quality of life, especially in areas lacking specialist neurologists.

---

### 📜 License
MIT License


---
