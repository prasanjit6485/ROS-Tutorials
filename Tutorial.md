# ROS tutorials

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

## Create catkin packages

```sh
$ cd ~/catkin_ws/src
$ catkin_create_pkg <package_name> [depend1] [depend2] ...
$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

## ROS master

```sh
$ roscore
$ roslaunch <package_name> <filename.launch>
```

## ROS run

```sh
$ rosrun <package_name> <node_name>
```

## ROS Nodes

```sh
$ rosnode list
$ rosnode info /some_node
```

## ROS Topics

```sh
$ rostopic list
$ rostopic info /some_topic
$ rostopic echo /some_topic
```

## ROS Messages

```sh
$ rosmsg list
$ rosmsg info some_msg
```

## ROS Services

```sh
$ rosservice list
$ rosservice call <service_name> <args>
```

## ROS Parameters

```sh
$ rosparam list
$ rosparam set <param_name> <value>
$ rosparam get <param_name>
```

## ROS Publishers

Publishers allow a node to send messages to a topic, so that data from the node can be used in other parts of the ROS system. In Python, ROS publishers typically have the following definition format, although other parameters and arguments are possible:
```sh
pub = rospy.Publisher("/topic_name", message_type, queue_size=size)
```

Once the publisher has been created as above, a message with the specified data type can be published as follows:
```sh
pub.publish(message)
```

## ROS Subscribers

Subscriber enables your node to read messages from a topic, allowing useful data to be streamed into to the node. In Python, ROS subscribers frequently have the following format, although other parameters and arguments are possible:
```sh
sub = rospy.Subscriber("/topic_name", message_type, callback_function)
```

## ROS Services

### Defining Services
A ROS service allows request/response communication to exist between nodes. Within the node providing the service, request messages are handled by functions or methods. Once the requests have been handled successfully, the node providing the service sends a message back to the requester node. In Python, a ROS service can be created using the following definition format:
```sh
service = rospy.Service('service_name', serviceClassName, handler)
```

### Using Services
On the other hand, to use a ROS service from within another node, you will define a ServiceProxy, which provides the interface for sending messages to the service:
```sh
service_proxy = rospy.ServiceProxy('service_name', serviceClassName)
```
