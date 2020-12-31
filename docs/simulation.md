# Simulation

- Spawn robot in an outdoor environment:

```sh
roslaunch spotmicro_config gazebo.launch
```

- Execute the navigation stack with RViz

```sh
roslaunch spotmicro_config slam.launch rviz:=true
```

- Send a 2D pose with RViz and see the robot moving
