# objectdetect_yolov5ros_pkg
## General Requirements
- **YOLOv5 Installation**: Follow the documentation on the [YOLOv5 Installation Guide](https://app.gitbook.com/o/vtYvioW5qkBb75Erv7gv/s/PzWCobYwRWwuEeL79eAC/installing-yolov5) in GitBook.
- **YOLOV5_PATH Enviornment Variable Creation**: Follow the documentation on the [YOLOV5_PATH Enviornment Creation]() in GitBook.
## Run with Intel RealSense D435 Camera
### Requirements
- **Intel RealSense D435 Camera Setup**: Follow the [Sensorland](https://github.com/IcebergASV/Sensorland) README.md file to complete the installation. 
### Usage
1. Open a terminal and launch the ```roslaunch realsense2_camera rs_camera.launch```. The object_detection_pkg subscribes to the /camera/color/image_raw publisher for live camera feed used for object detection.
2. Open a new terminal and launch the ```roslaunch yolov5_ros yolo_v5.launch ```

## Run in Gazebo Simulation
### Requirements
- **Gazebo**
### Usage
1. Open a terminal and launch the ```roslaunch topic```. The object_detection_pkg subscribes to the /webcam/image_raw publisher for live camera feed in Gazebo Simulation used for object detection.
2. Open a new terminal and launch the ```roslaunch yolov5_ros sim_yolo_v5.launch ``` 
