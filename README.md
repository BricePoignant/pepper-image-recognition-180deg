# Pepper 180° image recognition
## Installation steps
If using for the first time, please install the following packages in the src folder:

    git clone https://github.com/ros-naoqi/pepper_robot
    git clone https://github.com/ros-naoqi/naoqi_bridge
    git clone https://github.com/ros-naoqi/naoqi_bridge_msgs
    git clone https://github.com/ros-perception/vision_msgs

Also put the following command lines in devel/setup.bash :

    export PYTHONPATH=${PYTHONPATH}:$D/lib/python2.7/site-packages
    export DYLD_LIBRARY_PATH=${DYLD_LIBRARY_PATH}:$D/lib

And then execute the following command line : 

    catkin build

Also please make sure that the following files in the folder pepper_adv and pepper_talk under the folder src are executables : 
- visualization_node
- visualization_node_test
- head_node
- detector_node
- detector.py
- decoding_node
- decoding_node_test
- pepper_talk_node

## How to use
To use, execute one the following launch files in the same folder:

### USE ONLY IF YOU HAVE PEPPER : 

    roslaunch pepper_det.launch pepper_ip:='your_ip'
Connect to pepper using his ip in argument. Default ip is 10.0.1.207.

## USE IF YOU DON'T HAVE PEPPER : 

    roslaunch pepper_test.launch"

along with the following command line in an other terminal :

    rosrun image_publisher image_publisher test.jpg __name:=test

General usage : Wait for the message "Pepper is ready" to appear in the console before starting the detection using the following command in an other console :

    rostopic pub msg_begin std_msgs/Empty

If pepper doesn't wake up use the wakeup.py file using python.
