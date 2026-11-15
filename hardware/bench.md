# bench

instruments an agent can drive, so it can set a voltage and read a signal without anyone at the front panel. none of these are bought or tried yet; prices are from 2026-11-15.

### [sparkfun usb logic analyzer](https://www.sparkfun.com/usb-logic-analyzer-24mhz-8-channel.html) on [sigrok](https://sigrok.org)
8 channels at 24 mhz, $27. [`sigrok-cli`](https://sigrok.org/wiki/Sigrok-cli) captures and decodes digital signals from a script, using the `fx2lafw` driver in the packaged release.
- **reach for it when**: checking what a chip is actually saying on a wire.
- **watch out**: sigrok is barely maintained (last releases 2019 to 2021). it works, and nothing open has replaced it. the upgrade is the [dslogic plus](https://www.dreamsourcelab.com/shop/logic-analyzer/dslogic-plus/) ($149).
- **not this**: the newer dslogic u2basic, u3pro16 and u3pro32. sigrok does not support them.

### [siglent sds804x hd](https://siglentna.com/product/sds804x-hd/)
the oscilloscope: 4 channels, 70 mhz, 12-bit, about $460. it takes [scpi](https://en.wikipedia.org/wiki/Standard_Commands_for_Programmable_Instruments) text commands over the network, driven from python with [pyvisa-py](https://github.com/pyvisa/pyvisa-py) and no vendor software.
- **reach for it when**: an analog signal needs looking at. buy it then, not before.

## contextual

- power supply: use the makerspace one. buy the [siglent spd1168x](https://siglentna.com/product/spd1168x/) ($305, scpi over the network) only when an agent has to power-cycle or sweep a voltage unattended. it stops at 16 volts, so it can't run 24-volt motors.
- [nordic ppk2](https://www.nordicsemi.com/Products/Development-hardware/Power-Profiler-Kit-2) ($107): measures how much current a device draws over time, read from python with [ppk2-api-python](https://github.com/IRNAS/ppk2-api-python). only for battery-powered devices.
- [glasgow](https://glasgow-embedded.org) ($179 at [crowd supply](https://www.crowdsupply.com/1bitsquared/glasgow)): an open tool driven from python for talking to chips and buses directly. it does not replace the logic analyzer; its built-in one was removed from the code pending a rework.

**not this**: instruments with only a front panel, and budget supplies (riden, alientek dp100) whose control libraries are reverse-engineered and dormant.
