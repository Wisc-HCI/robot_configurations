## Relaxed-IK Robot Configurations

Relaxed-IK requires generation of configuration files in order to make use of
the planner. In this package, several configurations are stored than quickly
allow one to get started using Relaxed-IK.

Robot configurations are stored as directories with a collision file, urdf, and setup file.
In order to setup Relaxed-IK these files need to copied into the Relaxed-IK package.

Navigate to `relaxed_ik/src/` then overwrite setup.py with one provided. Note
you will need to change the name from `start_here_<robot>.py` to `start_here.py`.

Then copy the collision file to `relaxed_ik/src/RelaxedIK/Config/collision_files/`
and copy the urdf to `relaxed_ik/src/RelaxedIK/urdfs/`.

Next generate your full configuration. When invoking load, change `info_<robot>.yaml`
for your robot being configured. Note, these instructions taken from the setup.py file,
refer to that file for further documentation.

```
roslaunch relaxed_ik generate_info_file.launch
roslaunch relaxed_ik load_info_file.launch info_file_name:=info_robot.yaml
```

Then preprocess according to your use case.

```
roslaunch relaxed_ik preprocessing_julia.launch
roslaunch relaxed_ik preprocessing_python.launch
```
You are now ready to use Relaxed-IK!

## Ready

- UR5

## In Progress

- UR3
- Mico
- Mico2
- Mico3
