# hardware

the stack for things you can hold: printed parts, circuit boards, firmware, robots.

two rules pick everything here. one default per layer, and every layer has to be scriptable, so an agent can design, order, build and test without clicking through a gui.

this is a starting list. unlike the web stack, nothing here has shipped in a project of mine yet, so there are no `shipped in` lines. entries get corrected as real builds disagree with them.

| layer | default picks |
| --- | --- |
| [design](design.md) | build123d + bd_warehouse · f3d · kicad · pcbparts mcp · easyeda2kicad |
| [fabricate](fabricate.md) | orcaslicer (snapmaker orca on the u1) · klipper + moonraker · jlcpcb · jlccnc / jlc3dp · sendcutsend |
| [source](source.md) | digi-key · lcsc · mcmaster-carr · adafruit |
| [embedded](embedded.md) | esp32-s3 · xiao esp32-c6 · pico 2 w · rust + embassy · circuitpython · probe-rs · embedded-test · esphome |
| [robotics](robotics.md) | genesis · motorbridge · pinocchio · rerun · gemini 305 wrist camera · c920s overhead |
| [bench](bench.md) | sparkfun logic analyzer on sigrok · later: siglent sds804x hd scope, nordic ppk2 |

[rejected.md](rejected.md) lists what was considered and turned down, with the reason.
