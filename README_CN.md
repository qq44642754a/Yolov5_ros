# Yolov5_ros

For English version: [English](./README.md) 

提供了一个基于PyTorch-YOLOv5的[PyTorch-YOLOv5](https://github.com/ultralytics/yolov5)的ROS功能包。该功能包已在Ubuntu16.04和Ubuntu 18.04上进行了测试。

Authors: Zhitao Zheng (qq44642754@163.com)

<p>
   <img width = "1000" src="https://github.com/qq44642754a/Yolov5_ros/blob/master/yolov5_ros/yolov5_ros/media/image.png"></a>
</p>

# 开发环境：
- Ubuntu 16.04 / 18.04
- ROS kinetic/melodic
- Python>=3.6.0环境，PyTorch>=1.7

# 环境配置安装步骤：

## 安装Anaconda：

### 1.首先下载对应的安装包[Anaconda](https://www.anaconda.com/products/individual#linux)
### 2.然后执行脚本安装anaconda（文件名为下载对应的.sh文件名）

```
bash ~/Downloads/Anaconda3-2021.05-Linux-x86_64.sh
```

## 安装 Pytorch:

### 1. 首先创建python3.6以上版本的conda环境

```
conda create -n mypytorch python=3.8
```
### 2. 激活创建好的conda环境
```
conda activate mypytorch
```
### 3. 在PyTorch官网上选择指定版本安装Pytorch
Install PyTorch: https://pytorch.org/get-started/locally/
```
conda install pytorch torchvision torchaudio cpuonly -c pytorch
```


## 安装Yolov5_ROS

```
cd /your/catkin_ws/src

git clone https://github.com/qq44642754a/Yolov5_ros.git

cd yolov5_ros/yolov5

sudo pip install -r requirements.txt
```

## 基本用法

1. 首先，确保将您训练好的权重放在 [weights](https://github.com/qq44642754a/Yolov5_ros/tree/master/yolov5_ros/yolov5_ros/weights) 文件夹中。
2. `launch/yolo_v5.launch` 文件中的默认使用`yolov5s.pt这个权重文件，另外您需要在launch文件中额外修改您对应的摄像头话题名称以及是否使用Cpu选项：
```
roslaunch yolov5_ros yolo_v5.launch
```

## 特殊说明：
鉴于最近有很多人安装配置不好yolov5的环境，所以我这边配置了好了一个名为yolov5的conda环境

[百度网盘](https://pan.baidu.com/s/1Yp90Ri6owXk8wc1pfq_jcw)提取码(pjgj)。

下载好后把文件解压后放入/anaconda3/envs/文件夹下，然后运行以下指令添加到conda环境中

```
conda config --add envs_dirs 下载好的yolov5文件夹的路径
```
最后通过指令
```
conda  activate yolov5
```
来激活conda环境
