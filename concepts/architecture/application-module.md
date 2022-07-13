# Application Module

Application Module is task-level controller, implemented on a linux system. Angel Legs M30 use [NVIDIA Jetson Xavier](https://developer.nvidia.com/embedded/jetson-agx-xavier-developer-kit) as the application module.

![](../../.gitbook/assets/image.png)

## Dependencies

* **Ubuntu**: Os for M30 application module.
* **ROS2**: Mid-OS for M30 application module.
* **Docker**: Container tool for OTA and DB.

## Robot Applications

* The robot applications are task-level robot control ROS2 packages. The actual services of the robot are realized by robot applications.
* For example, M30 provides rehabilitation robot application, such as 'level walk training',  'squat training', etc.

## Engine

* The engine is set of ROS2 packages, controlling and managing robot hardware.
* With the engine running, resources of robot are accessible via ROS2 interfaces.
* Followings are each components of the engine.

### Robot Application Node Manager

* The robot application node manger is ROS2 package managing the life cycle of the robot applications.
* The robot application node manger provides ROS2 interface for the life cycle control of robot applications, such as run or stop request.

### Communication Bridge&#x20;

* The communication bridges are ROS2 packages providing manages the communication with the external devices, such as tablet PC or [Control Module](control-module.md).
* The communication bridges convert communication protocols for the external devices to ROS2 interfaces.

#### Mobile Bridge

* The mobile bridge is communication bridge for mobile applications running on mobile devices such as tablet PC.
* Communication with mobile devices uses ROS2 interface directly via Wi-fi or Wi-fi direct.

#### Web Bridge

* The web bridge convert HTTP/HTTPS requests from [Cloud Robotics Service](cloud-robotics-service.md) to ROS2 interfaces.

#### Ethernet Bridge

* The ethernet bridge is communication bridge for [Control Module](control-module.md).
* Communication with the control module uses TCP/IP with Data Object Protocol.

### DB Manager

* The DB manager manages uploading and downloading ROS2 messages to the data base at local and  [Cloud Robotics Service](cloud-robotics-service.md).

### Local Machine Controller

* The local machine controller is set of ROS2 packages controlling and managing hardware of application module.
* The local machine controller provides ROS2 interface for hardware of application module.

#### Audio Controller

* The audio controller is ROS2 package controlling I2S interface of application module.
* The audio controller provides ROS2 interface for playing audio files.

#### Device Status Monitor

* The device status monitor is ROS2 packace providing hardware status of application module, such as CPU temperature, CPU/GPU usage, via ROS2 interface.

#### Network Manger

* The network manager is ROS2 package managing network configuration of application module.

### ROS2 Custom Message Package

* The custom ROS2 messages of the engine are managed in single message package.

## System Manager

* The system manager is task routine implemented using shell script, managing status of ROS2 nodes and other applications to keep application module operate.

## OTA Manager

* The OTA manager is task implemented using shell script, managing process of OTA for ROS2 packages.
* The OTA functionality is implemented using Docker HUB.

##

###
