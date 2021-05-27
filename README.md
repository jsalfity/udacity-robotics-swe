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
