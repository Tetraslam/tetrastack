# rejected

what not to reach for in a hardware project, and why. read this before adding anything that isn't in [the hardware stack](README.md).

| what | instead | why |
| --- | --- | --- |
| [mujoco](https://mujoco.org) | genesis | hated the experience. genesis scenes are plain python and load a urdf directly |
| [newton](https://github.com/newton-physics/newton) | genesis | its main physics backend is mujoco, and it wants an nvidia gpu |
| [maniskill](https://www.maniskill.ai) | genesis, and lerobot if learning is needed | built for training policies at scale in simulation, which isn't the plan. a second physics engine. slowing: last commit august 2026 |
| [ros 2](https://docs.ros.org) | plain python with motorbridge and pinocchio | heavy, and agents writing arm code directly don't need it |
| [wokwi](https://wokwi.com) | embedded-test on the real chip | the simulator is closed and runs on their servers |
| [atopile](https://atopile.io) | kicad, and tscircuit to try | the open repository stopped in march 2026 and the product moved to a hosted workspace |
| [backplane](https://github.com/BackplaneWorks/Backplane) as the workspace | kicad driven directly, with kistack skills | a second agent harness. still on the watch list in [design](design.md) |
| fusion 360 | build123d | closed, cloud, no linux |
| closed printer firmware | klipper | no api an agent can call |
| instruments with only a front panel | anything scriptable | an agent can't use them |
