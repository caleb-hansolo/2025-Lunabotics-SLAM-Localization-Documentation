# Hopper Bin Camera - OV9281 Global Shutter UVC Camera

## Setup Steps

Additional Documentation for this camera is at this [link](https://docs.arducam.com/UVC-Camera/Appilcation-Note/External-Trigger-Mode/OV9281-Global-Shutter/)

1. Plug the camera into the Jetson Orin via USB
2. Install v4l utility packages
   ```shell
   sudo apt-get install v4l-utils
   ```
3. List UVC devices connected to the USB ports (if you have multiple devices connected, multiple devices will show up! ensure that your Arducam device shows up)
   ```shell
   v4l2-ctl --list-devices
   ```
4. Install `guvcview` to test live video stream
   ```shell
   sudo apt install v4l-utils guvcview
   ```
5. Run `guvcview`, and select appropriate video input stream when prompted
   ```shell
   guvcview
   ```

Video stream from `guvcview` should look something like this:
![image](https://github.com/user-attachments/assets/fa1b3acb-0d29-44aa-ac1e-05a45e21245b)

## Working with Rviz2

Make sure that ROS2 is installed first!!

1. Install v4l2 camera node
   ```shell
   sudo apt install ros-humble-v4l2-camera
   ```
2. Launch
   ```shell
   ros2 run v4l2_camera v4l2_camera_node --ros-args -p video_device:=/dev/video0
   ```
   Replace `video0` with the video stream corresponding to your camera (may be different if you have multiple cameras connected). For example, with the D435i connected, my video streams for the OV9281 were `video6` and `video7`.
3. In a separate terminal, view image:
   ```shell
   ros2 run image_tools showimage
   ```
4. Or, use Rviz to view (in a separate terminal as well)
   ```shell
   rviz2
   ```
   If using Rviz to visualize, select `Add` on the bottom left to add an image, go to the topics tab, find the `/image_raw topic`, and then select `Image`, and press `OK`. Rviz should look something like this, with the live video stream in the bottom left corner.
   ![image](https://github.com/user-attachments/assets/8a2dbb1c-2fd5-427f-aab5-51034c868484)


