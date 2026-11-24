# projects

hardware builds talked through on 2026-11-13 and 14, written down so they stop getting lost. none are started. order within each list is the order they were recommended in.

## the big one

**an agent that evolves physical objects overnight.** it designs a part, prints it, the part gets moved to a test rig, a camera measures how it did, and the agent designs the next one. things with no assembly and one number to beat: a glider that flies farthest, a top that spins longest, a legged shape that walks down a ramp with no motor. you wake up to forty generations on the floor and a family tree of designs.
- **watch out**: print time caps a night at maybe 10 to 30 designs. and something has to clear the bed between prints, which is what the arm is for.

## four builds around it

1. **a robot arm that tends the printer.** lifts finished parts off the bed and puts them on the test rig. this became the [reBot arm](robotics.md) plan.
2. **the test bench as an instrument.** a launcher, a ramp, an overhead camera and a scale on one board, behind a small api: run a trial, get back distance, time and weight.
3. **a desktop airflow camera.** a schlieren setup (a curved mirror, a small light, a camera) that makes air visible, so the agent can see the flow around a wing and not only how far it flew.
4. **a wall plotter.** two motors and a pen on strings, drawing the family tree of evolved designs on a wall. least useful, nicest to look at.

1 and 2 together turn the printer into a lab that runs itself.

## with the arm

**making things**
1. assembly: pressing bearings and magnets into printed parts, snapping pieces together
2. heat-set inserts and soldering, with an iron as the tool
3. 3d scanning: the arm moves a camera around an object. with the printer, a copy machine for parts
4. painting and drawing on objects, including curved prints
5. dispensing glue or sealant along a path
6. placing components on circuit boards (harder: 0.1 mm is only enough for larger parts)

**testing and measuring**

7. strength testing: bend printed samples until they break, report which settings are strongest
8. the evolution loop: launch, measure, reset
9. pressing real buttons and touchscreens to test apps and devices

**hands for agents**

10. hardware development with nobody there: press reset, swap an sd card, hold a probe on a test point
11. remote hands for machines: power buttons, cables, usb devices
12. a third hand at the bench that holds a part, a light or a camera

**research**

13. teaching by demonstration, and training on that data
14. building the hand

first three: 1, 3 and 10.
- **not this**: milling or cutting hard materials (not stiff enough), anything over 2.5 kg or past 75 cm of reach.

## on the arm itself

**control**
1. the agent harness: move commands, camera views, a safety envelope it can't leave, a library of reflex routines. everything else depends on it
2. force control: the arm goes soft, can be pushed by hand, stops on contact, presses with a set force
3. hand-eye calibration that re-runs whenever something gets bumped

**the end of the arm**

4. an automatic tool changer: gripper, pen, camera, soldering iron, suction cup
5. your own hand, designed and printed
6. touch: fingertip sensors

**teaching and simulation**

7. a teleoperation rig: a motorless second arm you move while the real one follows
8. a simulation matched to the real arm's friction and slack
9. your own benchmark: agent-written code against learned robot models, on your arm

**extending it**

10. a rail or wheeled base, so one arm reaches the printer, the bench and the rig
11. a second arm
12. redesigned parts, sent back upstream
13. the arm builds its successor

first three: 1, 2 and 4.

the idea underneath all of it: the agent is the brain and the programmer. it doesn't sit in the fast loop, it writes the fast loop as a small control routine that runs on the arm.

## the arm as a camera operator

he hates filming, and an arm doesn't. once it holds a camera it can make the [clips](https://github.com/tetraslam/desk) of physical things.

- **first tool for the tool changer: a printed phone clamp.** the arm carries 2.5 kg, and a phone shoots 4k at 60 frames a second.
- repeatable moves: the same slow orbit every time, so generation 1 and generation 40 can sit side by side from one angle
- timelapses where the camera drifts around a print as it grows
- physical subjects: a game on the real chromatic, the printer swapping toolheads, the arm working
- filming the overnight loop with nobody there
- **watch out**: the two cameras in [robotics](robotics.md) are for the robot to see with. the c920s is 1080p at 30 frames a second, which is usable but under the 60 the clips aim for, and the gemini is a depth camera. they stay as the robot's eyes.

## elsewhere

- a printer item for the bar that only shows while a print is running (an omarchy plugin, once the u1 is set up)
- the make-and-look loop for objects: cad, slice, print, look through the printer's camera, revise
