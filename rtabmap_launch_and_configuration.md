# Key Websites
Official repository: https://github.com/introlab/rtabmap/tree/master

Official rtabmap wiki: https://github.com/introlab/rtabmap/wiki

ROS2 with rtabmap: http://wiki.ros.org/rtabmap

# Setting Up rtabmap In Code
Basically what we need to get the data processing is a launch file and a config file. Currently, only the launch file is listed in this repository (for a D435i camera), but the config file will also be added once I figure out how to do that

# Navigation Method
We are going to be using stereo outdoor mapping/navigation since we mostly need to navigate around obstacles and navigate to certain goal areas (which is what stereo mapping is)

Follow these tutorials in order to set it up and get a general understanding of what is going on. They do not go all the way in depth but are good starting places

1. http://wiki.ros.org/rtabmap_ros/Tutorials/SetupOnYourRobot
2. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoHandHeldMapping
3. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoOutdoorMapping
4. http://wiki.ros.org/rtabmap_ros/Tutorials/StereoOutdoorNavigation
