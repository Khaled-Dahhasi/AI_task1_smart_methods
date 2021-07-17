AI_task1_smart_methods
# Installation and running robot arm package on ROS
This is my first task in the AI route on [Smart Methods'](https://s-m.com.sa/index.html) training program.

## Task description:
In this task i will install ubuntu version 18.04 on a linux virtual machine and then install ROS and run the [Arduino robot arm packages](https://github.com/smart-methods/arduino_robot_arm)



## Steps
1. Downloading [Ubuntu 18.04 image](https://releases.ubuntu.com/18.04.5/) to use with [virtual box](https://www.virtualbox.org/).
Readng a tutorial is adviced, i recommend reading [this](https://www.wikihow.com/Install-Ubuntu-on-VirtualBox)
2. Installing ROS (melodic version recommended for this Ubuntu version) using [the official tutorial](http://wiki.ros.org/melodic/Installation/Ubuntu)
3. Now we [install catkin](https://wiki.ros.org/catkin#Installing_catkin) and [make a new Workspace](http://wiki.ros.org/catkin/Tutorials/create_a_workspace) where we use the ROS packages in.
4. Installing the package using these steps: ![](https://user-images.githubusercontent.com/85564881/126035873-a1a3419b-7f6e-4d76-b37c-59b9a7af6c97.png) 
I struggled to do the above step correctly untill i did these additonal steps which i thank [Mo7ammed-saleh](https://github.com/mo7ammed-saleh) for putting them in his tutorial.
- open bashrc using `sudo nano ~/.bashrc`
- scroll to the bottom of the file and add the following: `source /home/(put name of your Ubuntu username here)/catkin_ws/devel/setup.bash` 
- press `ctrl + o`
- enter the command:`source ~/.bashrc`

5- Now we launch the Rviz simulation with this commmand `roslaunch robot_arm_pkg check_motors.launch`
![Controlling the robot arm with joint_state_publisher](https://user-images.githubusercontent.com/85564881/126036249-7b40158b-a700-487e-88b0-25d505b9c06e.JPG)

6- we can also [use an arduino](https://maker.pro/arduino/tutorial/how-to-use-arduino-with-robot-operating-system-ros) with our ROS bot. after downloading the arduino IDE code it using [the arduino code](https://github.com/smart-methods/arduino_robot_arm/blob/main/arduino_code/arduino_code.ino) given in the git hub.

7- Launching Gazebo simulator with Rviz and joint states control.
![Steps to launch Gazebo](https://user-images.githubusercontent.com/85564881/126039813-09feabc4-30a2-48b2-9aa7-4872e699d3bf.png)

here is an example of the simulation using joint state controller 
![robot_arm_Rviz-gazebo](https://user-images.githubusercontent.com/85564881/126039016-6cba9446-98a5-4b83-8a77-fee2d6aaa245.gif)

7- Using moveit which is an ROS package used for motion planning, kinematics, control and navigation. 
we use the command `roslaunch moveit_pkg demo.launch`
![moveit](https://user-images.githubusercontent.com/85564881/126040208-36549aa2-ca8f-4c63-a695-fd0a4432c123.gif)

and with this the task is done!

