# robotics

### [genesis](https://genesis-world.readthedocs.io)
physics simulation, to test motion code before it moves real metal. scenes are plain python, it loads a robot's urdf directly, and it runs on cpu or any gpu.
- **watch out**: tried once, on cpu with no display (genesis 1.4.6): it loaded the [reBot arm](https://github.com/Seeed-Projects/reBot-DevArm)'s urdf, drove the joints to targets, respected joint limits and rendered a camera image. the first build took 72 seconds; 300 steps then took under a tenth of a second. `pip install genesis-world` did not pull in torch or matplotlib, so install those too. contact and grasping are not yet tried.
- **not this**: mujoco.

### [motorbridge](https://motorbridge.seeedstudio.com)
seeed's python library for reading and commanding the arm's motors over can. the one motor interface, for the arm and whatever follows it.
- **not this**: hobby servos for anything load-bearing.

### [pinocchio](https://github.com/stack-of-tasks/pinocchio)
arm math: where the hand is for given joint angles, the joint angles for a wanted hand position, and gravity compensation.
- **reach for it when**: any code that moves the arm to a position. seeed ships an [integration for the reBot arm](https://wiki.seeedstudio.com/rebot_arm_b601_rs_pinocchio_meshcat/) ([repo](https://github.com/Seeed-Projects/reBotArm_control_py)).

### [rerun](https://rerun.io)
records what a robot sees and does (cameras, joint angles, 3d poses) on one timeline, and plays it back.
- **reach for it when**: every robot run. log from the start, so there is a recording when something goes wrong.

## contextual

- [raspberry pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/): the linux computer on a robot that moves. a robot that sits on a desk uses a usb-to-can adapter into a computer that is already there.
- [lerobot](https://huggingface.co/docs/lerobot): teaching the arm by demonstration, when agent-written code isn't enough for a task. seeed has a [guide for the reBot arm](https://wiki.seeedstudio.com/rebot_arm_b601_rs_lerobot/).
