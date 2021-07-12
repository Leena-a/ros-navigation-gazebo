# ros-navigation-gazebo

Steps of running the navigation stack on RViz to initialize the localization system, send goals to the robot on a map previously created using SLAM for ROS robots in the Gazebo environment.


The navigation will be applied on the map created using the [ros-slam-gazebo] tutorial; make sure to follow the steps in this tutorial to obtain appropriate results.


## Gazebo Simulation

Launch the Gazebo environment:
```
$ export TURTLEBOT3_MODEL=burger
$ source ~/catkin_ws/devel/setup.bash
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```


![turtlebot3_gazebo](https://user-images.githubusercontent.com/52850659/125345074-bf40e980-e360-11eb-87b9-9f0ae2857841.jpg)


## Navigation
Run the navigation node
```
$ export TURTLEBOT3_MODEL=burger
$ source ~/catkin_ws/devel/setup.bash
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```

### Initial Pose Estimation

`2D Pose Estimate`: Allows the user to initialize the localization system used by the navigation stack by setting the pose of the robot in the world.

1- In the RViz menu, click `2D Pose Estimate` button.

2- Click on the map where the actual robot is located and drag the large green arrow toward the direction where the robot is facing.

3- Repeat step 1 and 2 until the LDS sensor data is overlayed on the saved map.


![2D Pose Estimate](https://user-images.githubusercontent.com/52850659/125320239-2e5c1500-e344-11eb-8c76-f223bed669d1.gif)

Launch keyboard teleoperation node to precisely locate the robot, and narrow down the estimated location of the TurtleBot3 on the map.
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
Then, terminate the keyboard teleoperation node using `Ctrl` + `C`.


### Set Navigation Goal

`2D Nav Goal`: Allows the user to send a goal to the navigation by setting a desired pose for the robot to achieve.

1- Click the `2D Nav Goal` button in the RViz menu.


2- Click on the map to set the robot's destination and drag the green arrow toward the direction where the robot will be facing.


![2D_Nav_Goal](https://user-images.githubusercontent.com/52850659/125341937-e09fd680-e35c-11eb-8e0f-f50ff88fa48c.gif)


As soon as all the parameters x, y, θ are set, TurtleBot3 will start moving to the destination and manages to avoid obstacles as can be seen.


[ros-slam-gazebo]: <https://github.com/Leena-a/ros-slam-gazebo.git>


