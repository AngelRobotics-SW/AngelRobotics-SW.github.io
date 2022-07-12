# Application Module

Application Module is task-level controller, implemented on a linux system. Angel Legs M30 use [NVIDIA Jetson Xavier](https://developer.nvidia.com/embedded/jetson-agx-xavier-developer-kit) as the application module.

![](../../.gitbook/assets/image.png)

## Dependencies

* **Ubuntu**: Os for M30 application module.
* **ROS2**: Mid-OS for M30 application module.
* **Docker**: Container tool for OTA and DB.

## Robot Applications

* The robot applications are task-level robot controller, utilizing resource of robot. The actual services of the robot are realized by robot applications.
* The robot applications are implemented as ROS2 packages,&#x20;
* For example, M30 provides rehabilitation robot application, such as 'level walk training',  'squat training', etc.

## Engine

* The engine is set of ROS2 packages, controlling and managing robot hardware.
* With the engine running, all robot resources are accessible via ROS2 interfaces.
* Followings are each components of the engine.

### Robot Application Node Manager

* The robot application node manger manage life cycle of robot application nodes.
* Run or stop request of robot applications are implemented by ROS2 action.&#x20;

### Communication Bridge

* The communication bridge manages the connection with external devices or modules and converts the data exchanged through communication to ROS2 interface.
* Some communication bridge may contain communication protocols either.

#### Mobile Bridge

* The mobile bridge is communication bridge for mobile applications running on mobile devices such as tablet PC.

#### Web Bridge

* The web bridge convert HTTP/HTTPS requests to ROS2 interfaces.

#### Ethernet Bridge

* The ethernet bridge manage socket connection with the [Control Module](control-module.md) and convert the control module interface to ROS2 interface.

### DB Manager

* The DB manager manages uploading and downloading ROS2 messages to cloud DB and local DB either.

### Local Machine Controller

* The local machine controller controls and manages hardware of application module, providing ROS2 interface.
* For example, the local machine controller of M30 controls and manages hardware of Jetson Xavier.

#### Audio Controller

#### Device Status Monitor

#### Network Manger

### ROS2 Custom Message Package

## System Manager

## OTA Manager

##

###
