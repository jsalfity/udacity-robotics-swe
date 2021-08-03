## Project2 - "Ball Chaser"

Launch Gazebo: 

```roslaunch my_robot my_robot.launch```

Launch the ball chaser: 

```roslaunch ball_chaser ball_chaser.launch```. 

A simple proportional controller is implemented, `Kp` gain for `ang_z` and `lin_x` is set within `process_image.cpp`.