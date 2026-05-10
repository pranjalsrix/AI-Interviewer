# 🧠 AI-Powered Technical Interview Preparation Platform

A scalable, AI-driven full-stack interview preparation platform designed to simulate real-world technical interviews with voice interaction, coding assessments, and intelligent evaluation workflows. The system combines modern web technologies with an independent AI microservice architecture to deliver dynamic interview experiences across multiple technical domains.

The platform enables candidates to practice technical interviews in an interactive environment featuring real-time coding, speech-to-text processing, AI-generated interview questions, and detailed performance analytics. It supports customizable interview configurations based on role, difficulty level, and interview type, allowing users to simulate realistic technical screening environments.

---

# ✨ Core Features
## 🎯 Dynamic Interview Configuration

Users can configure interview sessions based on:

* Technical Role Selection

  * MERN Stack
  * Backend Development
  * Python Development
  * Data Science
  * Machine Learning
  * Frontend Engineering

* Difficulty Levels

  * Beginner
  * Intermediate
  * Advanced

* Interview Modes

  * Conceptual Oral Interviews
  * Coding Assessments
  * Mixed Technical Interviews

The AI system dynamically adjusts question complexity and evaluation criteria according to selected configurations.

---

# 🎙️ Voice-Based Technical Interviewing

The platform supports verbal interview responses through integrated speech-to-text processing.

### Features

* Real-time audio recording from browser
* Audio preprocessing using FFMPEG and PyDub
* Speech transcription using OpenAI Whisper
* Conceptual answer analysis through AI evaluation
* Confidence and communication assessment scoring

This creates a realistic simulation of live technical HR and conceptual interview rounds.

---

# 💻 In-Browser Coding Environment

The application integrates a fully interactive coding interface using Monaco Editor.

### Coding Features

* Multi-language coding support
* Real-time code writing and editing
* Syntax highlighting
* Structured coding interview workflow
* AI-powered code analysis and evaluation
* Logic-based scoring system
* Expected solution comparison

The coding environment is designed to replicate modern online assessment platforms used by technical recruiters.

---

# 🤖 AI Microservice Architecture

The system follows a microservice-inspired architecture where AI processing is isolated into an independent Python-based service for scalability and modularity.

## AI Service Responsibilities

### 🔹 Dynamic Question Generation

Interview questions are generated contextually using locally hosted LLM models through Ollama.

Capabilities include:

* Role-specific question generation
* Difficulty-aware question creation
* Coding problem generation
* Conceptual technical questioning
* Contextual follow-up generation

### 🔹 Intelligent Technical Evaluation

The AI service evaluates:

* Code correctness
* Logical implementation quality
* Conceptual answer relevance
* Technical depth
* Communication confidence
* Problem-solving quality

The evaluation engine returns structured JSON responses containing scores, explanations, and improvement feedback.

---

# 📊 Advanced Performance Analytics

The platform includes a dedicated analytics system for tracking interview performance over time.

## Analytics Features

* Session history tracking
* Technical performance scoring
* Confidence score analysis
* Question-level breakdowns
* AI-generated improvement suggestions
* Visual performance dashboards
* Historical trend monitoring

Charts and analytics are rendered using Chart.js for clean performance visualization.

---

# 🔐 Authentication & Security

The platform uses JWT-based authentication workflows for secure user management.

### Security Features

* User registration and login
* Password hashing using bcryptjs
* Protected API routes
* Token-based session management
* Authentication middleware architecture
* Secure route authorization

---

# 🛠️ Complete Tech Stack

# Frontend

| Technology       | Purpose                          |
| ---------------- | -------------------------------- |
| React (Vite)     | Frontend Framework               |
| Redux Toolkit    | State Management                 |
| Tailwind CSS     | UI Styling                       |
| React Router DOM | Routing                          |
| Monaco Editor    | Browser-based Coding Environment |
| Chart.js         | Performance Visualization        |
| Axios            | API Communication                |

---

# Backend API Gateway

| Technology | Purpose              |
| ---------- | -------------------- |
| Node.js    | Runtime Environment  |
| Express.js | Backend Framework    |
| MongoDB    | Database             |
| Mongoose   | ODM Layer            |
| JWT        | Authentication       |
| bcryptjs   | Password Encryption  |
| Multer     | File Upload Handling |

---

# AI Microservice

| Technology     | Purpose                   |
| -------------- | ------------------------- |
| Python 3.9+    | AI Service Runtime        |
| FastAPI        | AI Microservice Framework |
| Ollama         | Local LLM Runtime         |
| Mistral Model  | AI Question Generation    |
| OpenAI Whisper | Speech-to-Text            |
| PyDub          | Audio Processing          |
| FFMPEG         | Audio Conversion Pipeline |

---

# 🚀 Local Development Setup

# Prerequisites

Before starting the project, ensure the following dependencies are installed:

* Node.js (v16+)
* npm
* Python 3.9+
* pip
* MongoDB
* Ollama
* FFMPEG

---

# Ollama Setup

Install Ollama from:

https://ollama.com

Pull the required model:

```bash
ollama pull mistral
```

---

# 📦 Repository Setup

```bash
git clone https://github.com/pranjalsrix/ai-interviewer.git
cd ai-interviewer
```

---

# ⚙️ Backend Setup

```bash
cd backend
npm install
```

Create `.env`:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
NODE_ENV=development
AI_SERVICE_URL=http://localhost:8000
```

Run backend:

```bash
npm run server
```

---

# 🤖 AI Service Setup

```bash
cd ../ai_service
```

Create virtual environment:

```bash
python -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install fastapi uvicorn ollama openai-whisper pydub python-dotenv
```

Create `.env`:

```env
AI_SERVICE_PORT=8000
OLLAMA_MODEL_NAME=mistral
```

Run AI service:

```bash
uvicorn main:app --reload --port 8000
```

---

# 🌐 Frontend Setup

```bash
cd ../frontend
npm install
```

Create `.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

Run frontend:

```bash
npm run dev
```

---

# ⚡ One-Click Startup

The project also includes a simplified startup script:

```bash
FOR-FIRST-TIME.bat
```

This automates dependency installation and service startup workflows for rapid local setup.

---

# 📐 System Architecture

The platform follows a distributed service architecture for improved scalability and modular AI processing.

## Architecture Flow

### 1️⃣ Frontend Client (React)

Responsible for:

* User Interface
* Audio Recording
* Coding Environment
* Session Management
* Analytics Rendering

Communicates with Node.js backend via REST APIs.

---

### 2️⃣ Node.js Backend (API Gateway)

Responsible for:

* Authentication
* Database Operations
* Session Storage
* API Routing
* Middleware Management
* Communication with AI Service

Acts as the central orchestration layer.

---

### 3️⃣ Python AI Microservice

Handles computationally intensive AI tasks:

* Question Generation
* Speech Transcription
* Code Evaluation
* Conceptual Analysis
* Score Generation

Endpoints include:

* `POST /generate-questions`
* `POST /transcribe`
* `POST /evaluate`

---

### 4️⃣ Ollama LLM Engine

Provides locally hosted large language model execution for:

* Technical Question Generation
* Intelligent Evaluation
* Contextual Response Analysis
* Interview Simulation Logic

---

# 📂 Suggested Project Structure

```text
ai-interviewer/
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── middleware/
│   ├── models/
│   ├── config/
│   └── server.js
│
├── ai_service/
│   ├── services/
│   ├── utils/
│   ├── main.py
│   └── requirements.txt
│
└── README.md
```

---

# 📈 Future Improvements

Potential future enhancements include:

* Live AI interviewer avatars
* Real-time collaborative mock interviews
* WebRTC integration
* AI-generated resume analysis
* Adaptive interview learning system
* Docker containerization
* Kubernetes deployment
* Cloud GPU inference support
* Multi-model LLM switching

---

# 🧪 Testing & Evaluation Goals

The platform is designed to help candidates:

* Improve communication skills
* Practice coding under pressure
* Receive AI-generated feedback
* Analyze technical weaknesses
* Build interview confidence
* Simulate realistic interview environments

---

# 📄 License

This project is intended for educational, portfolio, and technical learning purposes.

