# Suave ROS2 nodes
This documents outlines the ros topics and nodes required for GPS-denied flight

## Launch RealSense and RTABMaps
### Color
```
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_sync:=true
```
```
ros2 launch rtabmap_examples realsense_d435i_color.launch.py
```

### Infra
```
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_infra1:=true enable_infra2:=true enable_sync:=true
```
```
ros2 param set /camera/camera depth_module.emitter_enabled 0
ros2 launch rtabmap_examples realsense_d435i_infra.launch.py
```

### Stereo
```
ros2 launch realsense2_camera rs_launch.py enable_gyro:=true enable_accel:=true unite_imu_method:=1 enable_infra1:=true enable_infra2:=true enable_sync:=true
```
```
ros2 param set /camera/camera depth_module.emitter_enabled 0
ros2 launch rtabmap_examples realsense_d435i_stereo.launch.py
```

## Suave RTABMap Listener
```
cd ~/Dev/suave-ros2_ws
source ./install/setup.bash
ros2 run suave_rtabmap rtabmap_listener
```
