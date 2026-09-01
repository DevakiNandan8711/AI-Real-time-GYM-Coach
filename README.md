# 🏋️‍♂️ AI Real-time GYM Coach

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=Streamlit&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![Groq](https://img.shields.io/badge/Groq_LLM-AI-orange)

An intelligent, real-time computer vision workout assistant that acts as your personal fitness coach. Built with modern web technologies and AI, it uses your device's camera to monitor exercise form, automatically count reps, track sets, and provide proactive, low-latency audio coaching.

---

## 🌟 Key Features

- **Real-Time Pose Estimation:** Leverages cutting-edge computer vision (MediaPipe) to accurately track human body joints and angles in real-time.
- **Form Correction & Metric Tracking:** Automatically analyzes biomechanics for multiple exercises including:
  - **Squats:** Tracks knee/back angles and depth.
  - **Push-ups:** Monitors elbow angles, body alignment, and hip position.
  - **Bicep Curls:** Checks for shoulder stability and momentum swings.
  - **Shoulder Press & Lunges:** Ensures proper extension and balance.
- **Proactive AI Voice Coaching:** Integrated with the **Groq LLM API** and Text-to-Speech (TTS) to generate contextual, natural-sounding audio feedback on your form as you work out.
- **Zero-Latency WebRTC Streaming:** Uses `streamlit-webrtc` to process video streams directly in the browser without uploading private video data to a server.
- **Progress Tracking & Analytics:** Secure user authentication (Login Wall) with SQLite persistence to maintain workout history, track progress, and visualize fitness journeys.

## 🛠️ Technology Stack

- **Frontend & Web Framework:** [Streamlit](https://streamlit.io/)
- **Real-time Video Processing:** WebRTC (`streamlit-webrtc`)
- **Computer Vision:** OpenCV, MediaPipe Pose Landmarker
- **AI & Natural Language Processing:** Groq LLM API
- **Database / Persistence:** SQLite
- **Data Manipulation:** Pandas

## 🚀 How It Works

1. **Plan Your Workout:** The user logs in and sets a target exercise, rep count, and set count from the intuitive sidebar.
2. **Start Video Stream:** WebRTC securely accesses the webcam and streams frames to the backend processor.
3. **Analyze & Count:** The video processor detects key body landmarks, calculates joint angles, and determines if a rep was completed with proper form.
4. **AI Feedback:** Real-time metrics are sent to the Voice Pipeline. The Groq LLM processes this context and returns personalized encouragement or form corrections via TTS.
5. **Save & Review:** Completed sets are logged in the local database to build a comprehensive workout history.

## 💻 Running Locally

### Prerequisites
- Python 3.9 or higher
- A webcam
- [Groq API Key](https://console.groq.com/keys)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/DevakiNandan8711/AI-Real-time-GYM-Coach.git
   cd AI-Real-time-GYM-Coach
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables:**
   Create a `.env` file in the root directory and add your Groq API key:
   ```env
   GROQ_API_KEY=your_api_key_here
   ```

5. **Run the application:**
   ```bash
   streamlit run main.py
   ```

## 📈 Future Scope
- **More Exercises:** Adding support for deadlifts, bench press, and yoga poses.
- **Advanced Analytics:** Detailed workout breakdown charts and weekly summaries.
- **Mobile Support:** Optimizing the WebRTC stream for seamless mobile browser usage.

---
*If you like this project, please consider giving it a ⭐ on GitHub!*
