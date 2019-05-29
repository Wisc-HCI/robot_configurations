# robot_configurations
## Summary
Provides a single repository of robot configurations used in lab projects/studies
with non-standard MoveIT configurations or robot descriptions.

When extending this repository, ensure that contributions do not fail to build
when dependencies are not installed. As an example, if using a UR5 then Kinova
dependencies should not be required for catkin_make.

## Dependencies
- UR 3 / UR 5 / UR 10
  - Wisc-HCI/robotiq_85_gripper
  - ros-industrial/universal_robot
  - (optional) ros-industrial/ur_modern_driver
- Kinova Mico
  - Kinovarobotics/kinova-ros
  - Wisc-HCI/robotiq_85_gripper

## TODO
- Update mico-robotiq moveit config meshes and urdf to robot description
- remove model.pdf ?
- create a change-log
- finish README documentation
- package.xml documentation cleaned up (also correct dependencies)
