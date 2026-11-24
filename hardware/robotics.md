# robotics

### [genesis](https://genesis-world.readthedocs.io)
physics simulation, to test motion code before it moves real metal. scenes are plain python, it loads a robot's urdf directly, and it runs on cpu or any gpu.
- **watch out**: tried once, on cpu with no display (genesis 1.4.6): it loaded the [reBot arm](https://github.com/Seeed-Projects/reBot-DevArm)'s urdf, drove the joints to targets, respected joint limits and rendered a camera image. the first build took 72 seconds; 300 steps then took under a tenth of a second. `pip install genesis-world` did not pull in torch or matplotlib, so install those too. contact and grasping are not yet tried.
- **watch out**: used for real on 2026-11-24 (genesis 1.5.0, on the gpu, in [athanor's golem](https://github.com/tetraslam/athanor/tree/master/builds/golem)), a pick and place with the reBot arm:
  - load seeed's mujoco file (`RS/mjcf/rs_arm.xml`), not the urdf. each urdf finger gets wrapped in one convex shape, which turns a pointed finger into a wedge that squeezes a block out of its grip. the mujoco file splits the fingers into pieces and the same grasp held first try.
  - `inverse_kinematics` hands back its best try with no sign that it failed. move the arm there and measure the miss yourself.
  - with the gripper pointing straight down the fingertips top out near 10 cm, because the wrist bends only 90 degrees.
  - the api moved in ten days: `start_recording` now takes the filename, and `stop_recording` takes nothing.
  - first build 87 seconds, then about 10 from the cache. a whole pick and place with a 60 fps recording runs in 16.
  - seeed tuned and checked its contact numbers in mujoco. whether genesis honours all of them is unknown, so when the real arm disagrees with the simulation, suspect that first.
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

### [orbbec gemini 305](https://store.orbbec.com/products/gemini-305)
the wrist camera: colour and depth, $229. depth starts at 4 cm, which is where a gripper works, and both sensors capture the whole frame at once, so images don't smear when the arm moves. read from python with [pyorbbecsdk](https://github.com/orbbec/pyorbbecsdk) (mit, no kernel patches).
- **watch out**: seeed's wrist bracket is named for the d405 and the 305 together, but the fit is unchecked. lerobot has no orbbec support, so it would need a small adapter.
- **not this**: the realsense d435i and gemini 2 on the wrist. their depth starts at 28 cm and 15 cm.

### [logitech c920s](https://www.logitech.com/en-us/shop/p/c920s-pro-hd-webcam)
the overhead camera: a plain $70 webcam on a fixed mount, for a view of the whole workspace. linux reads it natively.

## contextual

- [realsense d405](https://store.realsenseai.com/buy-realsense-depth-camera-d405.html) ($325): the wrist camera if lerobot support out of the box matters more than $96 and the closest 3 cm of depth.
- [raspberry pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/): the linux computer on a robot that moves. a robot that sits on a desk uses a usb-to-can adapter into a computer that is already there.
- [lerobot](https://huggingface.co/docs/lerobot): teaching the arm by demonstration, when agent-written code isn't enough for a task. seeed has a [guide for the reBot arm](https://wiki.seeedstudio.com/rebot_arm_b601_rs_lerobot/).
