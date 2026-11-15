# bench

instruments an agent can drive, so it can set a voltage and read a signal without anyone at the front panel.

### logic analyzer on [sigrok](https://sigrok.org)
capture and decode digital signals from the command line with [`sigrok-cli`](https://sigrok.org/wiki/Sigrok-cli).

### [glasgow](https://glasgow-embedded.org)
an open bench tool driven from python and the command line, for talking to chips and buses directly.
- **reach for it when**: probing or driving a digital interface from a script.
- **watch out**: it does not replace the logic analyzer. its built-in one was removed from the code pending a rework. $179 at [crowd supply](https://www.crowdsupply.com/1bitsquared/glasgow), in stock as of 2026-11-15. not bought yet.

### power supply and oscilloscope with [scpi](https://en.wikipedia.org/wiki/Standard_Commands_for_Programmable_Instruments)
any model that takes scpi commands over usb or the network. no models picked yet.
- **not this**: instruments with only a front panel.
