# design

where a part or a board is described, before anything is made.

### [build123d](https://build123d.readthedocs.io)
mechanical parts written as python. an agent writes the shape as code, and it exports step and stl.
- **reach for it when**: any printed, cut or machined part.
- **watch out**: take screws, bearings and gears from [bd_warehouse](https://github.com/gumyr/bd_warehouse) instead of redrawing them.
- **not this**: fusion 360 (closed, cloud, no linux). freecad scripts for new parts.

### [f3d](https://f3d.app)
how an agent sees a part. it renders a step or stl file to a png with no window, so the agent can look at what its code made before anything is printed. `pip install f3d`, then `Engine.create(True)`, `scene.add(file)`, `window.render_to_image().save(png)`.
- **reach for it when**: after every change to a part. render it from a few angles and look.
- **watch out**: the default camera looks straight down. set the camera for side and angled views.

### [kicad](https://www.kicad.org)
schematics and boards. the files are text and sit in git, and [`kicad-cli`](https://docs.kicad.org/master/en/cli/cli.html) runs checks and exports fabrication files without the gui.
- **reach for it when**: any circuit board.
- **watch out**: run erc and drc from `kicad-cli` before every order.

### [pcbparts mcp](https://github.com/Averyy/pcbparts-mcp)
how an agent picks parts for a board jlcpcb will assemble: search by specification, live stock checks, alternatives, and digi-key and mouser lookups. hosted with no key, or self-hosted.
- **watch out**: not yet tried. the offline fallback is the [jlcpcb parts database](https://github.com/CDFER/jlcpcb-parts-database), a daily sqlite file to query directly.

### [easyeda2kicad](https://github.com/uPesy/easyeda2kicad.py)
pulls the schematic symbol, footprint and 3d model for a part into kicad by its lcsc number.
- **watch out**: check imported pin numbers and footprint size against the datasheet. the tool does not guarantee them.
- **not this**: closed or browser-only board tools.

## contextual

- [ocp viewer](https://github.com/bernhard-42/ocp_viewer): a live view of a build123d part in the browser, for a person to orbit and inspect. `pip install ocp_viewer`, then `python -m ocp_viewer` serves it at `http://127.0.0.1:3939`. no vs code needed. not yet tried.
- [tscircuit](https://tscircuit.com): circuit boards written as typescript and react, with a `tsci` command line that previews the board and exports gerbers, placement files and a parts list. try it on the first simple board. kicad stays the default until a tscircuit board has come back from the fab working.
- [kistack](https://github.com/BackplaneWorks/kistack): human-written kicad skills for agents (schematic, pcb review, bom, exports, gerber review). `npx skills add American-Embedded/kistack`. the repo has no standard license, so read it before installing.

## watching

- [backplane](https://github.com/BackplaneWorks/Backplane): an agent workspace on top of a kicad fork, with board and schematic viewers and design history. it is a second agent harness, it is weeks old, and its mechanical side uses freecad. look again at the first real board.
