# objectdetect_yolov5ros_pkg

## Procedure run with Intel RealSense D435 Camera
1. Launch the ```roslaunch realsense2_camera rs_camera.launch```. The object_detection_pkg subscribes to the /camera/color/image_raw publisher for live camera feed used for object detection .For more information on setting up the camera reference the [Sensorland](https://github.com/IcebergASV/Sensorland).
2. Launch the ```roslaunch yolov5_ros yolo_v5.launch ```

## Procedure run in Gazebo Simulation
1. Launch the ```roslaunch topic```. The object_detection_pkg subscribes to the /camera/color/image_raw publisher for live camera feed used for object detection .For more information on setting up the camera reference the [Sensorland](https://github.com/IcebergASV/Sensorland).
2. Launch the ```roslaunch yolov5_ros sim_yolo_v5.launch ``` 
