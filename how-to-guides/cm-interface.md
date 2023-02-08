---
description: How to control CM
---

# CM Interface

### Network Setting

* local network
  * **ip:port** 169.254.162.187:1818
  * **subnetmask** 255.255.0.0
  * **gateway** 169.254.162.1
* using router
  * **ip:port** 192.168.0.181:1818
  * **subnetmask** 255.255.255.0
  * **gateway** 192.168.0.1
  * note address must be 192.168.**0**.x

### Required Package/Node

* cm\_manager/cm\_manager

****

### Configuration

Edit config/cm\_manager.yaml. Params will be set automatically at launch.

* launching cm\_manager:

```
ros2 launch cm_manager cm_manager.launch.py
```

* getting param file

while cm\_manager launched,

```
ros2 param dump /cm_manager --output-dir ${dir to your param file}
```

* setting param

while cm\_manager launched,

```
ros2 param load /cm_manager ${dir to your param file}
```



### CM State Management

cm\_manager produces interface for CM state via ROS2 service.

* setting state
  * call /system/set\_device\_state
  * interface
    * device\_name : list of device name to set
    * device: list of set info
      * state: target state enum
      * routine: list of routine name to set



### CM Topics

* general naming
  * **cmd**: command from AM to CM
  * **target**: command from CM to target HW
  * **state**: feedback measured by HW

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>cmd, target, state</p></figcaption></figure>

* joint
  * /joint/state (sensor\_msgs/msg/JointState)
    * name: joint names
    * position: absolute joint positions (measured by motor driver) \[deg]
    * velocity: joint angular velocity (measured by motor driver) \[deg/sec]
    * effort: actual driving current (measured by motor driver) \[A]
  * /joint/cmd (sensor\_msgs/msg/JointState)
    * position: position command \[deg]
    * effort: current command \[A]
  * /joint/target (sensor\_msgs/msg/JointState)
    * position: processed position command \[deg]
    * effort: processed current command \[A]
  * /joint/ctrl\_params (std\_msgs/msg/Float32MultiArray)
    * control paramters for joint
    * layout/dim\[\*]/lable: name of parameter
    * layout/dim\[\*]/size: size of data
    * data: series of all data
* /sensor
  * /sensor/btns (sys\_msgs/msg/Buttons)
    * button state
  * /sensor/foot (sys\_msgs/msg/FootSensor)
    * foot module data
    * reaction: ground reaction force/moment (geometry\_msgs/Twist)
    * contact: is ground contact?
    * bump: bump senosr raw data
* /tf
  * tf of robot model

