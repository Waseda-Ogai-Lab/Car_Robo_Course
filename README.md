# Car_Robo_Course

日本語 http://jgs.kyutech.ac.jp/car-robo/

English http://jgs.kyutech.ac.jp/car-robo/english/

# System Design
## COMS
![COMS](img/COMS.png)
## Prius
![Prius](img/Prius.png)

# Program
## 1. ROS
### Obstacle Detection with ZED Camera
`new_detect` rospy package to detect the object.

### GPS Receiver connected with Windows

`tcpcli/scripts/talker.py` to received the GPS signal from Windows RTK GPS by router, because the RTK-GPS now could only run on Windows, and it will broadcast the signal by net, so we could use router to received the information on ROS, then we will transfer it to Simulink.

## 2. Windows

### RTK-GPS

### VCDesigner

### dSPACE AutoBox


# Set Up Tutorial
`start.sh` includes the commands as follows.

```sh
gnome-terminal -e ~/joystick
sleep 10s
gnome-terminal -t "Joystick2coms" -x rosrun joystick2coms dumptest slcan0
sleep 2s
gnome-terminal -t "Joystick2coms" -x rosrun joystick2coms car_position
sleep 2s
gnome-terminal -t "Zed" -x roslaunch zed_wrapper zed.launch
sleep 10s
gnome-terminal -t "OrangLine" -x rosrun beginner_tutorials lane_detection.py
sleep 10s
gnome-terminal -t "detect" -x rosrun side_detect side_cam_detector.py
sleep 10s
gnome-terminal -t "detect" -x rosrun new_detect hello16
gnome-terminal -t "detect" -x python ~/catkin_ws/src/tcpcli/scripts/talker.py
gnome-terminal -t "detect" -x matlab
```
# Set up RTK-GPS rover
[GPS Set Up Japanese Doc](gps.md)

## COMS

1. turn on the power of the COMS at the backend of the car.
1. turn on the ROS computer.
1. turn on the Windows computer.
1. set up the RTK-GPS rover.
1. turn on the AD5454 controller.
1. set up the ROS system.
    ```sh
    source ~/catkin_ws/devel/setup.bash
    ./start.sh
    ```
1. set up the Simulink. 

## Prius


1. turn on the power of the Prius car.
1. turn on the ROS computer.
1. turn on the Windows computer.
1. set up the RTK-GPS rover.
1. turn on the Autobox controller.
1. set up the ROS system.
    ```sh
    source ~/catkin_ws/devel/setup.bash
    ./start.sh
    ```
1. set up the Simulink. 




# Start Autopilot
## COMS
1. turn on the car by the key.
1. when the dashboard is not lighted, turn on the switch of autopilot mode.
## Prius