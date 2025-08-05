# ROS2 TurtleBot3

First we need to install turtlebot packages and dependencies from the official docs:
  
```
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/
```

## Gazebo Simulation

The following commands sets the type of the robot and starts the gazebo simulation:
  
```
export TURTLEBOT3_MODEL=waffle
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

Now we can run the following commands in a new terminal window to control the robot in the gazebo simulation:
  
```
export TURTLEBOT3_MODEL=waffle
ros2 run turtlebot3_teleop teleop_keyboard
```
  
## Screenshot
  
<img width="1800" height="800" alt="image" src="https://github.com/user-attachments/assets/c82ec955-8688-430f-bce3-95ffc193aa74" />

## SLAM Simulation
  
The following commands sets the type of the robot and starts the SLAM simulaton:
```
export TURTLEBOT3_MODEL=burger
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```
  
Now in a new terminal window we need to run the following command to start the SLAM node:
  
```
export TURTLEBOT3_MODEL=waffle
ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
```

Now to control the robot in the simulation we need to run the following commands:
  
```
export TURTLEBOT3_MODEL=waffle
ros2 run turtlebot3_teleop teleop_keyboard
```

Lastly, to save the SLAM map we need to run the following command in a new terminal:

```
ros2 run nav2_map_server map_saver_cli -f ~/map
```

## Screenshot
  
<img width="750" height="680" alt="image" src="https://github.com/user-attachments/assets/dc4f3261-aed3-4803-8256-934607a2e81e" />
