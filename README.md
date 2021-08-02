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
gazebo ./udacity-robotics-swe/project/world/salfity_world.world
```

## Project2 - "Ball Chaser"

Launch Gazebo: 

```roslaunch my_robot world.launch```

Launch the ball chaser: 

```roslaunch ball_chaser ball_chaser.launch```. 

A simple proportional controller is implemented, `Kp` gain for `ang_z` and `lin_x` is set within `process_image.cpp`.

## Project3 - "Where am I"