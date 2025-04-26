<br />
<div align="center">
  <a href="https://github.com/atom-robotics-lab/assets/blob/main/logo_1.png?raw=true">
    <img src="https://github.com/atom-robotics-lab/assets/blob/main/logo_1.png?raw=true" alt="Logo" width="120" height="120">
  </a>
 <h3 align="center">GPS Navigation</h3>

  <p align="center">
    This is the repo for the <a href="https://github.com/atom-robotics-lab/GPS_Nav">GPS Nav</a> Project, Mr robot is autonomous navigation robot made by A.T.O.M Robotics capable of Navigation using GPS coordinates utilizes Mapviz and various srcipts for various tasks. Various other operations can also be performed thanks to its modularity.
  </p>
</div>
<br />

## About the Project
This project aims to develop a comprehensive ROS2 simulation package tailored for a differential drive robot.This repository shows how to set up a localization system using a GPS sensor(s) as the source of global positioning, robot_localization (RL) for sensor fusion, and how to use Nav2 to follow GPS waypoints.

### Built With
* [![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
* [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
* [![ROS 2](https://img.shields.io/badge/ros-%230A0FF9.svg?style=for-the-badge&logo=ros&logoColor=white)](https://www.sphinx-docs.org)

## Getting started
Follow these instructions to set up this project on your system.

### Prerequisites

* ROS Humble
Refer to the official [ROS 2 installation guide](https://docs.ros.org/en/humble/Installation.html)
* Gazebo Classic
```bash
sudo apt install ros-humble-gazebo-ros-pkgs
```
* Robot_localization and mapviz:
```bash
source /opt/ros/humble/setup.bash
sudo apt install ros-humble-robot-localization
sudo apt install ros-humble-mapviz
sudo apt install ros-humble-mapviz-plugins
sudo apt install ros-humble-tile-map
```
* Nav2 packages
```bash
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-nav2-bringup
```

### Installation
 
 1. Make a new workspace
    ```bash
    mkdir -p gps_nav_ws/src
    ```

2. Clone the GPS_Nav repository

    Now go ahead and clone this repository inside the "src" folder of the workspace you just created.

      ```bash
      cd gps_nav_ws/src
      git clone git@github.com:atom-robotics-lab/GPS_Nav.git
      ```

3. Compile the package

    Follow this execution to compile your ROS 2 package
  
      ```bash
      colcon build --symlink-install
      ```

4. Source your workspace
      ```bash
      source install/local_setup.bash
      ```

## Usage
Our package consists of three directories as follows:-

- The `mr_robot_description` dir contains all the bot model description files.
- The `mr_robot_gazebo` dir contains all the world description files.
- The `mr_robot_navigation` dir contains all the config files for enabling navigation and planning.

### 1. Launch navigation
Spawns our robot in a custom gazebo world along with all the necessary plugins. It also launches navigation
```bash
ros2 launch mr_robot_navigation gps_waypoint_follower.launch.py use_rviz:=True
```
**_NOTE:_** Make sure that you have installed the navigation dependencies before running the navigation launch file.<br />

### 2. Mapviz
[Docker image for tile map](https://github.com/danielsnider/MapViz-Tile-Map-Google-Maps-Satellite)<br />
* Launches mapviz GUI 
```bash
ros2 launch mr_robot_navigation mapviz.launch.py
```
![Screenshot from 2025-02-06 23-24-53](https://github.com/user-attachments/assets/95ac4f5f-862a-426a-a0ea-46600d2883c7)



### 3. Run interactive_waypoint_follower script
This script makes the robot navigate to the clicked waypoint in mapviz
```bash
ros2 run mr_robot_navigation interactive_waypoint_follower
```

### 4. Run gps_waypoint_logger script
Opens up a GUI to save the robot current coordinates and heading on demand to a yaml file 
```bash
ros2 run mr_robot_navigation gps_waypoint_logger
```

### 5. Run logged_waypoint_follower script
Robot navigates through previously logged waypoints
```bash
ros2 run mr_robot_navigation logged_waypoint_follower
```


https://github.com/user-attachments/assets/89ecf916-f9e9-4ee3-bdf6-f13138252aca






## Contributing

We wholeheartedly welcome contributions!  
They are the driving force that makes the open-source community an extraordinary space for learning, inspiration, and creativity. Your contributions, no matter how big or small, are **genuinely valued** and **highly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/New-Feature`)
3. Commit your Changes (`git commit -m 'Add some New-Feature'`)
4. Push to the Branch (`git push origin feature/New-Feature`)
5. Open a Pull Request

Please adhere to this project's `code of conduct`.

## License

[APACHE 2.0](https://choosealicense.com/licenses/apache-2.0/)

## Contact Us

If you have any feedback, please reach out to us at:  
Our Socials - [Linktree](https://linktr.ee/atomlabs)

## Acknowledgments

* [Our wiki](https://atom-robotics-lab.github.io/wiki)
* [ROS Official Documentation](http://wiki.ros.org/Documentation)
* [Gazebo Tutorials](https://classic.gazebosim.org/tutorials)
* [Ubuntu Installation guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)
* [Docker installation guide](https://docs.docker.com/engine/install/ubuntu/)
* [Nav2 official documentation](https://docs.nav2.org/index.html)
* [Mapviz official installation](https://swri-robotics.github.io/mapviz/)
