# Homework2

Repository for Homework 2 of Robotics Labs course completed by Marco Bartone P38000237, Giacomo Caiazzo P38000236, Matteo De Simone P38000232, Nicola Monetti P38000238.

Overview
This is a report of the Homework 2 of Robotics Lab course using Docker and ROS2 with Gazebo. The repo contains the steps to download the folders from github and to run the launch file for the simulations of the built manipulator robot with the position controller, the joint space inverse dynamic torque controller or in the operational space inverse dynamics torque controller.

Usage
Open the terminal, open the container and enter into the directory where you want to download the folder, then download it with:

      $ git clone https://github.com/TeoDeSimone/De_Simone_hmw2.git

-------------------------------


To build the packages, access the ROS2 workspace and build them with:

      $ colcon build

Atfer this, use the source command:

      $ source install/setup.bash

Run the simulations of the manipulator robot using the position controller with:

      $ ros2 launch iiwa_bringup iiwa.launch.py


 In order to use the torque controller, launch the simulations with:
 
      $ ros2 launch iiwa_bringup iiwa.launch.py command_interface:="effort" robot_controller:="iiwa_arm_torque_controller"

 To perform a zero-gravity simulation, change the values of gravity in the empty.world file in the ros2_iiwa/iiwa_description/gazebo/worlds/(line 16):

      <gravity>0 0 0</gravity>
 
 Last thing, be sure to press the play button of the gazebo simulation in time, otherwise the controllers won't be loaded correctly.

--------------------------------

Open another terminal, connect to the same docker container and use the following commands in the ROS2 workspace to run the node:

      $ source install/setup.bash
      $ ros2 run ros2_kdl_package ros2_kdl_node
