## Hardware

- [Components](#components)
- [Wiring](#wiring)

### Components

* Nvidia Jetson Nano
* PCA9685 16-channels PWM controller
* 12 Hextronik HX-5010 servomotors

### Wiring

* PCA9685 to Nvidia Jetson Nano (I2C Bus 1)

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

* Servo positions

#### TODO: IMU pinout

* I2C Bus 0

SDA is on Pin 27
SCL is on Pin 28
