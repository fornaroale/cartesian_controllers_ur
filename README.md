# Cartesian Controllers on Universal Robots

A minimal setup to get the ROS2 UR driver up and running with the `cartesian_controllers` for a *UR10e* robot.

## Setup

To get this up & running:
- install [these controllers](https://github.com/fzi-forschungszentrum-informatik/cartesian_controllers/tree/ros2)
- download the package and build it with colcon
- source the workspace
- start UR10e robot and controllers: `ros2 launch cartesian_controllers_universal_robots robot.launch.py`
- switch to the desired controller (eg. `ros2 control switch_controllers --deactivate scaled_joint_trajectory_controller --activate cartesian_motion_controller`)
- publish on target topic to try it out (eg. `ros2 topic pub --once /target_frame geometry_msgs/msg/PoseStamped '{header: {stamp: now, frame_id: "base_link"}, pose: { position: {x: 0.5, y: 0.5, z: 0}, orientation: {x: 0, y: 0, z: 0, w: 1}}}'`)
