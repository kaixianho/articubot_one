# open the gazebo, with maps (take note of the save .world location, got dev_ws or not?)  
'''
ros2 launch articubot_one launch_sim.launch.py world:=./dev_ws/src/articubot_one/worlds/obstacles_room.world 
'''
  

# launch slam toolbox 
'''
ros2 launch slam_toolbox online_async_launch.py slam_params_file:=./dev_ws/src/articubot_one/config/mapper_params_online_async.yaml use_sim_time:=true 
'''
  

# twist mux 
'''
ros2 run twist_mux twist_mux --ros-args --params-file ./dev_ws/src/articubot_one/config/twist_mux.yaml -r cmd_vel_out:=diff_cont/cmd_vel_unstamped  
'''
  

# nav2  
'''
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true 
'''
  

#visualize 
'''
rviz2 
'''
