# ROS tutorials

## Installing and Configuring Your ROS Environment

Follow the below link to install ROS and Manage your environment
http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment

## Create catkin workspace

$ mkdir -p ~/catkin_ws/src

$ cd ~/catkin_ws/src

$ catkin_init_workspace

$ cd ~/catkin_ws

$ catkin_make

$ source devel/setup.bash

## Create catkin packages

$ cd ~/catkin_ws/src

$ catkin_create_pkg <package_name> [depend1] [depend2] ...

$ cd ~/catkin_ws

$ catkin_make

$ source devel/setup.bash

## ROS master

$ roscore

$ roslaunch <package_name> <filename.launch>

## ROS run

$ rosrun <package_name> <node_name>

## ROS Nodes

$ rosnode list

$ rosnode info /some_node

## ROS Topics

$ rostopic list

$ rostopic info /some_topic

$ rostopic echo /some_topic

## ROS Messages

$ rosmsg list

$ rosmsg info some_msg

## ROS Services

$ rosservice list

$ rosservice call <service_name> <args>

## ROS Parameters

$ rosparam list

$ rosparam set <param_name> <value>

$ rosparam get <param_name>

