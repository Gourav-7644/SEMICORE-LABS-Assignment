# Smart Parking Detection System  
## Smart Parking & Surveillance AI Model Challenge - Task 1

This project implements a real-time smart parking space detection system using YOLOv8. It detects vehicles and monitors the occupancy status of predefined parking zones in a video feed.
---

## Key Features
-Detects parked vehicles using YOLOv8
-Monitors 12 user-defined parking zones
-Visual feedback with bounding boxes and slot outlines
-Color-coded slot status:
🟥 Red: Occupied
🟩 Green: Available
-Displays real-time count of available parking slots
---
## 📊 Performance Metrics

### 🚗 Parking Detection

| **Metric**          | **Value**                  |
|---------------------|----------------------------|
| **Accuracy**        | 97.47% ✅ *(exceeds required 90%)* |
| **Precision**       | 92.42%                     |
| **Recall**          | 100.00%                    |
| **Processing Speed**| 0.61 FPS                   |

## Setup and Installation

1. Install the required packages:
```bash
pip install -r requirements.txt

2. Project Structure:
```
Smart_parking_detection/
├── parking1.mp4          # Input video
├── coco.txt              # Class labels (COCO dataset)
├── yolov8s.pt            # YOLOv8 model weights
├── main.py               # Detection and parking logic
├── requirements.txt      # Python dependencies
└── README.md             # Documentation (this file)
```

## Usage

### Run the Parking Detector
```bash
python main.py
##Controls:
-Press ESC to exit the video preview
```
#### Features:
-Detects parked cars using YOLOv8 object detection
-Monitors 12 predefined parking zones in a video feed
-Determines occupancy status based on object center points
-Highlights occupied slots in red and vacant ones in green
-Counts and displays the number of free parking spaces in real-time
-Easy-to-use interface with frame-by-frame analysis

### Detection Logic
-Model: YOLOv8 Small (yolov8s.pt)
-Object Detection:
   Class: Car
   Threshold: Set internally by YOLO
-Center Point Calculation: Used for zone check
-Zone Verification: Each slot is defined by a 4-point polygon
-Slot Coloring:
   Red if occupied (vehicle center lies within the zone)
   Green if free

## Technical Details

### Model
-Base: YOLOv8 Small (yolov8s.pt)
-Input: Parking lot video (parking1.mp4)
-Classes: All (filtered to car class only)

### Parking Slot Detection Parameters
-Detection threshold: Default YOLO confidence
-Zone monitoring: 12 hardcoded polygon regions
-Occupancy logic: Based on object center point inside zone
-Output: Annotated video feed displayed via OpenCV (optional save available)

## Dataset
This implementation uses a pre-trained YOLOv8 model (yolov8s.pt) trained on the COCO dataset, which includes car, truck, and other vehicle classes: https://github.com/ultralytics/ultralytics
