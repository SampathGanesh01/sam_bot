# SAM_BOT
## Autonomous Mobile Robot in ROS2 Foxy 

Clone the Repository to your workspace , Ros2foxy and Navigation2 stack must be installed 

1. The robot can be Launched in the Gazebo via the following commands
  To Launch the robot in the empty Gazebo world 
   --ros2 launch sam_bot launch_sim.launch.py
   To spawn the robot in the Gazebo world (please change LOcation according to your packages)
   -- ros2 launch sam_bot launch_sim.launch.py world:=/home/sampath/sam_ws/src/sam_bot/worlds/bot_world.world
   To control the Robot using teleop in the SImulated World
   -- ros2 launch sam_bot launch_sim.launch.py world:=/home/sampath/sam_ws/src/sam_bot/worlds/bot_world.world use_gazebo_control:=true


