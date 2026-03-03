# ✋ Real-Time Hand Tracking UDP Streaming

A real-time hand tracking system built using OpenCV and CVZone that detects 21 hand landmarks and streams the landmark data over UDP.

This project:
- Captures live webcam feed
- Detects a single hand
- Extracts 21 landmark coordinates (x, y, z)
- Converts coordinates to screen space
- Sends data via UDP socket
- Enables integration with external systems (e.g., Unity, robotics, games)

---

## 👨‍💻 Author

Sheshehang Limbu  

---

## 🚀 Features

- 🎥 Real-time webcam capture
- ✋ 21-point hand landmark detection
- 📡 UDP data transmission
- ⚡ Lightweight and fast
- 🎮 Ready for Unity / game engine integration
- 🧠 Uses MediaPipe via CVZone

---

## 🛠 Tech Stack

- Python 3.x
- OpenCV
- CVZone
- MediaPipe
- Socket (UDP)

---

## 📂 Project Structure

.
├── hand_tracking_udp.py
├── requirements.txt
└── README.md

---

## 📦 Installation

1️⃣ Create virtual environment:

python -m venv venv
source venv/bin/activate

2️⃣ Install dependencies:

pip install -r requirements.txt

Or manually:

pip install opencv-python
pip install cvzone
pip install mediapipe

---

## ▶️ Run the Project

python hand_tracking_udp.py

Press:
CTRL + C to stop

---

## 📡 How It Works

1. Webcam captures frame (1280x720)
2. CVZone detects hand
3. Extracts 21 landmarks
4. Each landmark contains:
   - x
   - y
   - z
5. Y-axis inverted to match screen coordinates
6. Data formatted as:

[x1, y1, z1, x2, y2, z2, ..., x21, y21, z21]

7. Data sent via UDP to:

127.0.0.1:5052

---

## 📡 UDP Configuration

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
serverAddressPort = ("127.0.0.1", 5052)

You can change:

- IP address (for network streaming)
- Port number

Example for Unity on same machine:
127.0.0.1

Example for another device:
"192.168.x.x"

---

## 🎮 Use Cases

- Unity hand tracking controller
- Gesture-based gaming
- Robotics control
- VR/AR interactions
- Remote motion tracking
- AI gesture recognition systems

---

## 📊 Data Format Example

[
  x1, y1, z1,
  x2, y2, z2,
  ...
  x21, y21, z21
]

Total values sent per frame:
63 values

---

## ⚠️ Notes

- Ensure webcam is connected
- Port 5052 must not be blocked
- Works best in good lighting
- Currently supports maxHands=1
- Increase to 2 for dual-hand tracking

---

## 📈 Future Improvements

- Add gesture classification
- Add TCP streaming option
- Add smoothing filter
- Add FPS counter
- Convert to WebSocket streaming
- Add GUI dashboard
- Create Unity demo project
- Deploy to Raspberry Pi

---

## 🔒 Security Notes

- UDP is connectionless (no guarantee of delivery)
- For production, consider:
  - TCP
  - Encryption
  - Authentication

---

## 🏆 Project Type

Computer Vision + Real-Time Streaming + Socket Programming  
Suitable for:
- Interactive systems
- Game development
- AI projects
- Robotics
- Portfolio demonstration

---

## 📜 License

Copyright (c) 2026 Sheshehang Limbu

All rights reserved.

This project may not be copied, modified, or distributed
without explicit permission from the author.
