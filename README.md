# Robotics Systems-Device driver

## Description
Created a device driver to control a DC motor based on the [device driver](https://github.com/ryuichiueda/robosys_device_drivers) created in the lecture.

---

## Environment
Ubuntu server 20.04.3 LTS

---

## Requirements
| Name | Quantity |
| :--: | :------: |
| [Raspberry Pi 4 ModelB](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/) | 1 |
| [L298N](http://www.hiletgo.com/ProductDetail/1915475.html) | 1 |
| [DC Motor with Wheel](https://www.amazon.co.jp/-/en/Treedix-Electric-Plastic-Arduino-Electronic/dp/B088NMV7C6/ref=sr_1_1) | 4 |
| AA Battery | 4 |
| [4 AA Battery Holder](https://www.amazon.com/abcGoodefg-Battery-Holder-Switch-Leads/dp/B071XTF3Z9/ref=sr_1_34) | 1 |
| Jump wire male-to-male | 1 |
| Jump wire male-to-female | 4 |

---

## Schematic
<img src="https://user-images.githubusercontent.com/71488207/148551537-0493e93f-8110-4c06-87a2-c42404b92d16.png" width="600px">

### Connection
| GPIO | L298N | Motor | Battery Holder |
| :--: | :---: | :---: | :-----: |
| 22 | IN1 ||||
| 23 | IN2 ||||
| 24 | IN3 ||||
| 25 | IN4 ||||
|| OUT1 | 2 motor+ |||
|| OUT2 | 2 motor- |||
|| OUT3 | 2 motor- |||
|| OUT4 | 2 motor+ |||
|| +12V || + (Red) |
|GND PIN | GND || - (Black) |


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

## Acknowledgment
[The repository](https://github.com/MibuchiYuta/Control_DCmotor_RaspberryPi) I referred to when controlling the car. Thanks to Yuta Mibuchi.

---

## License
[GNU General Public License v3.0](https://github.com/RyodaiArai/Robotics_Systems-Device_driver/blob/main/COPYING)
