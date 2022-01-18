# RMA

This package works together with MRS System. It is a easy to simulate UAVs and Multi UAVs considering your real kinematics.

## Build Status    
| Component 	       |  20.04              | 
| ------------------- | ------------------- |
| RMA 	             | ![image](https://user-images.githubusercontent.com/74054598/149457205-fd48db89-0658-4511-af36-bcd8662562da.png)|


Features

   - UAV
   - Multi UAV
   - RPLidar
   - Velodyne
   - Rangefinder
   - Bluefox
   - Real-sense D-435


## Step 1 - Instal MRS System

Follow the instructions [here](https://github.com/ctu-mrs/mrs_uav_system#installation) (on Installation topic) to install MRS System or use the commands:

```bash 
cd /tmp
echo '
GIT_PATH=~/git
mkdir -p $GIT_PATH
cd $GIT_PATH
sudo apt-get -y install git
git clone https://github.com/ctu-mrs/mrs_uav_system
cd mrs_uav_system
git checkout master
git pull
./install.sh -g $GIT_PATH
source ~/.bashrc' > clone.sh && source clone.sh
```

## Step 2 - Upload class's package

```bash 
cd ~/workspace/src 
git clone https://github.com/vivaldini/RMA.git 
catkin build 
bash ../devel/setup.bash
```

## Step 3 - Setting Gazebo

Start Gazebo by entering the following at the command prompt.

```bash 
gazebo
```

Click in Edit -> Model Editor

Click in File -> Save as

Save the model in the Location: /workspace/src/RMA/models.

### Step 4

To add the directory to models and worlds:

   - Open gazebo
   - Click on "Insert" (upper left)
   - Click "Add Path" (upper left)
   - Choose the paste ~/workspace/src/RMA/models
   - Close gazebo

### Step 5 - Test the environment

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

### Step 6: Use algorithms and information available from MRS

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
    1. In the course, we will see ROS, but it is important for improving your expertise to do the tutorials. That will be passed as Frequency Activities.
    2. The scenario was developed by @lidiaxp.

    
## Support

For support send email vivaldini@ufscar.br
