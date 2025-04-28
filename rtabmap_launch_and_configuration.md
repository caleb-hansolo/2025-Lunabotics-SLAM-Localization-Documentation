# Key Websites
Official repository: https://github.com/introlab/rtabmap/tree/master

Official rtabmap wiki: https://github.com/introlab/rtabmap/wiki

ROS2 with rtabmap: http://wiki.ros.org/rtabmap

# Setting Up rtabmap Processing
Basically what we need to get the data processing is a launch file and a config file. Currently, only the launch file is listed in this repository (for a D435i camera) as realsense_d435i_stereo.launch.py, but the config file will also be added once I figure out how to do that

The config file will need to be tuned heavily to actually get good accuracy out of the sensors

We might also need a params file but I am not 100% sure

# Code Implementation
This section is about actually reading information from rtabmap and using it to influence navigation code

I believe you set up slam with c code in https://github.com/introlab/rtabmap_ros/tree/ros2/rtabmap_slam

Also need to look at msg's in the rtabmap_ros repository. Honestly just go through every folder in here and see what you do and don't need, a lot if it is just what we need

# Navigation Method
We are going to be using stereo outdoor mapping/navigation with a stereo camera + 2d lidar. We mostly need to navigate around obstacles and navigate to certain goal areas (which is what stereo mapping is)

Follow these tutorials in order to set it up and get a general understanding of what is going on. They do not go all the way in depth but are good starting places. I will update this later with more sources that I find but I have not gotten to implementing these steps yet

1. http://wiki.ros.org/rtabmap_ros/Tutorials/SetupOnYourRobot#Kinect_.2B-_2D_laser
2. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoHandHeldMapping
3. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoOutdoorMapping
4. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoOutdoorNavigation
