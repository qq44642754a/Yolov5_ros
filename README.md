# Yolov5_ros

This package provides a ROS wrapper for [PyTorch-YOLOv5](https://github.com/ultralytics/yolov5) based on PyTorch-YOLOv5. The package has been tested with Ubuntu 16.04 and Ubuntu 18.04.

**Authors**: Zhitao Zheng (<qq44642754@163.com>)

# develop environment：
- Ubuntu 16.04 / 18.04
- ROS Kinetic / Melodic
- Python>=3.6.0 environment, including PyTorch>=1.7

# Prerequisites:

## Install Anaconda:

### 1. First download the corresponding installation package [Anaconda](https://www.anaconda.com/products/individual#linux)
### 2. Then install anaconda （for example）

```
bash ~/Downloads/Anaconda3-2021.05-Linux-x86_64.sh
```
### 3. Edit the ~/.bashrc file and add it at the end

```
export PATH=/home/bai/anaconda3/bin:$PATH
```
### 4. Execute after save and exit:

```
source ~/.bashrc
```

## Install Pytorch:

### 1. First create an anaconda virtual environment for pytorch

```
conda create -n mypytorch python=3.8
```
### 2. activate the mypytorch environment

```
conda activate mypytorch
```
### 3. Install pytorch1.8 in the created pytorch environment

```
conda install pytorch torchvision cudatoolkit=10.2 -c pytorch
```
### 4. Edit ~/.bashrc file, set to use python3.8 in mypytorch environment

```
alias python='/home/bai/anaconda3/envs/mypytorch/bin/python3.8'
```
### 5. Execute after save and exit:

```
source ~/.bashrc
```

## Installation yolov5_ros

```
cd /your/catkin_ws/src

git clone https://github.com/qq44642754a/Yolov5_ros.git

cd Yolov5_ros/

sudo pip install -r requirements.txt
```

## Basic Usage

1. First, make sure to put your weights in the [models](https://github.com/qq44642754a/Yolov5_ros/tree/master/yolov5_ros/weights) folder. There are already 3 weight files in the folder: smoking recognition, mask recognition, and yolov5s.pt.
2.  The default settings (using `yolov5s.pt`) in the `launch/yolo_v5.launch` file should work, all you should have to do is change the image topic you would like to subscribe to:

```
roslaunch yolov5_ros yolo_v5.launch
```

  
  Alternatively you can modify the parameters in the [launch file](https://github.com/qq44642754a/Yolov5_ros/tree/master/yolov5_ros/launch/yolo_v5.launch), recompile and launch it that way so that no arguments need to be passed at runtime.

### Node parameters

* **`image_topic`** 

    Subscribed camera topic.

* **`weights_path`** 

    Path to weights file.

* **`pub_topic`** 

    Published topic with the detected bounding boxes.
    
* **`confidence`** 

    Confidence threshold for detected objects.

