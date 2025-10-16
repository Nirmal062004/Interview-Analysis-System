# Interview-Analysis-System
# PrepVista - AI-Powered Career Preparation Platform

> Complete career preparation solution with AI-driven video analysis, mock interviews, and resume optimization.

## 🎯 What is PrepVista?

PrepVista is an all-in-one platform that helps job seekers prepare for interviews using AI technology. It provides:

- **📹 Video Communication Analysis** - AI analyzes your body language, posture, eye contact, and speech
- **🎤 AI Mock Interviews** - Get personalized interview questions based on your resume with real-time feedback
- **📄 Resume Optimization** - ATS compatibility check and job description matching with actionable tips

## 🛠️ Tech Stack

**Frontend:**
- React + TypeScript
- Vite
- Tailwind CSS

**Backend:**
- Python Flask
- MongoDB
- Google Gemini AI
- MediaPipe & OpenCV
- Speech Recognition

## 📦 Installation

### Prerequisites

1. **Python 3.11** - [Download](https://www.python.org/downloads/)
2. **Node.js 18+** - [Download](https://nodejs.org/)
3. **MongoDB** - [Download](https://www.mongodb.com/try/download/community)

### Backend Setup

```bash
# 1. Navigate to backend folder
cd backend

# 2. Create virtual environment
python -m venv venv

# 3. Activate virtual environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# 4. Install all dependencies
pip install Flask==3.0.0 Flask-CORS==4.0.0 Flask-PyMongo==2.3.0 pymongo==4.6.0 python-dotenv==1.0.0 PyJWT==2.8.0 bcrypt==4.1.2 Werkzeug==3.0.1 gunicorn==21.2.0 python-docx==1.1.0 mediapipe==0.10.9 opencv-python==4.9.0.80 transformers==4.36.2 moviepy==1.0.3 librosa==0.10.1 matplotlib==3.8.2 pdfplumber==0.10.3 google-generativeai==0.3.2 pandas==2.1.4 gTTS==2.5.0 pygame==2.5.2 SpeechRecognition==3.10.1 Pillow==10.2.0

# 5. Create .env file in backend folder
# Copy this content:
MONGO_URI=mongodb://localhost:27017/
DB_NAME=career_prep_db
JWT_SECRET_KEY=your-secret-key-change-this
GEMINI_API_KEY_1=your-gemini-api-key
GEMINI_API_KEY_2=your-gemini-api-key
FLASK_ENV=development
FLASK_PORT=5000
FRONTEND_URL=http://localhost:5173

# 6. Start MongoDB
# Windows:
net start MongoDB
```

### Frontend Setup

```bash
# 1. Navigate to frontend folder
cd PrepVista_frontend

# 2. Install dependencies
npm install

# 3. Create .env file in frontend root
# Copy this content:
VITE_API_URL=http://localhost:5000/api
```

## 🚀 Running the Application

### Start Backend (Terminal 1)

```bash
cd backend
venv\Scripts\activate          # Windows
# source venv/bin/activate     # Mac/Linux
python app.py
```

You should see:
```
✅ Connected to MongoDB: career_prep_db
🚀 Starting Career Preparation Platform API
📍 Server: http://localhost:5000
```

### Start Frontend (Terminal 2)

```bash
cd PrepVista_frontend
npm run dev
```

You should see:
```
  VITE v5.x.x  ready in xxx ms

  ➜  Local:   http://localhost:5173/
```

## 🎮 Using the Platform

1. **Open your browser** to `http://localhost:5173`
2. **Sign Up** with your email and password
3. **Choose a feature:**
   - 📹 **Video Analysis** - Upload or record a video to get feedback
   - 🎤 **AI Interview** - Upload your resume to generate personalized questions
   - 📄 **Resume Optimizer** - Upload resume + job description for ATS analysis

## 📊 Features Breakdown

### Video Analysis
- Records or accepts uploaded videos
- Analyzes posture, eye contact, confidence
- Transcribes speech and checks pace
- Identifies filler words
- Generates downloadable DOCX report

### AI Interview
- Extracts info from your resume
- Generates branch-specific questions
- Evaluates your answers with AI
- Provides feedback and ideal answers
- Creates comprehensive interview report

### Resume Optimizer
- Extracts text from PDF resume
- Compares against job description
- Calculates ATS compatibility score
- Identifies missing keywords
- Provides actionable improvement tips
- Generates professional PDF report

## 🔑 API Keys Required

You need **Google Gemini API keys** for AI features:

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create API keys
3. Add them to `backend/.env`:
   ```
   GEMINI_API_KEY_1=your-key-here
   GEMINI_API_KEY_2=your-key-here
   ```

## 📁 Project Structure

```
PrepVista/
├── backend/
│   ├── app.py                 # Main Flask app
│   ├── config.py              # Configuration
│   ├── models/                # Database models
│   ├── routes/                # API endpoints
│   ├── services/              # Business logic
│   ├── utils/                 # Helper functions
│   └── uploads/               # Temp file storage
├── frontend/
│   ├── src/
│   │   ├── components/        # React components
│   │   ├── services/          # API calls
│   │   └── App.tsx            # Main app
│   └── public/
├── analysis.py                # Video analysis logic
├── interview.py               # Interview logic
└── resume.py                  # Resume analysis logic
```

**Test full flow:**
1. Sign up at http://localhost:5173
2. Upload a video in Video Analysis
3. See AI-powered results!
