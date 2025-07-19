# Traffic Monitoring System 🚦

This Traffic Monitoring System is a web-based application developed using Flask. It leverages **YOLO (You Only Look Once)** object detection to analyze traffic from video streams, track vehicle movement, and log key metrics such as speed, direction, and overspeeding status into a CSV report.

---

## 📚 Table of Contents

* [Introduction](#introduction)
* [Prerequisites](#prerequisites)
* [Installation](#installation)
* [Usage](#usage)
* [Code Explanation](#code-explanation)
* [Contributions](#contributions)

---

## 🧭 Introduction

The Traffic Monitoring System enables users to upload a `.mp4` video file and processes it using a YOLO model to detect and track vehicles. It generates:

* A real-time video stream with annotated tracking overlays.
* A CSV file (`Traffic_Report.csv`) recording vehicle statistics.

### 🔑 Key Features

* Real-time vehicle tracking and speed estimation.
* Detection of traffic violations (e.g., overspeeding).
* Clear visualization of tracking info on video.
* Web-based interface using Flask for ease of use.

---

## ✅ Prerequisites

Ensure the following are installed:

* Python 3.x
* [Flask](https://flask.palletsprojects.com/)
* [OpenCV (cv2)](https://pypi.org/project/opencv-python/)
* [Pandas](https://pandas.pydata.org/)
* [Ultralytics YOLO](https://docs.ultralytics.com/)
* [cvzone](https://pypi.org/project/cvzone/)

Install them with:

```bash
pip install flask opencv-python pandas ultralytics cvzone
```

Also required:

* A pre-trained YOLO model (e.g., `yolov8s.pt`).
* A `Coco.txt` file listing COCO class names (e.g., `car`, `bus`, `truck`).
* An empty `Traffic_Report.csv` file to store outputs.

---

## ⚙️ Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/cmushagalusa/traffic-monitoring-system.git
   cd traffic-monitoring-system
   ```

2. **Install dependencies:**

   ```bash
   pip install flask opencv-python pandas ultralytics cvzone
   ```

3. **Add YOLO model:**
   Place `yolov8s.pt` in the project directory.

4. **Prepare supporting files:**

   * `Coco.txt`: Contains one class name per line.
   * `Traffic Report.csv`: An empty file with headers (e.g., `ID, Speed, Direction, Status, Timestamp`).

---

## 🚀 Usage

1. **Run the application:**

   ```bash
   python TrackCarsSpeed.py
   ```

2. **Upload your `.mp4` video file:**
   The system will:

   * Detect and track vehicles.
   * Display real-time video with overlays.
   * Log vehicle metrics in `Traffic Report.csv`.

---

## 🧠 Code Explanation

Key logic and structure:

* **Flask App Setup:**
  Configured with secret key and file upload handling.

* **Video Upload Handling:**
  The `allowed_file()` function ensures correct file types.

* **YOLO Inference:**
  Detects vehicles using a pretrained YOLO model.

* **Tracking:**
  Vehicles are tracked frame-by-frame using a `Tracker` class.

* **Speed Calculation:**
  Based on the displacement of detected objects between frames.

* **CSV Logging:**
  Each vehicle’s ID, speed, direction, overspeeding status, and timestamp are saved.

* **Visualization:**
  Overlays lane lines, vehicle IDs, speeds, and other data on the video stream.

---

## 🙌 Contributions

* **Cajetan Songwae**
* **Clovis Mushagalusa Cirubakaderha**

