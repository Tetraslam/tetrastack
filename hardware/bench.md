# bench

instruments an agent can drive, so it can set a voltage and read a signal without anyone at the front panel. none of these are bought or tried yet; prices are from 2026-11-15.

### [sparkfun usb logic analyzer](https://www.sparkfun.com/usb-logic-analyzer-24mhz-8-channel.html) on [sigrok](https://sigrok.org)
8 channels at 24 mhz, $27. [`sigrok-cli`](https://sigrok.org/wiki/Sigrok-cli) captures and decodes digital signals from a script, using the `fx2lafw` driver in the packaged release.
- **reach for it when**: checking what a chip is actually saying on a wire.
- **watch out**: sigrok is barely maintained (last releases 2019 to 2021). it works, and nothing open has replaced it. if it gets in the way, fork it and build from source. the upgrade is the [dslogic plus](https://www.dreamsourcelab.com/shop/logic-analyzer/dslogic-plus/) ($149).
- **not this**: the newer dslogic u2basic, u3pro16 and u3pro32. sigrok does not support them.

### [siglent spd1168x](https://siglentna.com/product/spd1168x/)
the power supply an agent can drive: 16 volts, 8 amps, $305, scpi over usb or the network with [pyvisa-py](https://github.com/pyvisa/pyvisa-py).
- **reach for it when**: an agent has to power-cycle a board or sweep a voltage on its own.
- **watch out**: it stops at 16 volts, so it can't run the arm's 24-volt motors.

## buy later

### [siglent sds804x hd](https://siglentna.com/product/sds804x-hd/)
the oscilloscope: 4 channels, 70 mhz, 12-bit, about $460. it takes [scpi](https://en.wikipedia.org/wiki/Standard_Commands_for_Programmable_Instruments) text commands over the network, driven from python with [pyvisa-py](https://github.com/pyvisa/pyvisa-py) and no vendor software.
- **reach for it when**: an analog signal needs looking at.

### [nordic ppk2](https://www.nordicsemi.com/Products/Development-hardware/Power-Profiler-Kit-2)
measures how much current a device draws over time, $107, read from python with [ppk2-api-python](https://github.com/IRNAS/ppk2-api-python).
- **reach for it when**: the first battery-powered device.

## contextual

- 24-volt and high-current work: the makerspace supply (25 volts, 10 amps). it is manual only, so a person sets it.
- [glasgow](https://glasgow-embedded.org) ($179 at [crowd supply](https://www.crowdsupply.com/1bitsquared/glasgow)): an open tool driven from python for talking to chips and buses directly. it does not replace the logic analyzer; its built-in one was removed from the code pending a rework.

**not this**: instruments with only a front panel, and budget supplies (riden, alientek dp100) whose control libraries are reverse-engineered and dormant.
