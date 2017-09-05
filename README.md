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

$ git clone https://github.com/prasanjit6485/ros_tutorials or catkin_create_pkg <package_name> [depend1] [depend2] ...

$ cd ~/catkin_ws

$ catkin_make

$ source devel/setup.bash

## ROS master

$ roscore

$ roslaunch <package_name> <filename.launch>

$ roslaunch beginner_tutorials talker_listener.launch

$ roslaunch simple_arm robot_spawn.launch

## Nodes

## Topics

## Messages

## Services

## Parameters

