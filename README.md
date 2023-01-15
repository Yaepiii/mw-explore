# k-explore
Multi-weight independent exploration procedures, can be user - designated areas for independent exploration

This feature pack contains the following folders:

- exploration_master : the metapackage

- exploration_msgs : defines some service and action used in explore_k

- explore_k : includes the node that contains the main exploration function

- polygon_layer : the self-defining costmap layer in order to limit exploration area

# Requirement
The package has been tested on both ROS Noetic, The following requirements are needed before installing the package:

1- You should have installed a ROS distribution (Noetic or later).

2- Created a workspace.

3- Installed the "gmapping" or other SLAM ROS package: on Ubuntu, and if you are running ROS Noetic, you can do that by typing the following command in the terminal:
```
$ sudo apt-get install ros-noetic-gmapping
```
4- Install ROS navigation stack. You can do that with the following command (assuming Ubuntu, ROS Noetic):
```
$ sudo apt-get install ros-noetic-navigation
```

# Installation
Download the package and place it inside the `/src` folder in your workspace. And then compile using `catkin_make`.

# Run
The `slam_view.launch` file in the `/launch` folder launches the pre-configured SLAM node, the move_base node, and the rviz interface. When you start a simulated environment or run the driver on a real robot, you can launch these nodes with the following command.

```
roslaunch explore_k slam_view.launch
```

You can then use the following command to start the autonomous exploration program:

```
roslaunch explore_k explore.launch
```

Click `Publish Point` at the top of RViz.

Click **a single corner** of n corners of the region (n=4 if your region is square/rectangular, to be pedantic)．

Repeat step 6 and 7 above for n times. After that you'll see a polygon with n corners.

Do the step 6 once again, then this time click anywhere within the polygon.

Finally, exploration start.
