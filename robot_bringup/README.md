# robot_bringup

If during development of a new robotic platform in the lab, one needs to change
the original launch files for general use in the lab then please add them here.

The sole purpose of this package is to provide ready to deploy versions of launch
files instead of having to change them in their original package. This was
motivated by the ur_modern_driver which for what ever reason, has their software
stack easily deployable is just controlling the robot but a pain if actually
integrating the robot as part of a larger system.

The real issue with all of these is that they build in URDF loads and inflexible
joint/tf publishing schemes that don't play well with other components.
