# Robot Configurations

## Summary
Provides a single repository for robot configurations used in lab projects/studies
with non-standard MoveIt configurations and/or robot descriptions.

## Workflow

To install, simply clone the repository into your catkin workspace and install
the relevant dependencies for the robot being used (see below). Note that MoveIt
should be installed. If using only the robot descriptions for an alternate planner
(such as [Relaxed-IK](https://github.com/uwgraphics/relaxed_ik)) then either copy
the relevant URDFs or delete the unnecessary
packages from local repository clone.

When extending this repository, ensure that contributions do not fail to build
when dependencies are not installed. As an example, if using a UR5 then Kinova
dependencies should not be required for catkin_make to successfully build.

## Robots
- UR 3 + Robotiq 85
- UR 5 + Robotiq 85
- UR 10 + Robotiq 85
- Kinova Mico + Kinova 2-Finger
- Kinova Mico + Robotiq 85

## Dependencies
- UR 3 / UR 5 / UR 10
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [ros-industrial/universal_robot](https://github.com/ros-industrial/universal_robot)
  - (optional) [ros-industrial/ur_modern_driver](https://github.com/ros-industrial/ur_modern_driver)
- Kinova Mico
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [Kinovarobotics/kinova-ros](https://github.com/Kinovarobotics/kinova-ros)

## Changelog

### 1.0.0 - 2019-05-29
#### Added
- Kinova Mico MoveIt configurations
- BSD License
- robot_configurations metapackage

#### Changed
- Updated README with new direction for robot_configurations
- UR MoveIt configurations
- Updated dependencies

#### Removed
- UR specifics such as drivers, gazebo packages, etc.

### 0.0.0 - 2018-xx-xx
#### Added
- Added URDFs for UR robots with Robotiq85 grippers
- Added MoveIt configurations for UR robots with Robotiq85 grippers

#### Changed
- Forked from ros-industrial/universal_robot
