# Hardware

- [Components](#components)
- [Wiring](#wiring)

## Components

- Nvidia Jetson Nano
- [18650 UPS HAT Shield for NVIDIA Jetson Nano](http://raspberrypiwiki.com/T200)
- PCA9685 16-channels PWM controller
- 12 Hextronik HX-5010 servomotors

## Wiring

- PCA9685 to Nvidia Jetson Nano (I2C Bus 1)

```no-lang
J41 Pin 1 (3v3) --> PCA9685 VCC
J41 Pin 3 (SDA) --> PCA9685 SDA
J41 Pin 5 (SCL) --> PCA9685 SCL
J41 Pin 6 (GND) --> PCA9685 GND
```

```bash
sudo usermod -aG i2c $USER

i2cdetect -y -r 1
```

- Servo positions

### TODO: IMU pinout

- I2C Bus 0

SDA is on Pin 27
SCL is on Pin 28

### Powering NVIDIA Jetson Nano

![T200](https://raspberrypiwiki.com/images/b/bc/T200-Interface-schematic.jpg)

- How to read battery info via I2C: <http://raspberrypiwiki.com/T200_software>

#### TODO

- Connect external power switch (PH2.0)

  1. SW => NO， GND => COM, 5V0 =>LED+，LED- => COM
  2. (+) => SW , (-) => GND

- Buy 5.5x2.5mm power jack
- Use XH2.54 to power other devices
- Read I2C information
- Connect cable to 3d camera
- Mount switch in robot
