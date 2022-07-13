# Control Module

Control Module is integrated driver for basic robot hardware. In terms of robot control, the control module is joint-level controller. Angel Legs M30 use [STM32H743](https://www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html) as the control module.

![Control Module Architecture](<../../.gitbook/assets/image (6).png>)

## Drivers

* The hardware-related libraries and middle-wares are grouped as "drivers".
  * **HAL(Hardware Abstraction Layer)**: HAL library provided by STM32
  * **FreeRTOS**: Real-time scheduler.
  * **LwIP(Light-weight IP)**: TCP/IP stack.
  * **CANFD**: FDCAN Supports.
  * **BSP(Board Support Package)**: Interface for specific IC or hardware.
  * **IO Interface**: Wrapper of HAL library.

## Framework

* Framework to implement the control module as multi-device driver.
* This framework defines "**device**" as some hardware or specific process with unique functions. Each "**device**" runs in separated thread.
* The "devices" are managed as **state machine**.
* The functions of "devices" is implemented as "**drive routines**", that are functions called repeatedly.

## Main Firmware

* Main Firmware refers to implemented "devices" based on multi-device driver framework.
* Followings are "devices" of the control module.

### Core

* "Core device" manage the control module itself, monitoring battery power state and errors of other devices.

### Ethernet

* "Ethernet device" manage TCP server of the control module, which is main interface for the control module.
* The [Application Module](application-module.md) can control the robot using TCP, as "ethernet device" provide total interface to the  control module.

### Joint

* "Joint device" is whole-body dynamic controller of the robot.

### UI

* "UI device" controls the basic indicator of robot, such as LEDs or buzzer.

### Geometry

* "Geometry device" compute geometry of robot.

### Boot

* "Boot device" manage the boot/shutdown sequence of hardware.

### External Device

* "External device" provide interface to the extra peripheral ports, such as SPI or I2C for add-on devices.



##
