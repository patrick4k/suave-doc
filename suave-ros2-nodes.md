# Suave ROS2 nodes
This documents outlines the ros topics and nodes required for GPS-denied flight

## Launch RealSense and RTABMaps
NOTE: `ros2 launch realsense2_camera` will issue a warning "Hardware Notification:Motion Module failure,1.7114e+12,Error,Hardware Error" the first time it launchs, to fix this `ctrl+c` then relaunch it.
### Color
```
ros
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_sync:=true
```
```
ros
ros2 launch rtabmap_examples realsense_d435i_color.launch.py
```

### Infra
```
ros
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_infra1:=true enable_infra2:=true enable_sync:=true
```
```
ros
ros2 param set /camera/camera depth_module.emitter_enabled 0
ros2 launch rtabmap_examples realsense_d435i_infra.launch.py
```

### Stereo
```
ros
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_infra1:=true enable_infra2:=true enable_sync:=true
```
```
ros
ros2 param set /camera/camera depth_module.emitter_enabled 0
ros2 launch rtabmap_examples realsense_d435i_stereo.launch.py
```

## Suave RTABMap Listener
```
ros
cd ~/Dev/suave-ros2_ws
source ./install/setup.bash
ros2 run suave_rtabmap rtabmap_listener
```
