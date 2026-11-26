# fabricate

turning a design into an object, at home or by order.

### [orcaslicer](https://github.com/OrcaSlicer/OrcaSlicer)
the slicer, run from the command line.
- **watch out**: the snapmaker u1 uses [snapmaker orca](https://github.com/Snapmaker/OrcaSlicer), snapmaker's open fork (agpl, linux builds). mainline orcaslicer still has open u1 issues around multi-colour prints. the fork's command line is not yet tried.
- **watch out**: slicing from a script, tried on 2026-11-25 (snapmaker orca 2.4.1 flatpak, in [athanor's slice.py](https://github.com/tetraslam/athanor/blob/master/lib/athanor/slice.py)). it works, and a 250 mm part slices in two seconds. four things it took to get there: the command line wants each profile as one whole file, so the `inherits` chains have to be flattened first. the key `wipe_tower_filament` in the u1's process profile crashes it outright (segfault, no message), so drop it. set `curr_bed_type` to `Textured PEI Plate`, or it assumes a cool plate and heats the bed to 35 instead of 65. and the flatpak can't see `/tmp`, only the home folder.
- **watch out**: the u1 answers on the network out of the box (2026-11-25, stock firmware 2.1.2): it announces itself as `_snapmaker._tcp`, and moonraker on port 7125 answers status queries with no login. uploading a g-code file and starting it works the same day (`POST /server/files/upload`, then `/printer/print/start?filename=`). the camera works on stock firmware, one frame at a time: send the json-rpc call `camera.start_monitor` with `{"domain": "lan", "interval": 0}` over moonraker's websocket (no token needed on the lan), and two seconds later a fresh 1920x1080 picture is at `/server/files/camera/monitor.jpg`. athanor's `printer.look()` does this. moonraker lists no webcam and `/webcam/` answers 502, so a smooth live stream still needs the [extended firmware](https://github.com/paxx12-s/SnapmakerU1-Extended-Firmware). each print's timelapse also lands in a read-only file root called `camera` (`/server/files/camera/<name>.mp4`), so an agent can see a print after it finishes.
- **not this**: slicers that only work by clicking.

### [klipper](https://www.klipper3d.org) + [moonraker](https://moonraker.readthedocs.io)
printer firmware, and the http api in front of it. moonraker is what an agent calls to upload a file, start a print and read temperatures.
- **reach for it when**: every printer. one interface for the snapmaker and the ender.
- **watch out**: the u1 already runs klipper, but ssh and open access need the community [extended firmware](https://github.com/paxx12-snapmaker-u1/SnapmakerU1-Extended-Firmware), and damage caused by it is not covered by warranty. on the ender, klipper runs on a linux computer that stays plugged into the printer over usb for the whole print, so use a machine that stays home.
- **not this**: printers with closed firmware.

### [jlcpcb](https://jlcpcb.com)
circuit boards and assembly.
- **watch out**: choose parts from [lcsc](source.md) first, because assembly pulls from its catalog. make the order files (gerbers, parts list, placement file) with [fabrication toolkit](https://github.com/bennymeg/Fabrication-Toolkit)'s command line, which applies jlcpcb's rotation corrections. there is no way to place an assembled-board order from a script: the [official api](https://api.jlcpcb.com/) needs an approved application and assembly orders through it are unconfirmed. so an agent uploads the files in the browser and fills the cart, and a person checks part placement and pays.
- **not this**: hand-soldering small surface-mount parts.

### [jlccnc](https://jlccnc.com) / [jlc3dp](https://jlc3dp.com)
machined metal, and printing in materials the home printers can't do.
- **reach for it when**: a part is not flat and can't be printed at home.

### [sendcutsend](https://sendcutsend.com)
laser-cut and bent sheet metal.
- **reach for it when**: flat or folded metal parts.
- **not this**: buying a mill or a laser yet.
