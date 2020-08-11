# multi_slam_karto

This is a centralized multi-robot SLAM implementation. All scans of robots are optimized in a graph, instead of using the map-merge method to generate global map.

This work contains a modified version of [SLAM Karto](https://github.com/ros-perception/slam_karto) and [Open Karto](https://github.com/ros-perception/open_karto). The gazebo environment uses [rrt_exploration_tutorials](https://github.com/hasauino/rrt_exploration_tutorials).

![multi_slam_karto](./demo/demo.gif)

## Prerequisites

This package has been tested on Ubuntu16.04 with ROS Kinetic. As far as I know, Kobuki packages in step 4 can't be installed correctly on ROS Melodic. 

(1) You should have installed a ROS distribution with gazebo.

(2) Install ROS navigation stack.

`$ sudo apt-get install ros-melodic-navigation`

(3) Install eigen.

(4) Install Kobuki robot packages

`sudo apt-get install ros-kinetic-kobuki ros-kinetic-kobuki-core ros-kinetic-kobuki-gazebo`

## Known Issue / TO DO List

1. The static global cost map cannot be loaded correctly.

2. Add threshold at initial optimization between robots. 
