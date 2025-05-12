#  MacV Object Tracker Task

This project implements a multi-object tracking application for analyzing video footage. It identifies objects, tracks them with consistent IDs, visualizes movement trails, and computes presence durations for each object.

---

##  Demo

Open `result.html` to view the output video with tracking visualization embedded in a browser.

---

## Features

- ✅ Object detection using thresholding and contour detection
- ✅ Multi-object tracking using a custom Centroid Tracker
- ✅ Bounding boxes, centroids, and movement trail visualization
- ✅ Frame-wise calculation of time spent by each object
- ✅ Export to MP4 (H.264) format compatible with HTML5 video tag
- ✅ Sample HTML file to display output video in browser

---

## Tech Stack

| Component       | Tool / Library     |
|----------------|--------------------|
| Language        | Python 3.x         |
| Detection       | OpenCV thresholding & contour detection |
| Tracking        | Custom Centroid Tracker |
| Visualization   | OpenCV (cv2.circle, cv2.putText, etc.) |
| Export Format   | MP4 using H.264 (`avc1`) codec |
| Browser Support | HTML5 `<video>` tag |

---

## Approach

### 1. **Object Detection**
- Applied grayscale + thresholding
- Used contour detection to localize bright moving objects

### 2. **Object Tracking**
- Used a Centroid Tracker to assign and maintain consistent IDs
- Objects matched using Euclidean distance

### 3. **Metric Calculation**
- Each object’s first frame was logged
- Duration = `(last frame - entry frame) / FPS`

### 4. **Visualization**
- Bounding box (optional), centroid, and trail lines drawn on each frame
- Object ID rendered near centroid

### 5. **Export & HTML Display**
- Video saved in MP4 format using H.264 codec (`avc1`)
- HTML file embeds the video using `<video>` tag

---

## Files

| File | Description |
|------|-------------|
| `Assignment.py` | Main tracking pipeline |
| `output_tracked_video.mp4` | Output video with annotations |
| `result.html` | HTML file to view video |
| `README.md` | This file |
| `Documentation.pdf` | Technical explanation of approach |

---

## 📝 How to Run

```bash
pip install opencv-python numpy
python Assignment.py
