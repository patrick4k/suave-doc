# suave-setup
Setup instructions for SUAVE companion computer

## Flash with ubuntu
- Use 20.04 LTS

## Update apt
```
sudo apt update
sudo apt upgrade
```

## Enable SSH
- https://ubuntu.com/server/docs/service-openssh

## Install ROS
- https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html
- Make sure you install the development tools!
- Create `ros` alias by adding `alias ros='source /opt/ros/humble/setup.bash'` to `~/.bash_aliases`

## Install librealsense
- https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md
- After installation, plug in a camera and run `realsense-viewer` and `rs-motion` to ensure data from the camera is being properly streamed through the API

## Install RTABMaps_ROS
- https://github.com/introlab/rtabmap_ros/tree/ros2
- Run example in https://github.com/introlab/rtabmap_ros/blob/ros2/rtabmap_examples/launch/realsense_d435i_infra.launch.py

## Install git
```
sudo apt install git
```

## Clone suave repos
```
cd ~
mkdir Dev
cd Dev
git clone https://github.com/patrick4k/suave-controller.git
git clone https://github.com/patrick4k/suave-ros2_ws.git
```

## Install python dependencies
```
sudo apt install python3-pip
pip install mavsdk
```

## Add dialout permission
- Add dialout to user
```
sudo usermod -a -G dialout $USER
sudo reboot
```
- Verify dialout was applied `groups $USER`

## Update connection string
- Search for PX4 in the serial connections, connection should look like this: `usb-FTDI_FT232R_USB_UART_A10L1BX5-if00-port0`
- Update connection_string in suave-controller and suave-ros2_ws
