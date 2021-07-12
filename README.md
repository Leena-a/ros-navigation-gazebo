# ros-navigation-gazebo
Steps of running the Navigation Simulation on a map previously created using SLAM for ROS robots in the Gazebo environment.


The navigation will be applied on the map created using the [ros-slam-gazebo] tutorial; make sure to follow the steps in the previous tutorial to obtain appropriate results


## Gazebo Simulation

Launch the Gazebo environment:
```
$ export TURTLEBOT3_MODEL=burger
$ source ~/catkin_ws/devel/setup.bash
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```


![TurtleBot3_Gazebo](https://user-images.githubusercontent.com/52850659/125320653-97dc2380-e344-11eb-9b17-8c7a3accca31.png)



## Navigation
Run the navigation node
```
$ export TURTLEBOT3_MODEL=burger
$ source ~/catkin_ws/devel/setup.bash
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```

### Initial Pose Estimation 

1- In the RViz menu, click `2D Pose Estimate` button.

2- Click on the map where the actual robot is located and drag the large green arrow toward the direction where the robot is facing.

3- Repeat step 1 and 2 until the LDS sensor data is overlayed on the saved map.


![2D Pose Estimate](https://user-images.githubusercontent.com/52850659/125320239-2e5c1500-e344-11eb-8c76-f223bed669d1.gif)





[ros-slam-gazebo]: <https://github.com/Leena-a/ros-slam-gazebo.git>


