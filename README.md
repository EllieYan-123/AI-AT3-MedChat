# 🩺 MedChat - AI-Powered Medical Chatbot for Doctor-Patient Interaction

MedChat is a lightweight, intelligent medical chatbot designed to assist both patients and doctors. Patients can input symptoms and receive predicted conditions and medication suggestions. Doctors can review the AI's prediction, confirm or revise the diagnosis, and submit medical advice in a structured dual-view interface.

---

## 🚀 Features

- 🔍 **Symptom understanding via BERT (MiniLM)**
- 🧠 **Semantic similarity matching** for condition prediction
- 💊 **Medication recommendation** with filtering (alcohol/pregnancy)
- 👨‍⚕️ **Doctor-side diagnosis confirmation & prescription**
- 🧾 **Real-time logging** to CSV for traceability
- 🖥️ **Dual interface (Patient / Doctor)** built with Streamlit
- 🌐 **Public deployment via ngrok or Docker-ready for cloud**

---

## 🖼 System Architecture

```mermaid
flowchart TD
    Patient[🧍 Patient] --> PatientUI["Patient View"]
    Doctor[🧑‍⚕️ Doctor] --> DoctorUI["Doctor View"]

    PatientUI --> Chatbot["MedicalChatbot (BERT-based)"]
    DoctorUI -->|Review| Chatbot
    Chatbot --> CSV["chat_log.csv"]

    Chatbot --> SymptomMatcher
    Chatbot --> DrugRecommender```
##


## 📦 Project Structure

.
├── ui.py / app.py                 # Main Streamlit interface (dual view)
├── medical_chatbot.py            # Backend logic: symptom matcher + drug recommender
├── drugs_side_effects_drugs_com.csv   # Dataset (drug + condition + side effects)
├── logs/
│   └── chat_log.csv              # Patient logs
├── models/                       # (optional) Saved models if extended
└── requirements.txt              # Python dependencies


## 🧪 Getting Started

1. Clone the repo
git clone https://github.com/yourname/medchat
cd medchat

2. Set up the environment
conda create -n medchat python=3.9
conda activate medchat
pip install -r requirements.txt

3. Run the app locally
streamlit run ui.py


## 🗂 Dataset
This app uses a custom drug-condition dataset (drugs_side_effects_drugs_com.csv) containing:

 ·	medical_condition

 ·	medical_condition_description

 ·	drug_name

 ·	side_effects

 ·	alcohol compatibility

 ·	pregnancy_category


## 📊 Logging & Audit
All diagnosis activity is logged in real-time to logs/chat_log.csv, including:

 ·	Timestamp

 ·	Patient info

 ·	Symptoms

 ·	Predicted & confirmed diagnosis

 ·	Doctor notes


## 🧠 Models Used
 ·	MiniLM-L6-v2: fast, compact BERT-based encoder

 ·	Cosine similarity: for condition matching

 ·	SentenceTransformer: embedding interface



