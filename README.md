## open the gazebo, with maps (take note of the save .world location, got dev_ws or not?)  
```
ros2 launch articubot_one launch_sim.launch.py world:=./dev_ws/src/articubot_one/worlds/obstacles_room.world 
```
## launch slam toolbox - for mapping and localization
```
ros2 launch slam_toolbox online_async_launch.py slam_params_file:=./dev_ws/src/articubot_one/config/mapper_params_online_async.yaml use_sim_time:=true 
```
## twist mux - to allow control from keyboard and nav2 at the same time
```
ros2 run twist_mux twist_mux --ros-args --params-file ./dev_ws/src/articubot_one/config/twist_mux.yaml -r cmd_vel_out:=diff_cont/cmd_vel_unstamped  
```
## nav2 - navigation 2 tool for self navigation of robot 
```
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true 
```
## visualize with rviz2 
```
rviz2
```
## keyboard control 
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```
