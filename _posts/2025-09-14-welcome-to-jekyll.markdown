---
layout: post
title:  "Turtleboot"
description: Bash scripts to auto install ROS (Jazzy) on a Turtlebot3
date:   2025-09-14 07:20:47 -0400
categories: RBE3002, ROS2, ROBOTIS
github_repo: https://github.com/kmhswimgirl/turtleboot
excerpt: After deciding to embark on my quest to learn ROS 2 I had to do some tech setup. While dual booting my ancient Dell PC with Ubuntu 24.04 and installing ROS, I realized that installing this on a robot that has a SBC with only 2GB of RAM would be incredibly tedious.
---

After deciding to embark on my quest to learn ROS 2 I had to do some tech setup. While dual booting my ancient Dell PC with Ubuntu 24.04 and installing ROS, I realized that installing this on a robot that has a SBC with only 2GB of RAM would be incredibly tedious.

Turtleboot is a collection of bash scripts that install ROS 2 Jazzy Jalisco, flash the OPEN CR motor controller, and deal with any specific configuration options a user might want.

There file structure of Turtleboot is as such:
``` 
turtleboot/
├── ros.bash
├── preros.bash
├── opencr.bash
└── lite.bash
```

Each script plays a specific role and makes sure that a Turtlebot3 can be setup from any stage in the process. For instance, `preros.bash` deals with configuring some of the update rules before the turtlebot has to be rebooted per the ROBOTIS docs. I also found an error is ROBOTIS' setup guide while creating this project, the package `ros-jazzy-xacro` is actually required to run the turtlebot bringup command which is most likely due to the onboard URDF file utilizing xacro.

I also took the chance to add some fun ascii art while learning how to run these with the correct permissions (need sudo commands, but can't run as root...):
```
 _____           _   _      ____              _   
|_   _|   _ _ __| |_| | ___| __ )  ___   ___ | |_ 
  | || | | | '__| __| |/ _ \  _ \ / _ \ / _ \| __|
  | || |_| | |  | |_| |  __/ |_) | (_) | (_) | |_ 
  |_| \__,_|_|   \__|_|\___|____/ \___/ \___/ \__|
                   _____     ____
                 /      \  |  o | 
                |        |/ ___\| 
                |_________/     
                |_|_| |_|_|
```