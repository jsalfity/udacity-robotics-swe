# Udacity Robotics SWE 

## Project1 - "Build My World"

Plugin Build Instructions:

```sh
cd <full/path>/udacity-robotics-swe/project1
mkdir build
cd build/
cmake ../
make 
export GAZEBO_PLUGIN_PATH=<full/path>/udacity-robotics-swe/project1/build
```

Specific to Gazebo7, in `CMakeLists.txt`:

```sh
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}") # Does not compile
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GAZEBO_CXX_FLAGS}" # Correct
```

Launching Gazebo `salfity_world.world`:

```sh
gazebo ./udacity-robotics-swe/project2/world/salfity_world.world
```

## Project2 - "Ball Chaser"

Launch Gazebo: 

```roslaunch my_robot world.launch```

Launch the ball chaser: 

```roslaunch ball_chaser ball_chaser.launch```. 

A simple proportional controller is implemented, `Kp` gain for `ang_z` and `lin_x` is set within `process_image.cpp`.

## Project3 - "Where am I"

Creating the map with `pgm_map_creator`, have to fix `pgm_map_creator/msgs/CMakeLists.txt` and comment out:

```sh
  set (msgs
  collision_map_request.proto
  # ${PROTOBUF_IMPORT_DIRS}/vector2d.proto
  # ${PROTOBUF_IMPORT_DIRS}/header.proto
  # ${PROTOBUF_IMPORT_DIRS}/time.proto
)
```

Make the package:

```sh
cd project3/catkin_ws
catkin_make
```

Launch the robot in the gazebo world:

```sh
roslaunch my_robot world.launch
```

Launch the `amcl` node:

```sh
roslaunch my_robot amcl.launch
```

Either send a command in rviz with `Send 2DGoal` or command by teleop:

```sh
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
