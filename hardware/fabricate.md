# fabricate

turning a design into an object, at home or by order.

### [orcaslicer](https://github.com/OrcaSlicer/OrcaSlicer)
the slicer, run from the command line.
- **watch out**: for the snapmaker u1, use [snapmaker orca](https://github.com/Snapmaker/OrcaSlicer), snapmaker's open fork (agpl, linux builds). mainline orcaslicer still has open u1 issues around multi-colour prints. the fork's command line is not yet tried.
- **not this**: slicers that only work by clicking.

### [klipper](https://www.klipper3d.org) + [moonraker](https://moonraker.readthedocs.io)
printer firmware, and the http api in front of it. moonraker is what an agent calls to upload a file, start a print and read temperatures.
- **reach for it when**: every printer. one interface for the snapmaker and the ender.
- **watch out**: the u1 already runs klipper, but ssh and open access need the community [extended firmware](https://github.com/paxx12-snapmaker-u1/SnapmakerU1-Extended-Firmware), and damage caused by it is not covered by warranty. on the ender, klipper runs on a linux computer that stays plugged into the printer over usb for the whole print, so use a machine that stays home.
- **not this**: printers with closed firmware.

### [jlcpcb](https://jlcpcb.com)
circuit boards and assembly.
- **watch out**: choose parts from [lcsc](source.md) first, because assembly pulls from its catalog.
- **not this**: hand-soldering small surface-mount parts.

### [jlccnc](https://jlccnc.com) / [jlc3dp](https://jlc3dp.com)
machined metal, and printing in materials the home printers can't do.
- **reach for it when**: a part is not flat and can't be printed at home.

### [sendcutsend](https://sendcutsend.com)
laser-cut and bent sheet metal.
- **reach for it when**: flat or folded metal parts.
- **not this**: buying a mill or a laser yet.
