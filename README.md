# Robotics Systems-Device Driver

---

## Overview
This device driver was created by modifying the [device driver](https://github.com/ryuichiueda/robosys_device_drivers) created by Associate Professor Ryuichi Ueda in [Robotics Systems](https://www.youtube.com/watch?v=xQW8-FNuboo) lecture, and controls wheels according to the input alphabet (f, b, s, r, l).

---

## Environment
Ubuntu Server 20.04.3 LTS

---

## Requirement
| Name | Quantity | Datasheet |
| :--: | :------: | :-------: |
| [Raspberry Pi 4 ModelB](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/) | 1 | [PDF](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/files/7833504/raspberry-pi-4-datasheet.pdf) |
| [L298N (Motor driver)](https://www.amazon.co.jp/-/en/VKLSVAN-Stepper-Controller-Compatible-Arduino/dp/B08B87WWHV/ref=sr_1_5) | 1 | [PDF](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/files/7833507/l298.pdf)
| [DC Motor with Wheel](https://www.amazon.co.jp/-/en/Treedix-Electric-Plastic-Arduino-Electronic/dp/B088NMV7C6/ref=sr_1_1) | 4 |
| AA Battery | 4 |
| [4 AA Battery Holder](https://www.amazon.com/abcGoodefg-Battery-Holder-Switch-Leads/dp/B071XTF3Z9/ref=sr_1_34) | 1 |
| Jump wire male-to-male | 1 |
| Jump wire male-to-female | 4 |

---

## Schematic
<img src="https://user-images.githubusercontent.com/71488207/148551537-0493e93f-8110-4c06-87a2-c42404b92d16.png" width="600px">

## Connection
| GPIO | L298N | Motor | Battery Holder |
| :--: | :---: | :---: | :-----: |
| 22 | IN1 |
| 23 | IN2 |
| 24 | IN3 |
| 25 | IN4 |
|| OUT1 | 2 motors+ |
|| OUT2 | 2 motors- |
|| OUT3 | 2 motors- |
|| OUT4 | 2 motors+ |
|| +12V || + (Red) |
|GND PIN | GND || - (Black) |

---

## Model
<img src="https://user-images.githubusercontent.com/71488207/148588983-0917a38b-b10c-49bf-8c56-caae8d74ad70.png" width="600px">

---

## Install & Build
```
$ git clone https://github.com/RyodaiArai/RoboticsSystems-DeviceDriver
```
```
$ cd Robotics_Systems-Device_Driver
```
```
$ make
```
```
$ sudo insmod control.ko
```
```
$ sudo chmod 666 /dev/control0
```

## Usage
### Forward
```
$ echo f > /dev/control0
```
### Backward
```
$ echo b > /dev/control0
```
### Stop
```
$ echo s > /dev/control0
```
### Right rotation
```
$ echo r > /dev/control0
```
### Left rotation
```
$ echo l > /dev/control0
```

## Uninstall
```
$ sudo rmmod control
```
```
$ make clean
```

---

## Video

[<img src="https://user-images.githubusercontent.com/71488207/148650950-bebfaad0-4e61-44c5-b9ce-ca8a43426572.png" width="600px">](https://www.youtube.com/watch?v=RbxuJ0crwDw)  
Click on the image to play the video on YouTube.

---

## License
[GNU General Public License v3.0](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/blob/main/COPYING)
