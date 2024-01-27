# objectdetect_yolov5ros_pkg
## Description
This repository is a fork of the original [Yolov5_ros](https://github.com/qq44642754a/Yolov5_ros) package developed by Zhitao Zheng. We extend our heartfelt thanks to Zhitao Zheng for their foundational work. This project has been modified and tailored specifically for IcebergASV, enhancing its capabilities and adaptability. Significant alterations include customization for seamless integration with IcebergASV's systems and the addition of functionalities to run both with a camera setup and in a simulation environment. 
## General Requirements
- **YOLOv5 Installation**: Follow the documentation on the [YOLOv5 Installation Guide](https://app.gitbook.com/o/vtYvioW5qkBb75Erv7gv/s/PzWCobYwRWwuEeL79eAC/yolov5-setup/installing-yolov5) in GitBook. Since a virtual environment is created in the documentation **make sure to activate it in every terminal you use** for this package. 
- **YOLOV5_PATH Enviornment Variable Creation**: Follow the documentation on the [YOLOV5_PATH Enviornment Creation](https://app.gitbook.com/o/vtYvioW5qkBb75Erv7gv/s/PzWCobYwRWwuEeL79eAC/yolov5-setup/yolov5_path-environment-variable) in GitBook.
## Run with Intel RealSense D435 Camera
### Requirements
- **Intel RealSense D435 Camera Setup**: Follow the [Sensorland](https://github.com/IcebergASV/Sensorland) README.md file to complete the installation. 
### Usage
1. Open a terminal and launch the ```roslaunch realsense2_camera rs_camera.launch```. The objectdetect_yolov5ros_pkg subscribes to the **/camera/color/image_raw** topic for live camera feed used for object detection.
2. Open a new terminal and launch the ```roslaunch yolov5_ros yolo_v5.launch ```

## Run in Gazebo Simulation
### Requirements
- **Gazebo**
### Usage
1. Open a terminal and launch gazebo. The objectdetect_yolov5ros_pkg subscribes to the **/webcam/image_raw** topic for live camera feed in Gazebo Simulation used for object detection.
2. Open a new terminal and launch the ```roslaunch yolov5_ros sim_yolo_v5.launch ```

## Node Parameters
- **image_topic**: Subscribed camera topic.
- **weights_path**: Path to weights file.
- **pub_topic**: Published topic with the detected bounding boxes.
- **confidence**: Confidence threshold for detected objects.

## Original README from Yolov5_ros

The original [README_EN.md](https://github.com/IcebergASV/objectdetect_yolov5ros_pkg/blob/gazebo-simulation/README_EN.md) provides alternate detailed instructions for setting up and running the Yolov5_ros package, including prerequisites, installation steps, and basic usage.
