# robotics

### [raspberry pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)
the linux computer on the robot, with a can adapter for the motors.

### [genesis](https://genesis-world.readthedocs.io)
physics simulation, to test motion code before it moves real metal. scenes are plain python, it loads a robot's urdf directly, and it runs on cpu or any gpu.
- **watch out**: proposed, not yet tried. the reBot arm's ready-made simulation files target mujoco and isaac sim, so here the arm's urdf has to be loaded and checked by hand.
- **not this**: mujoco.
