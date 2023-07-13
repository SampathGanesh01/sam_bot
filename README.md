# SAM_BOT
## Autonomous Mobile Robot in ROS2 Foxy 

Clone the Repository to your workspace , Ros2foxy and Navigation2 stack must be installed 

### 1. The robot can be Launched in the Gazebo via the following commands

   
  To Launch the robot in the empty Gazebo world
  ```
   ros2 launch sam_bot launch_sim.launch.py
```
 You can control the robot using 
 ```
rqt_robot_steering
```


### 2. BOT WORLD 

   To spawn the robot in the Gazebo world (please change LOcation according to your packages)
   ```
   ros2 launch sam_bot launch_sim.launch.py world:=/home/sampath/sam_ws/src/sam_bot/worlds/bot_world.world
```
   To control the Robot using teleop in the SImulated World
   ```
   ros2 launch sam_bot launch_sim.launch.py world:=/home/sampath/sam_ws/src/sam_bot/worlds/bot_world.world use_gazebo_control:=true
```
![image](https://github.com/SampathGanesh01/sam_bot/assets/84275114/533bd083-1c84-4f9c-a38c-f1afc826d7d5)
### 3.Laser filter 

To see the Laser data which is filtered you need to on the General robot and then also need to run filter node which will give us filtered odometry data 

   To spawn  the Robot  in the SImulated World
```
   ros2 launch sam_bot launch_sim.launch.py world:=/home/sampath/sam_ws/src/sam_bot/worlds/bot_world.world use_gazebo_control:=true
```
To run the filter node 
```
python3 laser_filter.py
```
