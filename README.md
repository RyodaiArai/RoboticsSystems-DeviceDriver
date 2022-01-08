# Robotics Systems-Device driver

## Description
This device driver was created by modifying a [device driver](https://github.com/ryuichiueda/robosys_device_drivers) created by Associate Professor [Ryuichi Ueda](https://lab.ueda.tech/) in a lecture on [Robotics Systems](https://www.youtube.com/watch?v=xQW8-FNuboo).
This device driver controls a 4-wheeled vehicle according to the inputted alphabet (f, b, s, r, l).

---

## Environment
Ubuntu server 20.04.3 LTS

---

## Requirements
| Name | Quantity | Datasheet |
| :--: | :------: | :-------: |
| [Raspberry Pi 4 ModelB](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/) | 1 | [PDF](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/files/7833504/raspberry-pi-4-datasheet.pdf) |
| [L298N (Motor driver)](https://www.amazon.co.jp/-/en/VKLSVAN-Stepper-Controller-Compatible-Arduino/dp/B08B87WWHV/ref=sr_1_5) | 1 | [PDF](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/files/7833507/l298.pdf)
| [DC Motor with Wheel](https://www.amazon.co.jp/-/en/Treedix-Electric-Plastic-Arduino-Electronic/dp/B088NMV7C6/ref=sr_1_1) | 4 ||
| AA Battery | 4 ||
| [4 AA Battery Holder](https://www.amazon.com/abcGoodefg-Battery-Holder-Switch-Leads/dp/B071XTF3Z9/ref=sr_1_34) | 1 ||
| Jump wire male-to-male | 1 ||
| Jump wire male-to-female | 4 ||

---

## Schematic
<img src="https://user-images.githubusercontent.com/71488207/148551537-0493e93f-8110-4c06-87a2-c42404b92d16.png" width="600px">

## Connection
| GPIO | L298N | Motor | Battery Holder |
| :--: | :---: | :---: | :-----: |
| 22 | IN1 ||||
| 23 | IN2 ||||
| 24 | IN3 ||||
| 25 | IN4 ||||
|| OUT1 | 2 motors+ |||
|| OUT2 | 2 motors- |||
|| OUT3 | 2 motors- |||
|| OUT4 | 2 motors+ |||
|| +12V || + (Red) |
|GND PIN | GND || - (Black) |

---

## Model
<img src="https://user-images.githubusercontent.com/71488207/148588983-0917a38b-b10c-49bf-8c56-caae8d74ad70.png" width="600px">
<img src="https://user-images.githubusercontent.com/71488207/148589209-8408da05-e588-46f1-aab9-53dfaa98a288.png" width="600px">

---

## Install & Build
```
$ git clone https://github.com/RyodaiArai/Robotics_Systems-Device_driver
```
```
$ cd Robotics_Systems-Device_driver
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
### Move forward
```
$ echo f > /dev/control0
```
### Move back
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

---

## License
[GNU General Public License v3.0](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/blob/main/COPYING)

---

## Acknowledgment
[The repository](https://github.com/MibuchiYuta/Control_DCmotor_RaspberryPi) I referred to when controlling the car. Thanks to Yuta Mibuchi.
