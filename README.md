# yolov10_speed_detector

![yolov10pic](https://github.com/user-attachments/assets/972b05c4-fe1b-44fb-b08d-5fafe1a82763)


## YOLOv10 Speed Detector

This project uses YOLOv10 for detecting and estimating the speed of objects in a video stream. By tracking object movement across frames, the detector calculates speed in real time, providing insights into object motion for applications such as traffic monitoring or sports analysis.

## Files Overview

speed.py: Main script that performs object tracking, speed estimation, and display of results.
yolotrack1file: YOLOv10 configuration file to fine-tune object tracking for speed detection.

## Features

#### Real-Time Speed Detection: 
Calculates object speed in real-time using YOLOv10's object detection and tracking capabilities.
####: Customizable Regions:
Define specific regions in the frame for speed measurement.
#### Flexible Input:
Works with pre-recorded video files or a live camera feed.
#### Frame Skipping for Efficiency
Optionally skip frames to improve performance without compromising accuracy.

## Installation
#### Clone the Repository:
bash
Copy code
git clone https://github.com/dylanross19/YOLOv10-Speed-Detector.git
cd YOLOv10-Speed-Detector
Install Requirements:

#### Install necessary Python packages from requirements.txt:
bash
Copy code
pip install -r requirements.txt
Download YOLOv10 Model Weights:

Make sure the yolov10n.pt model file is in the project directory, or download it from Ultralytics.
Usage

#### Set up Regions of Interest (Optional):
Define line_pts for the specific region in which you want to measure object speed.

#### Run the Speed Detector:
bash
Copy code
python speed.py
By default, this script opens speed.mp4 for processing. You can modify the script to use any video or webcam feed.

#### Mouse Tracking (Optional):
Hover over the frame to display current mouse coordinates. This helps to set region points accurately.

#### Exit the Program:

Press q to exit the live video display.

How It Works
Object Detection and Tracking: YOLOv10 identifies objects (e.g., cars, people) and tracks them across frames.

Speed Estimation: The SpeedEstimator class calculates speed based on the movement of object center points across frames. Speed is calculated only if the object passes within a specified region (line_pts).

Real-Time Display:

Bounding boxes and speed labels are displayed on each frame in the video feed.
Annotator draws the object track lines and displays the speed of each detected object in kilometers per hour.
Example Output

Each object is tracked with a bounding box, and the calculated speed is displayed. Tracks are color-coded to distinguish individual objects.

Configuration
line_pts: Define the region for speed calculation.
spdl_dist_thresh: Set distance threshold for calculating speed.
view_img: Set to True to display annotated frames during processing.
count: Adjust frame skipping by changing the frame counter logic in speed.py to control the performance.
Troubleshooting
Cannot Open Video: Ensure that the video file path is correct and the file format is supported by OpenCV.
Poor Speed Estimation: Adjust line_pts or spdl_dist_thresh for more accurate region-based measurements.
License
MIT License
