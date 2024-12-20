
# UST-10lx Hokuyo Lidar with Hector Slam
This is the guide on how to use UST10-Lx Hokuyo Lidar with ROS1 without using IMU.


## Requirements
 
Setup | Description | Link
:----------: | :----: | :----------:
**Ubuntu**|`Focal Fossa (20.04)`  | https://releases.ubuntu.com/focal/
**ROS 1** |`Noetic` | https://wiki.ros.org/noetic/Installation
**Gedit** | Text editor | https://www.geeksforgeeks.org/gedit-command-in-linux/









## Installation

1. Install the urg_node
`sudo apt-get install ros-noetic-urg-node` 

2. Make sure you configure the Ethernet port in the setting. 

Eg:-
 - IPv4 
 - IP: 192.168.0.1
 - Subnet: 255.255.255.0


3. Follow the instruction from this link https://sourceforge.net/p/urgnetwork/wiki/ROS_en/#:~:text=This%20is%20how%20to%20install%20urg_node%2C%20and%20how,to%20%22%2Flaser%22.%20Add%20%22LaserScan%22.%20Change%20%22LaserScan-%3ETopic%22%20to%20%22%2Fscan%22.


4. Make sure the topic scan exist by using this command in terminal.
` rostopic echo scan`

5. Install the hector-slam 
`sudo apt-get install ros-noetic-hector-slam`

6. Add files name `mapping_default2.launch` to using below command
``````
roscd hector_mapping/launch
touch mapping_default2.launch
gedit mapping_default2.launch

``````
7. Paste the `mapping_default2.launch` code in the github and save.

8. Exit the file and add new file name `tutorial2.launch` using below command.

```````
cd
roscd hector_slam_launch/launch
touch tutorial2.launch
gedit tutorial2.launch
````````

9. Paste the `tutorial2.launch` code in the github and save it.

10. Run two urg node file and the hector_slam file in separate terminal window.

Terminal 1
````
rosrun urg_node urg_node _ip_address:=192.168.0.10
`````

Terminal 2 
`````
roslaunch hector_slam_launch tutorial2.launch
`````

11. Try walking and map the surroundings.



 
**Disclaimer this guide is only for newbies in ROS and the usage is for testing the lidar only. Try search another guide on how to improve localization by integrating with IMU.


GOODLUCK !!!
