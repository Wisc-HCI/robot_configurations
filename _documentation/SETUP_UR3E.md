# Setup UR3e

## Setting up ur_modern_driver

At the time of writing this documentation support for the UR3e with ROS is still in development. The solution provided may break with future work.

Currently tested with UR-Polyscope 5.3.

1. Clone fork of [ur_modern_driver](https://github.com/dniewinski/ur_modern_driver)
  - An alternative that may work is found [here](https://github.com/akihikoy/ur_modern_driver/tree/kinetic-devel)
    - tried this one but could not get to build.
  - Cannot use original repository, currently results in a deserializing packet error.

2. Install [controller_manager](http://wiki.ros.org/controller_manager)
  - Needed to build the UR driver.

3. Before launch,
  - Need to enable Remote Control
    - Menu > Settings > System > Remote Control > Enable
  - Need to select Remote Control mode instead of Local mode
  - Setup or determine your network address

4. Update launch file or use robot_configurations file
  - reverse port missing in ur_common.launch this needs to be removed from the bringup files. (Or use use the file provided in robot_configurations).

5. If using MoveIt, need to update the universal_robot package e-series MoveIt planning context launch files.
  - Currently they point to UR3 URDFs instead of the UR3e URDFs.
  - Alternatively use the MoveIt configuraiton provided in the robot_configurations repository.

## Setting up robotiq_driver

Provided in the [Lab's Robotiq driver repository](https://github.com/Wisc-HCI/robotiq_85_gripper) is an action server
to send a URScript to the UR3e robot to control the gripper. This requires the
ur_modern_driver to run.

Driver is currently under development, thus not all features are available at
this time. Note: it does not receive feedback and just delays for assumed time.

Run this node with values:
```
rosrun robotiq_85_driver urscript_gripper_action_server.py speed:=255 urscript_topic:=/ur_driver/URScript
```

## Known Issues
- universal_robot package e-series MoveIt planning context need to be changed to correct URDFs.
  - Currently they point to UR3 URDFs instead of the UR3e URDFs.

- ur_modern_driver reverse port missing in ur_common.launch.
  - Need to use the robot_bringup launch files provided in the robot_configurations repository.

- After a protective stop, MoveIt seems to freeze up when commanding robot. Need to restart driver.
  - This may be a problem with switching to local mode in general (unconfirmed)

- Robot must be powered and brake-released to control the robot, however joint-states are provided when powered but still locked.

- If using ROS melodic, then all moveit packages that have 'move_group/MoveGroupExecuteService' loaded in move_group under capabilities needs to have it removed to run without error.

- ur_modern driver launches a robot_state_publisher which we don't always want.

- ur_modern_driver sends out to joint_states. Use the robot_bringup launch file which wraps this with a namespace.
