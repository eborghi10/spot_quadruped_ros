# Spot Micro quadruped robot

- [Overview](#overview)
- [Mechanics](#mechanics)
- [Hardware](#hardware)
- [Software](#software)
- [Future Work](#future-work)
- [External Links](#external-links)

## Overview

This project is a modification for the SpotMicroAI quadruped project, a 4-legged open source robot.
There are a few modification but the baseline quadruped is the SpotMicroAI.
The most important key points of this design:

* It runs with ROS
* It won't use super expensive motors but it will try to be energetically efficient

## Mechanics

Version 1.02 was designed by [Brad Prince](https://gitlab.com/custom_robots/spotmicroai/3dprinting/-/tree/master/Basic%203d%20parts%20by%20Brad%20Prince/v1.02).

## Hardware

* Nvidia Jetson Nano
* PCA9685 16-channels PWM controller
* 12 Hextronik HX-5010 servomotors

### Wiring

* PCA9685 to Nvidia Jetson Nano

```no-lang
J41 Pin 1 (3v3) --> PCA9685 VCC
J41 Pin 3 (SDA) --> PCA9685 SDA
J41 Pin 5 (SCL) --> PCA9685 SCL
J41 Pin 6 (GND) --> PCA9685 GND
```

```bash
sudo usermod -aG i2c $USER

sudo apt install -y libi2c-dev

i2cdetect -y -r 1
```

* Servo positions

## Software

* ROS Melodic

### Workspace setup

* [**champ** (branch: `development`)](https://github.com/eborghi10/champ/tree/development)
* [**i2c_pwm_board** (branch: `master`)](https://github.com/eborghi10/i2c_pwm_board)
* [**robots** (branch: `development`)](https://github.com/eborghi10/robots/tree/development)
* [**spot_control_hw** (branch: `development`)](https://github.com/eborghi10/spot_control_hw/tree/development)
* [**spotmicro_description** (branch: `development`)](https://github.com/eborghi10/spotmicro_description/tree/development)

### Calibration

```sh
roslaunch spotmicro_config calibration.launch

# TODO: EDIT JOINT_CALIBRATION NODE
roslaunch champ_bringp joints_gui.launch
```

#### TODO: [Add instructions](https://github.com/mike4192/spotMicro/blob/master/servo_calibration.md#commanding-individual-servos-for-calibration)

### Execution

```sh
roslaunch spotmicro_config bringup.launch
```

## Future work

### Short term

* Fix PWM driver errors on the screen when launching quadruped_controller
* Use champ_bring/joints_gui.launch for calibration
* Automatically detect I2C address? Reboot device at startup?
   * PWM controller changes its address on each reboot

### Long term

* Integrate an IMU and Laser - Make it move autonomously
* Improve leg mechanics (energy efficiency)
* Integrate 3D cameras and make it walk in rough terrain

## External links

Spot Micro AI community: [https://gitlab.com/custom_robots/spotmicroai]
