cmake_minimum_required(VERSION 3.0.2)
project(yolov5_ros_msgs)


find_package(catkin REQUIRED COMPONENTS
  std_msgs
  message_generation
)

add_message_files(
        DIRECTORY msg
        FILES
        BoundingBox.msg
        BoundingBoxes.msg
)

generate_messages(
        DEPENDENCIES
        std_msgs
)

catkin_package(

)


include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
