# design

where a part or a board is described, before anything is made.

### [build123d](https://build123d.readthedocs.io)
mechanical parts written as python. an agent writes the shape as code, and it exports step and stl.
- **reach for it when**: any printed, cut or machined part.
- **not this**: fusion 360 (closed, cloud, no linux). freecad scripts for new parts.

### [kicad](https://www.kicad.org)
schematics and boards. the files are text and sit in git, and `kicad-cli` runs checks and exports fabrication files without the gui.
- **reach for it when**: any circuit board.
- **watch out**: run erc and drc from `kicad-cli` before every order.
- **not this**: closed or browser-only board tools.

## contextual

- [kistack](https://github.com/BackplaneWorks/kistack): human-written kicad skills for agents (schematic, pcb review, bom, exports, gerber review). `npx skills add American-Embedded/kistack`. the repo has no standard license, so read it before installing.

## watching

- [backplane](https://github.com/BackplaneWorks/Backplane): an agent workspace on top of a kicad fork, with board and schematic viewers and design history. it is a second agent harness, it is weeks old, and its mechanical side uses freecad. look again at the first real board.
