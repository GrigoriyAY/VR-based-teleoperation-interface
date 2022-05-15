# VR-based teleoperation interface

VR-based teleoperation interface to control quadrotor equipped with robotic arm. This repository contains Unity application, codes (Arduino IDE) for wearable interface and manipulator, MATLAB file to control manipulator using GUI (can be useful for development of own planar manipulator). For more details about the project, please see the [Wiki](https://github.com/Y-Grigoriy/VR-based-teleoperation-interface/wiki).

## Repository structure

* [AirInterface folder](./AirInterface) contains files of Unity project (version 2019.4.35f1). The application contains scripts of Unity connection with the wearable interface (based on Bluetooth), **HTC VIVE** controllers, **mocap** (WiFi), flying robot represented by **Raspberry Pi 4** which is connected with **Pixhawk autopilot** and manipulator (OpenCM 9.04 micrcontroller). WiFi connection is implemented using [**ROS#**](https://github.com/siemens/ros-sharp). 

* [AirInterface-ROS](https://github.com/CityAplons/AirInterface-ROS) contains an implementation of control and feedback nodes for communication with Unity using available ROS interfaces. The project includes full setup for an experimental part and simulation.

* The folder ["IMU-based"](./IMU-based) contains code in Arduino IDE to track orientation of the operator arm using 3 IMU and 1 flex sensors via **Arduino Nano**. To run this code it is necessary to download libraries [MPU9250_Madg](./IMU-based/MPU9250_Madg) and [MadgwickAHRS_Troyka](./IMU-based/MadgwickAHRS_Troyka). The library "MPU9250_Madg" is a modification of the library: [MPU9250](https://github.com/bolderflight/MPU9250). It was used to read data from sensor **GY-91**. The library "MadgwickAHRS_Troyka" is a modification of the library: [Troyka-IMU](https://github.com/amperka/Troyka-IMU). It was used to process data from sensor GY-91 using Madgwick filter.

* The folder ["DroneArm_v10"](./DroneArm_v10) contains code in Arduino IDE to control position of the manipulator and read data from manipulator sensors using **OpenCM 9.04**. To run this code it is necessary to download library for [OpenCM 9.04](https://emanual.robotis.com/docs/en/software/arduino_ide/#install-on-windows).

* MATLAB file [Manipulator_v21.m](./Manipulator_v21.m) (File was last run in MATLAB R2019a version), you can control the movement of the planar manipulator in the GUI, as well as connect to a real 4-axis planar manipulator controlled by Arduino, USB2Dynamixel, or OpenCM 9.04 via Bluetooth or a COM port. To work with Arduino, ultrasonic sensor and Dynamixel servomotors via USB2Dynamixel, you need to install the following libraries: [MATLAB Support Package for Arduino Hardware](https://www.mathworks.com/matlabcentral/fileexchange/47522-matlab-support-package-for-arduino-hardware?s_tid=srchtitle), [Legacy HC-SR04 Add-On Library for Arduino](https://www.mathworks.com/matlabcentral/fileexchange/57898-legacy-hc-sr04-add-on-library-for-arduino), and [ROBOTIS Dynamixel SDK](https://github.com/ROBOTIS-GIT/DynamixelSDK).

**Note:** At the moment, some of the comments are written in Russian.
