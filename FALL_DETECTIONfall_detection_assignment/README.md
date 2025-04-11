# People Tracking System  
## Smart Parking & Surveillance AI Model Challenge - Task 2

This project implements a real-time people tracking system using YOLOv8 with support for video input. It identifies and tracks multiple individuals across frames with unique IDs.

---

## Key Features
- Multi-person tracking using YOLOv8
- Unique ID assignment for each detected person
- Real-time visualization of bounding boxes and IDs
- Custom object tracking logic
- Output video with tracked individuals

---

## Setup and Installation

1. Install the required packages:
```bash
pip install -r requirements.txt

2. Project Structure:
```
people_tracking_assignment/
├── data/
│   └── people.mp4        # Input video
├── tracker.py            # Custom tracking logic
├── main.py               # Detection and tracking pipeline
├── out.mp4               # Output video (auto-generated)
├── yolov8n.pt            # YOLOv8 model weights
├── requirements.txt      # Dependencies
└── README.md             # Documentation

```

## Usage

### Run the Tracking Pipeline
```bash
python main.py
```

#### Features:
- Detects people using YOLOv8
- Tracks them frame-by-frame using a custom tracker
- Displays unique bounding boxes and IDs
- Saves the result as out.mp4
- Easy-to-use interface

### Detection Logic
The system uses multiple techniques for accurate fall detection:
- Person detection using YOLOv8
- Score filtering using a detection threshold
- Object ID tracking with a custom algorithm
- Real-time annotation of frames

## Technical Details

### Model
- Base: YOLOv8 Nano (yolov8n.pt)
- Input: Video file (data/people.mp4)
- Classes:All (filtered by detection score)

### Fall Detection Parameters
- Detection threshold: 0.5
- Minimum fall duration: Color-coded ID visualization
- Output format: MP4

## Dataset
The model was trained on the Fall Detection Dataset from Roboflow:
https://universe.roboflow.com/hero-d6kgf/yolov5-fall-detection