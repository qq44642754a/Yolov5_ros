# objectdetect_yolov5ros_pkg

## Procedure
1. Launch the ```roslaunch realsense2_camera rs_camera.launch```. The object_detection_pkg subscribes to the /camera/color/image_raw publisher for live camera feed used for object detection .For more information on setting up the camera reference the [Sensorland](https://github.com/IcebergASV/Sensorland).
2. Launch the ```roslaunch object_detection_pkg object_detection.launch``` 
``