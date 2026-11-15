# hardware

the stack for things you can hold: printed parts, circuit boards, firmware, robots.

two rules pick everything here. one default per layer, and every layer has to be scriptable, so an agent can design, order, build and test without clicking through a gui.

this is a starting list. unlike the web stack, nothing here has shipped in a project of mine yet, so there are no `shipped in` lines. entries get corrected as real builds disagree with them.

| layer | default picks |
| --- | --- |
| [design](design.md) | build123d + bd_warehouse · kicad |
| [fabricate](fabricate.md) | orcaslicer · klipper + moonraker · jlcpcb · jlccnc / jlc3dp · sendcutsend |
| [source](source.md) | digi-key · lcsc · mcmaster-carr · adafruit |
| [embedded](embedded.md) | esp32-s3 · xiao esp32-c6 · pico 2 w · rust + embassy · probe-rs · wokwi cli · esphome |
| [robotics](robotics.md) | raspberry pi 5 · genesis · motorbridge · pinocchio · rerun |
| [bench](bench.md) | sigrok logic analyzer · glasgow · scpi power supply and scope |
