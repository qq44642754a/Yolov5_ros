# objectdetect_yolov5ros_pkg
## Description
This repository is a fork of the original [Yolov5_ros](https://github.com/qq44642754a/Yolov5_ros) package developed by Zhitao Zheng. We extend our heartfelt thanks to Zhitao Zheng for their foundational work. This project has been modified and tailored specifically for Iceberg ASV, enhancing its capabilities and adaptability. Significant alterations include customization for seamless integration with IcebergASV's systems and the addition of functionalities to run both with a camera setup and in a simulation environment. 
## General Requirements
- **YOLOv5 Installation**: Follow the documentation on the [YOLOv5 Installation Guide](https://app.gitbook.com/o/vtYvioW5qkBb75Erv7gv/s/PzWCobYwRWwuEeL79eAC/yolov5-setup/installing-yolov5) in GitBook. Since a virtual environment is created in the documentation **make sure to activate it in every terminal you use** for this package. 
- **YOLOV5_PATH Enviornment Variable Creation**: Follow the documentation on the [YOLOV5_PATH Enviornment Creation](https://app.gitbook.com/o/vtYvioW5qkBb75Erv7gv/s/PzWCobYwRWwuEeL79eAC/yolov5-setup/yolov5_path-environment-variable) in GitBook.
## sim_yolo_v5.launch and yolov5_launch Launch File Setup
### Paramter use_cpu
- **Purpose**: This parameter decides whether the CPU (Central Processing Unit) is utilized for specific computations or processes within the system.
- **Options**:
  - **true**:  Designates the CPU as the primary processing unit. This is suitable for systems that do not have a powerful GPU (Graphics Processing Unit) or for operations that do not demand intensive graphical computation.
  - **false**: Directs the system to employ other available processing units, typically a GPU, for computation. This option is more appropriate for graphically intensive tasks or when the objective is to reduce the CPU load.
- **Impact of Setting**:
  - **True**: May lead to decreased performance in graphically demanding tasks but offers better compatibility with systems that lack high-end GPUs.
  - **False**: Boosts performance for graphically intensive operations but can result in increased CPU load.

- **Specific Use-Case for NVIDIA Jetson TX2:**
  - When operating on the NVIDIA Jetson TX2, it is recommended to set **use_cpu** to **false**. The TX2 is equipped with a capable GPU, making it well-suited for handling tasks that are graphically demanding. By setting this parameter to **false**, the system leverages the TX2's GPU, thereby optimizing performance for tasks that require substantial graphical processing. This setting is particularly advantageous in performance-critical applications, such as in competitive environments, where maximizing the efficiency and capabilities of the GPU is crucial.
### Parameter visualize_object_detect
- **Options**:
  - **true**: Activates the visualization of object detection. Ideal for development, debugging, and accuracy verification of the object detection system.
  - **false**:  Deactivates the visualization functionality. Optimal for production environments or when the primary objective is to reduce computational load.
## Run with Intel RealSense D435 Camera
### Requirements
- **Intel RealSense D435 Camera Setup**: Follow the [Sensorland](https://github.com/IcebergASV/Sensorland) README.md file to complete the installation. 
### Usage
1. Open a terminal and launch the ```roslaunch realsense2_camera rs_camera.launch```. The objectdetect_yolov5ros_pkg subscribes to the **/camera/color/image_raw** topic for live camera feed used for object detection.
2. Reminder to activate your virtual enviornment ```source yolov5_env/bin/activate```
3. Open a new terminal and launch the ```roslaunch yolov5_ros yolo_v5.launch ```

## Run in Gazebo Simulation 
### Requirements
- **Gazebo**
### Usage
1. Open a terminal and launch gazebo. The objectdetect_yolov5ros_pkg subscribes to the **/webcam/image_raw** topic for live camera feed in Gazebo Simulation used for object detection.
2. Reminder to activate your virtual enviornment ```source yolov5_env/bin/activate```
3. Open a new terminal and launch the ```roslaunch yolov5_ros sim_yolo_v5.launch ```

## Node Parameters
- **image_topic**: Subscribed camera topic.
- **weights_path**: Path to weights file.
- **pub_topic**: Published topic with the detected bounding boxes.
- **confidence**: Confidence threshold for detected objects.

## Original README from Yolov5_ros

The original [README_EN.md](https://github.com/IcebergASV/objectdetect_yolov5ros_pkg/blob/gazebo-simulation/README_EN.md) provides alternate detailed instructions for setting up and running the Yolov5_ros package, including prerequisites, installation steps, and basic usage.
