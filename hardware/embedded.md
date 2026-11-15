# embedded

microcontrollers and the code on them.

### [esp32-s3-devkitc-1 (n16r8)](https://docs.espressif.com/projects/esp-dev-kits/en/latest/esp32s3/esp32-s3-devkitc-1/)
the networked board when a project needs many pins, usb or a camera.
- **watch out**: for rust, its chip needs espressif's own build of the compiler, installed with [espup](https://github.com/esp-rs/espup). the xiao esp32-c6 builds with stable rust.
- **not this**: a new chip family per project.

### [xiao esp32-c6](https://wiki.seeedstudio.com/xiao_esp32c6_getting_started/)
the small networked board for sensors and switches.

### rust with [embassy](https://embassy.dev)
the firmware language and async framework: [esp-hal](https://github.com/esp-rs/esp-hal) on esp32, and [embassy-rp](https://docs.embassy.dev/embassy-rp) if a pico is ever used.
- **reach for it when**: the device runs unattended, needs exact timing or low power, or sits on a custom board.
- **watch out**: wi-fi and bluetooth on esp32 come from [esp-radio](https://github.com/esp-rs/esp-hal/tree/main/esp-radio), which is still in beta and needs esp-hal's `unstable` feature. accepted: an agent can debug it. 

### [circuitpython](https://circuitpython.org)
python on the chip. adafruit writes its sensor drivers for it, and it has builds for both boards above.
- **reach for it when**: trying out a sensor or breakout, or any device where an adafruit driver exists and timing doesn't matter. move to rust when the device becomes permanent or needs exact timing.
- **watch out**: [micropython](https://micropython.org) is a fine swap when a project needs something circuitpython lacks. agents write both.

### [probe-rs](https://probe.rs)
flashing and debugging from one command line. the esp32 boards have a debug interface built into their usb port, so no extra probe is needed.

### [embedded-test](https://github.com/probe-rs/embedded-test)
firmware tests that run on the real chip. probe-rs flashes them, resets the board between cases and reports results like a normal rust test run. async tests work with embassy.
- **reach for it when**: any firmware test. the boards stay plugged in, so there is nothing to simulate.
- **not this**: wokwi. its simulator is closed and runs on their servers (50 free minutes a month, offline use only on the €20 plan).

## which language

- on the computer (cad, robot control, tests, tooling): python.
- on the chip, trying a sensor or building something quick: circuitpython.
- on the chip, permanent, timing-critical or low-power: rust with embassy.
- a device that only reports or toggles something for the house: esphome, no code.

## contextual

- [raspberry pi pico 2 w](https://www.raspberrypi.com/products/raspberry-pi-pico-2/): only when a project needs signal timing the esp32 can't give (its programmable i/o blocks generate exact waveforms). the esp32 boards cover everything else, so don't stock it. with one, add a [raspberry pi debug probe](https://www.raspberrypi.com/products/debug-probe/) for flashing over a wire.
- [esphome](https://esphome.io) into [home assistant](https://www.home-assistant.io): a sensor or a switch is a yaml file. use it instead of custom firmware when the device only reports or toggles something.
