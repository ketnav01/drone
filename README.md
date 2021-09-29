# drone

Pre requisite

mkdir -p ~/hector_group2_ws/src

cd ~/hector_group2_ws/

wstool init src https://raw.github.com/tu-darmstadt-ros-pkg/hector_quadrotor/kinetic-devel/tutorials.rosinstall

sudo apt install ros-melodic-gazebo-ros-control

sudo apt install ros-melodic-ros-control

sudo apt install ros-melodic-geographic-info

sudo apt install ros-melodic-joy

sudo apt install ros-melodic-teleop-twist-keyboard

sudo apt-get install libqt4-dev

catkin_make

To test:

cd ~/hector_group2_ws

source devel/setup.bash

roslaunch hector_quadrotor_demo outdoor_flight_gazebo.launch

on another terminal:

rosservice call /enable_motors "enable: true"

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

Part 2:

cd ~/hector_group2_ws/src

git clone https://github.com/ketnav01/drone.git

cd ..

source devel/setup.bash

catkin_make

roslaunch hector_quadrotor_demo outdoor_flight_gazebo.launch

On another terminal:

cd ~/hector_group2_ws

source devel/setup.bash

rosservice call /enable_motors "enable: true"

rosrun udm_group2_drone_control altitude_service.py

On another terminal:

cd ~/hector_group2_ws

source devel/setup.bash

rosservice call /udm_altitude_service "altitude: data: '2'"

Part 3:

cd ~/hector_group2_ws

source devel/setup.bash

roslaunch hector_quadrotor_demo outdoor_flight_gazebo.launch

On another terminal:

cd ~/hector_group2_ws

source devel/setup.bash

rosservice call /enable_motors "enable: true"

rosrun udm_group2_drone_control drone_move_service.py

On another terminal:

rosservice call /udm_drone_move_service "altitude: data: '2' horizontal_x: data: '3' horizontal_y: data: '0'"

Part 4:

cd ~/hector_group2_ws

source devel/setup.bash

roslaunch hector_quadrotor_demo outdoor_flight_gazebo.launch

On another terminal:

cd ~/hector_group2_ws

source devel/setup.bash

rosservice call /enable_motors "enable: true"

rosrun udm_group2_drone_control drone_move_service.py

On another terminal:

cd ~/hector_group2_ws

source devel/setup.bash

rosrun udm_group2_drone_control waypoints.py
