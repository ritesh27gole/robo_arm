# Robotic Arm

## Prerequisites
- Have Ubuntu 20.04 and ROS Noetic installed

## Cloning the repo
From home directory create /robo_arm_ws/src folder and run the following command
```
mkdir -p robo_arm_ws/src
cd robo_arm_ws/src
git clone https://github.com/ritesh27gole/robo_arm.git
```

## Updating Dependencies
```
cd ~/robo_arm_ws/
rosdep update
rosdep install --from-paths src --ignore-src -r -y --rosdistro noetic
```

## Installing Controllers For Robot
```
sudo apt-get update
sudo apt-get install ros-noetic-ros-controllers
```


## Building tutorial package
First build the project and source the setup file so that the system knows where to look for your build files
```
cd ~/robo_arm_ws
catkin build robo_arm
source devel/setup.bash
```

## Launch the robot
```
roslaunch robo_arm gazebo.launch
```


## Commands used during tutorial
useful tip: press tab to auto-complete words as you type commands
Open a new terminal to run commands for the robot

```
cd ~/robo_arm_ws
source devel/setup.bash
```
To run the main node run this command
```
rosrun robo_arm my_publisher
```

To send a command to the base
```
rostopic pub /base_controller/command std_msgs/Float64 "data: 1.0"
```

To see the ROS node tree run this command
```
rqt_graph
```
