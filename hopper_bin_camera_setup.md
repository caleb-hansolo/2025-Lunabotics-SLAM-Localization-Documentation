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


