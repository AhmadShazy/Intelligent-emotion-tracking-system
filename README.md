# Intelligent Emotion System

An Intelligent Emotion System built with a **FastAPI** Python backend and a vanilla **HTML/JS/CSS** frontend. The system analyzes user input (both text and speech) to detect emotional states and provide adaptive, context-aware responses.

![Project Status](https://img.shields.io/badge/status-development-blue.svg)
![Deployment](https://img.shields.io/badge/deployment-local-blueviolet.svg)
![Python Backend](https://img.shields.io/badge/backend-FastAPI-009688.svg)
![Frontend](https://img.shields.io/badge/frontend-Vanilla%20JS-F7DF1E.svg)

## Features
- 📝 **Text Emotion Analysis:** Detects emotions from written text (with score breakdowns).
- 🎙️ **Speech Emotion Analysis:** Upload or record audio directly in the browser; transcripts are generated and analyzed for emotion.
- 🧠 **Adaptive Feedback:** Generates contextual responses based on recent user emotion history.
- 📊 **Insight Dashboards:** View an interactive scatter plot timeline and statistics of your emotional states.
- 🗄️ **MongoDB Storage:** Persists conversation logs, transcripts, and detected emotions securely.

---

## Directory Structure

```text
.
├── backend/            # Python FastAPI application
│   ├── main.py         # Application entry point and API routes
│   ├── mongo_setup.py  # Database connection logic
│   ├── speech_model.py # Speech transcription handling
│   ├── text_model.py   # NLP Emotion prediction logic
│   └── requirements.txt# Backend Python dependencies
├── frontend/           # Vanilla Web frontend
│   ├── index.html      # Main UI
│   ├── styles.css      # Custom styling
│   └── app.js          # Client-side logic and API calls
├── scripts/            # Utility and diagnostic scripts
├── .env.example        # Example environment variables 
└── README.md           # This file
```

---

## Prerequisites

- **Python 3.9+**
- **MongoDB** (Ensure MongoDB is running locally on port `27017` or update the `MONGO_URI` in your `.env` file). Alternatively, you can use the built-in Mock DB by setting `USE_MOCK_DB=1` in the `.env` file.
- **FFmpeg** is required internally for audio processing. Make sure it is installed and added to your system's `PATH`.

---

## Setup & Installation

### 1. Environment Variables
Clone the repository and copy the example environment file:
```bash
cp .env.example .env
```
Fill in the parameters (such as `MONGO_URI` and `OPENAI_API_KEY` if you wish to use OpenAI for Whisper transcriptions).

### 2. Running the Backend Server
Navigate to the `backend` directory, install requirements, and run the server:
```bash
cd backend
python -m venv venv
# Windows: venv\Scripts\activate | Mac/Linux: source venv/bin/activate
pip install -r requirements.txt
python main.py
```
*The API will be available at `http://localhost:8000`. You can view interactive docs at `/docs`.*

### 3. Running the Frontend Server
Open a new terminal, navigate to the `frontend` folder, and start a basic HTTP server:
```bash
cd frontend
python -m http.server 8080
```
*(Note: Using port 8080 ensures our API routing hooks to the backend correctly).*

*Visit `http://127.0.0.1:8080` in your browser to interact with the system!*

---

> **Note to Windows users:** 
> If you have a `run_all.bat` script provided locally, you can double-click it directly from the project root to automatically launch both the backend and frontend at the same time in separate command prompt windows.
