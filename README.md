# Robot Configurations

## Summary
Provides a single repository for robot configurations used in lab projects/studies
with non-standard MoveIt configurations and/or robot descriptions.

## Workflow

To install, simply clone the repository into your catkin workspace and install
the relevant dependencies for the robot being used (see below). Note that MoveIt
should be installed. If using only the robot descriptions for an alternate planner
(such as [Relaxed-IK](https://github.com/uwgraphics/relaxed_ik)) then refer to the
[sub-package documentation](./relaxed_ik_robot_configs/README.md) to setup
configurations along with the official Relaxed-IK setup documentation.

When extending this repository, ensure that contributions do not fail to build
when dependencies are not installed. As an example, if using a UR5 then Kinova
dependencies should not be required for catkin_make to successfully build.

## Robots
- UR 3 + Robotiq 85
- UR 5 + Robotiq 85
- UR 10 + Robotiq 85
- Kinova Mico + Kinova 2-Finger
- Kinova Mico + Kinova 3-Finger
- Kinova Mico + Robotiq 85

## Dependencies
- UR 3 / UR 5 / UR 10
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [ros-industrial/universal_robot](https://github.com/ros-industrial/universal_robot)
  - (optional) [ros-industrial/ur_modern_driver](https://github.com/ros-industrial/ur_modern_driver)
- Kinova Mico
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [Kinovarobotics/kinova-ros](https://github.com/Kinovarobotics/kinova-ros)
- General
  - (optional) [moveit](http://wiki.ros.org/moveit)
  - (optional) [uwgraphics/relaxed_ik](https://github.com/uwgraphics/relaxed_ik)

## Changelog

### 1.0.2 - 2019-06-10
### Added
- Added relaxek_ik_robot_configs sub-package (still in progress)
  - UR5 written
  - UR3, Mico, Mico2, Mico3 stubbed

### Changed
- Removed relaxed_ik data from robot_descriptions (now in separate)
- Updated high-level urdfs that reference relaxed_ik_configurations
- Updated mico moveit urdfs and configs to point to correct urdfs

### 1.0.1 - 2019-06-09
### Added
- Added relaxed-ik usable urdfs and supporting urdfs with robotiq 85 gripper
- Added Todo field in README

### Changed
- Updating README with optional dependencies
- Now providing relaxed-ik support for Mico w/ 3-Finger grippers

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
