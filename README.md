# 🎓 Facial Recognition — Campus Entry System

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-red)
![Flask](https://img.shields.io/badge/Flask-2.x-black)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

> AI-powered facial recognition system for automated campus entry,
> using HOG algorithm and Neural Networks for real-time face detection
> and student identification.

---

## 📊 Results

| Metric | Value |
|---|---|
| Algorithm | HOG (Histogram of Oriented Gradients) |
| Feature Vector Size | **128 values per face** |
| Input | Live webcam / video stream |
| Database | MongoDB (student profiles) |
| Deployment | Flask web application |

---

## 🎯 Overview

This project implements an automated student attendance system using
facial recognition. When a student enters the campus, the system
detects their face via webcam, extracts a 128-value HOG feature vector,
and matches it against the student database to automatically mark
their presence.

**Key features:**
- Real-time face detection using HOG algorithm
- 128-dimensional feature vector extraction per face
- Student database stored and managed in MongoDB
- Two operating modes: Entry mode and Presence mode
- Web interface built with Flask for live monitoring
- Automatic attendance update on face match

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **OpenCV** — face detection and video stream processing
- **HOG Algorithm** — feature extraction (128-value vector)
- **Neural Network** — face recognition and classification
- **MongoDB** — student database management
- **Flask** — web application and live dashboard
- **RaspberryPi** *(optional)* — embedded deployment

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/rowan26/facial-recognition-campus-entry
cd facial-recognition-campus-entry
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Setup MongoDB
```bash
# Start MongoDB locally
mongod --dbpath /data/db
```

### 4. Run the application
```bash
# Mode 1 — Entry mode (webcam live)
python face_recognition_video_present.py

# Mode 2 — Add new student to database
python face_recognition_action.py
```

---

## 📁 Project Structure
facial-recognition-campus-entry/
│
├── ai-source/
│   ├── face_recognition_action.py       # Encode faces → save to DB
│   ├── face_recognition_video_absent.py # Detect & mark absent students
│   └── face_recognition_video_present.py# Live recognition pipeline
│
├── web-app/
│   ├── app.py                           # Flask web server
│   ├── templates/                       # HTML pages
│   └── static/                          # CSS / JS assets
│
├── docs/
│   └── presentation.pdf                 # Full project documentation
│
└── README.md

---

## 🧠 How It Works
Webcam Input
│
▼
Face Detection (OpenCV)
│
▼
HOG Feature Extraction → 128-value vector
│
▼
Neural Network Classifier
│
▼
MongoDB Lookup → Student Match
│
▼
Attendance Updated ✅

---

## 🖥️ Operating Modes

**Mode Entry** — Student is physically at the establishment. The system
detects their face live, matches it against the database and
automatically updates their attendance record.

**Mode Presence** — Student is away from the establishment. The system
still processes their profile from the database for remote tracking.

---

## 📌 Limitations & Future Work

- Currently works on a single fixed camera setup
- Future: multi-camera support for larger campuses
- Future: add liveness detection to prevent photo spoofing
- Future: deploy on RaspberryPi for embedded standalone system

---

## 👤 Author

**Rowan HADJAZ**
- GitHub: [@rowan26](https://github.com/rowan26)
- LinkedIn: [rowan-hadjaz](https://linkedin.com/in/rowan-hadjaz)
