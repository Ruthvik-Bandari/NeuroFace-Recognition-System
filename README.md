<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/OpenCV-4.5+-green?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV">
  <img src="https://img.shields.io/badge/dlib-19.17-orange?style=for-the-badge" alt="dlib">
  <img src="https://img.shields.io/badge/Flask-2.0+-red?style=for-the-badge&logo=flask&logoColor=white" alt="Flask">
  <img src="https://img.shields.io/badge/Deep%20Learning-ResNet-purple?style=for-the-badge" alt="Deep Learning">
</p>

<h1 align="center">🧠 NeuroFace Recognition System</h1>

<p align="center">
  <strong>Real Time Multi Face Recognition Attendance System using Deep Learning</strong>
</p>

<p align="center">
  <em>An intelligent face recognition system capable of detecting and identifying multiple faces simultaneously for automated attendance tracking</em>
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Screenshots](#-screenshots)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 🎯 Overview

**NeuroFace Recognition System** is a sophisticated deep learning based face recognition application developed as a final year undergraduate project. The system leverages dlib's ResNet model to generate 128 dimensional face embeddings, enabling accurate identification of multiple individuals in real time video streams.

The primary use case is automated attendance management, eliminating the need for manual roll calls or card based systems. The system captures face data, extracts unique facial features, and matches them against a database to automatically record attendance with timestamps.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🎭 **Multi Face Detection** | Simultaneously detect and recognize multiple faces in a single frame |
| 🔐 **128D Face Embeddings** | Uses ResNet based deep learning model for accurate face encoding |
| 📊 **68 Point Facial Landmarks** | Precise facial feature detection using dlib's shape predictor |
| ⚡ **Real Time Processing** | Live video stream processing with FPS monitoring |
| 🖥️ **GUI Face Registration** | User friendly Tkinter interface for registering new faces |
| 📝 **Automated Attendance** | Automatic attendance logging with date and timestamp |
| 🌐 **Web Dashboard** | Flask based web interface to view attendance records |
| 🔄 **Centroid Tracking** | Intelligent face tracking across video frames |
| 💾 **SQLite Database** | Persistent storage for attendance records |
| 📈 **CSV Feature Storage** | Efficient storage and retrieval of face embeddings |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        NeuroFace Recognition System                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐         │
│  │   Face         │    │   Feature       │    │   Face          │         │
│  │   Registration │───▶│   Extraction    │───▶│   Recognition   │         │
│  │   (Tkinter)    │    │   (ResNet)      │    │   & Attendance  │         │
│  └─────────────────┘    └─────────────────┘    └─────────────────┘         │
│          │                      │                      │                    │
│          ▼                      ▼                      ▼                    │
│  ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐         │
│  │   Face Images   │    │   128D Face     │    │   SQLite        │         │
│  │   Storage       │    │   Embeddings    │    │   Database      │         │
│  │   (data/)       │    │   (CSV)         │    │   (attendance)  │         │
│  └─────────────────┘    └─────────────────┘    └─────────────────┘         │
│                                                         │                   │
│                                                         ▼                   │
│                                                 ┌─────────────────┐         │
│                                                 │   Flask Web     │         │
│                                                 │   Dashboard     │         │
│                                                 └─────────────────┘         │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Technology Stack

### Core Technologies

| Technology | Purpose |
|------------|---------|
| **Python 3.8+** | Primary programming language |
| **dlib** | Face detection, landmark prediction, and face recognition |
| **OpenCV** | Image processing and video capture |
| **NumPy** | Numerical computations for face embeddings |
| **Pandas** | Data manipulation for CSV operations |

### Deep Learning Models

| Model | Description |
|-------|-------------|
| **HOG Face Detector** | Histogram of Oriented Gradients for face detection |
| **Shape Predictor 68** | 68 point facial landmark detection model |
| **ResNet Face Recognition** | Deep residual network for 128D face encoding |

### Application Framework

| Framework | Purpose |
|-----------|---------|
| **Flask** | Web application for attendance dashboard |
| **Tkinter** | Desktop GUI for face registration |
| **SQLite** | Lightweight database for attendance records |

---

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- Webcam for face capture
- CMake and C++ compiler (for dlib installation)

### Step 1: Clone the Repository

```bash
git clone https://github.com/Ruthvik-Bandari/NeuroFace-Recognition-System.git
cd NeuroFace-Recognition-System
```

### Step 2: Create Virtual Environment (Recommended)

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/macOS
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Download Pre trained Models

Download the required dlib models and place them in `data/data_dlib/`:

1. **Shape Predictor 68 Landmarks**
   - Download: [shape_predictor_68_face_landmarks.dat](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

2. **Face Recognition ResNet Model**
   - Download: [dlib_face_recognition_resnet_model_v1.dat](http://dlib.net/files/dlib_face_recognition_resnet_model_v1.dat.bz2)

```bash
# Create directory structure
mkdir -p data/data_dlib
mkdir -p data/data_faces_from_camera

# Extract downloaded models to data/data_dlib/
```

---

## 🚀 Usage

### Step 1: Register Faces

Launch the face registration GUI to capture and store face images:

```bash
python get_faces_from_camera_tkinter.py
```

**Instructions:**
1. Click **"Clear"** to remove old data (optional)
2. Enter the person's **name** in the input field
3. Click **"Input"** to create a folder for that person
4. Position your face in front of the camera
5. Click **"Save current face"** multiple times (5 to 10 images recommended)
6. Repeat for each person you want to register

### Step 2: Extract Face Features

Generate 128D face embeddings for all registered faces:

```bash
python features_extraction_to_csv.py
```

This creates `data/features_all.csv` containing face encodings for all registered individuals.

### Step 3: Run Face Recognition

Start the real time face recognition and attendance system:

```bash
python attendance_taker.py
```

**Controls:**
- Press **'Q'** to quit the application

The system will:
- Detect faces in real time
- Match faces against the database
- Automatically record attendance (one entry per person per day)

### Step 4: View Attendance Records

Launch the web dashboard to view attendance:

```bash
python app.py
```

Open your browser and navigate to `http://127.0.0.1:5000`

---

## 📁 Project Structure

```
NeuroFace-Recognition-System/
│
├── app.py                              # Flask web application
├── attendance_taker.py                 # Main face recognition module
├── features_extraction_to_csv.py       # Feature extraction script
├── get_faces_from_camera_tkinter.py    # Face registration GUI
├── requirements.txt                    # Python dependencies
├── attendance.db                       # SQLite database
│
├── data/
│   ├── data_dlib/
│   │   ├── shape_predictor_68_face_landmarks.dat
│   │   └── dlib_face_recognition_resnet_model_v1.dat
│   │
│   ├── data_faces_from_camera/         # Registered face images
│   │   ├── person_1_John/
│   │   ├── person_2_Jane/
│   │   └── ...
│   │
│   └── features_all.csv                # 128D face embeddings
│
└── templates/
    └── index.html                      # Attendance dashboard template
```

---

## ⚙️ How It Works

### 1. Face Detection
The system uses dlib's **HOG (Histogram of Oriented Gradients)** based frontal face detector to identify face regions in video frames.

### 2. Facial Landmark Detection
For each detected face, the **68 point shape predictor** identifies key facial features including:
- Eye corners and centers
- Nose tip and bridge
- Mouth corners
- Jawline contours

### 3. Face Encoding
The **ResNet based face recognition model** generates a **128 dimensional embedding vector** for each face. This compact representation captures the unique characteristics of each individual's face.

### 4. Face Matching
Recognition is performed by computing the **Euclidean distance** between the current face encoding and all stored encodings. A match is declared if the distance is below the threshold (0.4).

```python
# Euclidean distance calculation
dist = np.sqrt(np.sum(np.square(feature_1 - feature_2)))

# Match threshold
if dist < 0.4:
    # Face recognized
```

### 5. Centroid Tracking
For multi face scenarios, **centroid tracking** maintains face identity across frames by matching face positions between consecutive frames.

### 6. Attendance Recording
Upon recognition, the system records attendance with:
- Person's name
- Current time
- Current date

Duplicate entries for the same day are prevented through database constraints.

---

## 📸 Screenshots

<p align="center">
  <em>Add screenshots of your application here</em>
</p>

### Face Registration GUI
```
[Screenshot: Tkinter GUI showing camera feed and registration controls]
```

### Real Time Recognition
```
[Screenshot: Live recognition with face bounding boxes and names]
```

### Attendance Dashboard
```
[Screenshot: Flask web interface displaying attendance records]
```

---

## 🔮 Future Enhancements

- [ ] **Anti Spoofing Detection** - Prevent photo based attacks using liveness detection
- [ ] **GPU Acceleration** - CUDA support for faster processing
- [ ] **Multiple Camera Support** - Handle input from multiple video sources
- [ ] **Mobile Application** - Cross platform mobile app for attendance
- [ ] **Cloud Integration** - Sync attendance data to cloud platforms
- [ ] **Email Notifications** - Automated attendance reports via email
- [ ] **Face Mask Detection** - Recognition with partial face occlusion
- [ ] **REST API** - Expose recognition capabilities via API endpoints
- [ ] **Admin Panel** - User management and system configuration
- [ ] **Analytics Dashboard** - Attendance trends and statistics

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Ruthvik Bandari**

- GitHub: [@Ruthvik-Bandari](https://github.com/Ruthvik-Bandari)
- LinkedIn: [Connect with me](https://www.linkedin.com/in/ruthvik-nath-bandari-908b00247/)

---

<p align="center">
  <strong>⭐ Star this repository if you found it helpful!</strong>
</p>

<p align="center">
  Made with ❤️ for the Computer Science community
</p>
