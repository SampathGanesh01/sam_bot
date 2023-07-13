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
![image](https://github.com/SampathGanesh01/sam_bot/assets/84275114/84920e95-b506-4a52-9979-159978fda593)

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
![image](https://github.com/SampathGanesh01/sam_bot/assets/84275114/8b3f1f55-f4d1-4157-8c36-a0eedfa05e69)

### 4.Wypoint Follower 

Before Going to follow waypoints we need to create a map 
we can create a map using SLAMTOOLBOX and can even able to do autonomous Navigation using nav2 
To create  a map use below command 
```
ros2 launch sam_bot online_async.launch.py use-sim_time:=True
```
Save the map using rviz 

To autonomously Navigating using saved map 
![image](https://github.com/SampathGanesh01/sam_bot/assets/84275114/f56a3977-a4c3-486f-a60f-e91519069115)
```
ros2 launch nav2_bringup bringup_launch.py use_sim_time:=True map:=/home/sampath/sam_ws/src/sam_bot/maps/my_map.yaml
```
The map has been cleaned using GIMP and saved in the Maps folder 
To do : 
Well while creation of map , The robot doesnot have stable motion may be due to inadequate stablity the tfs are not stable 
Need to develop script for waypoint follower 
