## Changelog

### 1.0.6 - 2021-02-24
- moveit_robot_configs updated package build and run dependencies for robot_descriptions

### 1.0.5 - 2021-01-21
- Added panda_kinetic_intertial URDF, needed for Unity-ROS# robot importing
- Changelog is now separate from README
- Updating license documentation

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
