## Software

- [Workspace setup](#workspace-setup)
- [Calibration](#calibration)
    - [Servos](#servos)
    - [IMU](#imu)

### Workspace setup

* Ubuntu Mate 18.04 + ROS Melodic

* [**champ** (branch: `development`)](https://github.com/eborghi10/champ/tree/development)
* [**i2c_imu** (branch: `master`)](https://github.com/RoboticaUtnFrba/i2c_imu/tree/master)
* [**i2c_pwm_board** (branch: `master`)](https://github.com/eborghi10/i2c_pwm_board)
* [**robots** (branch: `development`)](https://github.com/eborghi10/robots/tree/development)
* [**spotmicro_description** (branch: `development`)](https://github.com/eborghi10/spotmicro_description/tree/development)

### Calibration

#### Servos

```sh
roslaunch spotmicro_config calibration.launch

# TODO: EDIT JOINT_CALIBRATION NODE
roslaunch champ_bringp joints_gui.launch
```

##### TODO: [Add instructions](https://github.com/mike4192/spotMicro/blob/master/servo_calibration.md#commanding-individual-servos-for-calibration)

#### IMU

##### [TODO](https://github.com/RoboticaUtnFrba/create_autonomy/wiki/Tuning-robot-localization#calibrating-imu)

- Install RTIMULib: https://github.com/RoboticaUtnFrba/RTIMULib/blob/master/Linux/README.md#build-using-cmake

```
sudo apt-get install libqt4-dev
```
