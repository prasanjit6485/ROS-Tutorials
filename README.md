
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

```sh
$ roslaunch beginner_tutorials talker_listener.launch
```

## Launch simple_arm

```sh
$ roslaunch simple_arm robot_spawn.launch
```

Open a new terminal, and send a service call to point the arm directly up towards the sky:

```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosservice call /arm_mover/safe_move "joint_1: 1.57 joint_2: 1.57"
$ rosservice call /arm_mover/safe_move "joint_1: 0 joint_2: 0"
```

To view the camera image stream, open a new terminal and use the command:

```sh
$ rqt_image_view /rgb_camera/image_raw
```

