# Voice Integrity Firewall (SIH Project)

A privacy-preserving system for detecting AI-generated voices and preventing voice-based fraud.

## 🚀 Project Overview

This project is an API-first deepfake voice detection system built for the **Smart India Hackathon (SIH)**. It utilizes a memory-safe FastAPI backend to ingest audio files, extract raw numeric arrays, and process them through an acoustic machine learning risk engine to deliver instant security assessments.

### Key Architecture Features

* **Privacy-First:** Audio files are processed entirely in server RAM using `io.BytesIO` and NumPy. Files are never stored on the hard drive.
* **Rapid MVP Pipeline:** File-upload-based architecture optimized for `.wav`, `.mp3`, `.m4a`, and `.ogg` formats, including WhatsApp voice notes, while avoiding complex or restricted telecom integrations.
* **Contextual Risk Scoring:** Dynamically classifies audio into **Low**, **Medium**, or **High** risk with actionable security recommendations.

---

## 📂 Repository Structure

```text
Voice-Integrity-Firewall/
├── backend/          # FastAPI server, audio processing, and ML inference
├── frontend/         # Vanilla HTML/JS client interface
├── data/             # Experimental audio datasets
├── docs/             # Project architecture and reports
├── ml/               # Model training notebooks and weights
└── tests/             # Automated or manual test scripts
```

---

## 🛠️ Getting Started & Local Setup

### 1. Backend Setup

Navigate to the backend directory and set up your Python environment:

```bash
# Move into the backend folder
cd backend

# Create a virtual environment
python -m venv .venv

# Activate the environment (Windows)
.venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt
```

### Run the FastAPI Development Server

The server runs on port `7000` by default:

```bash
uvicorn main:app --host 0.0.0.0 --port 7000 --reload
```

Once the server is running, you can access the interactive API documentation through Swagger UI:

**http://127.0.0.1:7000/docs**

---

### 2. Frontend Setup

Navigate to the frontend directory:

```bash
cd frontend
```

You can simply open `index.html` directly in your browser, or serve it using a Live Server extension in your editor.

Make sure the frontend JavaScript points to the local backend API endpoint:

```text
http://127.0.0.1:7000/api/analyze-audio
```

---

## 🔄 Application Flow

```text
Audio File
    ↓
FastAPI Backend
    ↓
In-Memory Processing (io.BytesIO)
    ↓
Audio Processing & Feature Extraction
    ↓
ML Risk Engine
    ↓
Risk Classification
    ↓
Security Recommendation
```
