# RMA

This package works together with the MRS System. 

### Dependencies   
| Operational System 	         |  Ubuntu 20.04            | 
| ---------------------------- | ------------------------ |
| ROS 	                       | ![image](https://user-images.githubusercontent.com/74054598/149457205-fd48db89-0658-4511-af36-bcd8662562da.png)|
| MRS System 	                 | Native installation      | 
| Gazebo    	                 | Gazebo multi-robot simulator - version 11.13.0     | 

Features

   - UAV
   - Multi UAV
   - RPLidar
   - Velodyne
   - Rangefinder
   - Bluefox
   - Real-sense D-435


## Step 1 - Upload class's package

```bash 
cd ~/workspace/src 
git clone https://github.com/vivaldini/RMA.git 
catkin build 
bash ../devel/setup.bash
```

## Step 2 - Setting Gazebo

Start Gazebo by entering the following at the command prompt.

```bash 
gazebo
```

Click on Edit -> Model Editor

Click in File -> Save as

Save the model in the Location: /workspace/src/RMA/models.

### Step 3

To add the directory to models and worlds:

   - Open gazebo
   - Click on "Insert" (upper left)
   - Click "Add Path" (upper left)
   - Choose the paste ~/workspace/src/RMA/models
   - Close gazebo

### Step 4 - Test the environment

- UAV
```bash 
cd
bash ~/workspace/src/RMA/src/start/start.sh
```

- Multi UAVs run

```bash
  cd
  bash ~/workspace/src/RMA/src/start/multiStart.sh
```

### Step 5: Use algorithms and information available from MRS

Repository 1: https://ctu-mrs.github.io/docs/system/uav_ros_interface.html#uavmanager

Repository 2: https://ctu-mrs.github.io/docs/software/mavros.html#used-topics-and-services

Topic Informations:

   - Localization: /uav1/odometry/odom_main
   - Laser: /uav1/garmin/range
   - Global motion: /uav1/control_manager/reference
   - Local motion: /uav1/control_manager/goto_fcu

### Extra 1: Ways to stop the simulation

Press “CTRL + a” and after “k” in the prompt.

If something remains open:

```bash
alias killg='killall gzclient && killall gzserver && killall rosmaster'
killall px4
tmux kill-server
```

### Extra 2 - Learning ROS

Communication with the MRS will be done through ROS. If you are not yet aware, it is interesting to carry out the tutorial 1.1.1 to 1.1.18 link: http://wiki.ros.org/ROS/Tutorials

## Note:
    1. We will see ROS in the course, but it is important to improve your expertise to do the tutorials. That will be passed as Frequency Activities.
    2. The scenario was developed by @lidiaxp.

    
## Support

For support, send email to vivaldini@ufscar.br
