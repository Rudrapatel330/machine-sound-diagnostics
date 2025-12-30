# Machine Sound Diagnostics 🔊⚙️

**Machine Sound Diagnostics** is a machine fault detection system that analyzes sound recordings to determine if a machine has a fault or not. The project includes a Python-based ML backend and a full Android application that sends `.wav` audio recordings to the backend for analysis.

🌐 **GitHub Repository:**  
https://github.com/Rudrapatel330/machine-sound-diagnostics.git

---

## 📌 Overview

This project uses sound recordings to detect machine faults. An Android app captures or uploads `.wav` audio files of machine sounds and sends them to a Python backend, where machine learning detects whether a fault is present.

The backend is deployed on platforms such as Hugging Face Spaces, and the Android app communicates via API.

---

## 💡 Features

### 🔹 Machine Learning Backend
- Python-based sound classification model
- Takes `.wav` audio as input
- Uses audio preprocessing techniques (MFCC, spectrogram, etc.)
- Predicts Fault / No Fault
- Easily expandable to multiple machine parts

### 📱 Android Application
- Records or uploads `.wav` machine audio
- Sends audio data to ML backend server
- Displays prediction results in app UI

---

## 📁 Project Structure

