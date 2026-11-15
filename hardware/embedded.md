# embedded

microcontrollers and the code on them.

### [esp32-s3-devkitc-1 (n16r8)](https://docs.espressif.com/projects/esp-dev-kits/en/latest/esp32s3/esp32-s3-devkitc-1/)
the networked board when a project needs many pins, usb or a camera.

### [xiao esp32-c6](https://wiki.seeedstudio.com/xiao_esp32c6_getting_started/)
the small networked board for sensors and switches.

### [raspberry pi pico 2 w](https://www.raspberrypi.com/products/raspberry-pi-pico-2/)
the board for precise timing.
- **watch out**: keep a [raspberry pi debug probe](https://www.raspberrypi.com/products/debug-probe/) attached, so an agent can flash and debug without anyone pressing a button.
- **not this**: a new chip family per project.

### rust with [embassy](https://embassy.dev)
the firmware language and async framework: [esp-hal](https://github.com/esp-rs/esp-hal) on esp32, [embassy-rp](https://docs.embassy.dev/embassy-rp) on the pico. one language across both chips.
- **watch out**: maturity on the esp32-c6 and the pico 2's chip is not confirmed. c with esp-idf is the fallback.

### [probe-rs](https://probe.rs)
flashing and debugging from one command line, for both chips.

### [embedded-test](https://github.com/probe-rs/embedded-test)
firmware tests that run on the real chip. probe-rs flashes them, resets the board between cases and reports results like a normal rust test run. async tests work with embassy.
- **reach for it when**: any firmware test. the boards stay plugged in, so there is nothing to simulate.
- **not this**: wokwi. its simulator is closed and runs on their servers (50 free minutes a month, offline use only on the €20 plan).

## contextual

- [esphome](https://esphome.io) into [home assistant](https://www.home-assistant.io): a sensor or a switch is a yaml file. use it instead of custom firmware when the device only reports or toggles something.
