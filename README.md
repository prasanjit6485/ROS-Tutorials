
## Installing and Configuring Your ROS Environment

Follow the below link to install ROS and Manage your environment
http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment

## Create catkin workspace

```sh
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace
$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

## Clone catkin packages

```sh
$ cd ~/catkin_ws/src
$ git clone https://github.com/prasanjit6485/ros_tutorials
$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

## Launch beginner_tutorials

### Examine simple publisher and subscriber nodes

```sh
$ roslaunch beginner_tutorials talker_listener.launch
```

### Examine simple service and client nodes

```sh
$ roscore
```

Open a new terminal, rosrun server node
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosrun beginner_tutorials add_two_ints_server.py
```

Open a new terminal, rosrun client node
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosrun beginner_tutorials add_two_ints_client.py 1 3
```

## Launch simple_arm

```sh
$ roslaunch simple_arm robot_spawn.launch
```

Open a new terminal, and send a service call to point the arm directly up towards the sky:
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosservice call /arm_mover/safe_move "joint_1: 1.57
joint_2: 1.57"
$ rosservice call /arm_mover/safe_move "joint_1: 0
joint_2: 0"
```

To view the camera image stream, open a new terminal and use the command:
```sh
$ rqt_image_view /rgb_camera/image_raw
```

## Launch capture_features_and_train

This tutorial helps us to capture features like color and surface normal for different objects located under models directory and train SVM to see the overall accuracy. The train classifier can further be used for object recognition prurpose.

```sh
$ export GAZEBO_MODEL_PATH=~/catkin_ws_tutorial/src/ROS-Tutorials/capture_features_and_train/models
$ roslaunch capture_features_and_train training.launch
```

Open a new terminal, and run capture_features node to capture feature of various model and dump the training dataset for training SVM (Support Vector Machine):
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ export GAZEBO_MODEL_PATH=~/catkin_ws_tutorial/src/ROS-Tutorials/capture_features_and_train/models
$ cd ~/catkin_ws/src/ROS-Tutorials/capture_features_and_train/train_datasets
$ rosrun capture_features_and_train capture_features.py --list 3
```

Run train_svm node to see the overall accuracy of captured feature and dump the classifier which can be used for recognition purpose:
```sh
$ cd ~/catkin_ws/src/ROS-Tutorials/capture_features_and_train/train_datasets
$ rosrun capture_features_and_train train_svm.py --list 3
```
