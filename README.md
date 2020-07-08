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
dependencies should not be required for catkin_make to successfully build. A notable exception is for MoveIt, which if not installed may necessitate deletion of `*_moveit_config` directories.

## Robots
- UR 3 + Robotiq 85
- UR 5 + Robotiq 85
- UR 10 + Robotiq 85
- Kinova Mico + Kinova 2-Finger
- Kinova Mico + Kinova 3-Finger
- Kinova Mico + Robotiq 85
- UR 3e + Robotiq 85 (in development)
- Franka Emika Panda (in development)

## Dependencies
- Universal Robots UR 3 / UR 5 / UR 10 / UR 3e
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
    - Use the remote serial version of the driver
  - [fmauch/universal_robot](https://github.com/fmauch/universal_robot)
    - Use this fork until merged into [ros-industrial](https://github.com/ros-industrial/universal_robot)
  - [industrial_core](wiki.ros.org/industrial_core) via `apt install ros-<VERSION>-industrial-core`
  - (Optional) [UniversalRobots/Universal_Robots_ROS_Driver](https://github.com/UniversalRobots/Universal_Robots_ROS_Driver)

- Kinova Mico
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [Kinovarobotics/kinova-ros](https://github.com/Kinovarobotics/kinova-ros)

- Franka Emika Panda
  - [frankaemika/franka_ros](https://github.com/frankaemika/franka_ros)

- General
  - (Optional) [moveit](http://wiki.ros.org/moveit) vai `apt install ros-<VERSION>-moveit`
  - (Optional) [uwgraphics/relaxed_ik](https://github.com/uwgraphics/relaxed_ik)

## Deprecated Dependencies
- (Deprecated) Universal Robots UR 3 / UR 5 / UR 10
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
  - [ros-industrial/universal_robot](https://github.com/ros-industrial/universal_robot)
  - (Optional) [ros-industrial/ur_modern_driver](https://github.com/ros-industrial/ur_modern_driver)
  - [industrial_core](https://wiki.ros.org/industrial_core) via `apt install ros-<VERSION>-industrial-core`

- (Deprecated) Universal Robots [UR 3e](./_documentation/OLD_SETUP_UR3E.md)
  - [Wisc-HCI/robotiq_85_gripper](https://github.com/Wisc-HCI/robotiq_85_gripper)
    - Must use URScript Driver!
  - [ros-industrial/universal_robot](https://github.com/ros-industrial/universal_robot)
    - Need version with UR e-series support (See [notes](./_documentation/OLD_SETUP_UR3E.md) for changes)
  - [industrial_core](wiki.ros.org/industrial_core) via `apt install ros-<VERSION>-industrial-core`
  - [dniewinski/ur_modern_driver](https://github.com/dniewinski/ur_modern_driver.git)
    - Must use this fork until merged into [ros-industrial](https://github.com/ros-industrial/universal_robot) (See [notes](./_documentation/OLD_SETUP_UR3E.md) for setup)

## Changelog

### 1.0.4 - 2020-06-28
- updated README documentation for UR robots usng Universal_Robots_ROS_Driver
- updated README documentation for Panda robot

### 1.0.3 - 2019-06-25
### Added
- robot_bringup package added
  - support for physical UR robots in lab
- Support for UR3e started
- Setup documentation provided
- Nao descriptions and relaxed_ik configurations
- Updating robot_descriptions subdiretory kinova_mico to kinova
  - changes to moveit config follows

### Changed
- Updating README documentation for UR3e support

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
