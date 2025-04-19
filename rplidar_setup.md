# RPLidar Setup

Model: RPLidar A3M1-R3

Baud Rate: 256,000

## Setup Steps

**Ensure Jetson Orin is on Ubuntu 22.04**

1. Plug in the Lidar to the Orin via USB
   
3. Check which port it is using and its permissions by running the command:
    ```bash
    ls -l /dev | grep ttyUSB
    ```
    
4. If the user doesn't have read and write permissions, run this command:
    ```bash
    sudo chmod 666 /dev/ttyUSB0
    ```
    *make sure to replace ttyUSB0 with the port your lidar is on!*
   
5. Clone the rplidar_sdk git repository to your machine
   ```bash
   git clone https://github.com/Slamtec/rplidar_sdk
   ```
   
6. cd into `~/rplidar_sdk`
   
7. Compile/make by this command running in the `~/rplidar_sdk` directory
   ```bash
   make
   ```
   
8. Next, to test that the Lidar is working and sending data properly, cd into `~/rplidar_sdk/output/Linux/Release` and run
   ```bash
   ./ultra_simple --channel --serial /dev/ttyUSB0 256000
   ```
   * Ensure the port is correct (mine is connected on `ttyUSB0`)
   * Ensure the baud rate (the final parameter of this command, A3 Lidars have `256000` baud rate) matches the baud rate of your lidar model
   * **TROUBLESHOOTING:** *If you get a "no such file or directory" error when running `./ultra_simple`, ensure it is in the `/Release` directory by running `ls`. If it is not, rerun `make` in the `~/rplidar_sdk` directory*

After running these steps, you should get an output like:
```yaml
Ultra simple LIDAR data grabber for SLAMTEC LIDAR.
Version: x.x.x
SLAMTEC LIDAR S/N: xxxxxxxxxxx...
Firmware Ver: x.x
Hardware Rev: x
SLAMTEC LIDAR health status: x
grab scan data...
theta:  10.53 Dist: 0213.25 Q:47
theta:  10.72 Dist: 0214.75 Q:47
...
```
   
   
