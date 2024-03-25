# suave-setup
Setup instructions for SUAVE companion computer

# Flash with ubuntu
- Use 20.04 LTS

# Enable SSH
- https://ubuntu.com/server/docs/service-openssh

# Install ROS
- https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html
- Create `ros` alias by adding `alias ros='source /opt/ros/humble/setup.bash'` to `~/.bash_aliases`

# Install librealsense
- https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md
- After installation, plug in a camera and run `realsense-viewer` and `rs-motion` to ensure data from the camera is being properly streamed through the API

# Install RTABMaps_ROS
- https://github.com/introlab/rtabmap_ros/tree/ros2
- Run example in https://github.com/introlab/rtabmap_ros/blob/ros2/rtabmap_examples/launch/realsense_d435i_infra.launch.py
