# Triple Threat Simulator

A browser simulator for FRC 1880's HtH V2 robot in the 2026 game, REBUILT.

**Live site:** https://jay-1880.github.io/frc-simulator/

## What it does

- **Full matches:** 20 s auto, then 2:20 teleop with REBUILT hub shifts (timing from pyrebuilt's `game.py`; the auto winner's hub goes inactive first). Red and blue scores, with fuel in an inactive hub not counting.
- **Opponent robots:** an AI scorer that collects fuel and shoots into its hub, and an optional defender that blocks you. Robots are 63 kg rigid bodies: hits bounce and spin, and pushing fights wheel traction.
- **Autos from pyrebuilt:** Shoot, Shoot + Gobbler (left / right) and Gobbler only (left / right), with the same waypoints, headings and state machines as `autonomous/routines.py`, flipped for red and mirrored for left. Pick one in the menu; it runs in the match's auto period, or press P in practice.
- **Practice:** drive the robot on the 2026 field, intake fuel and score it in your alliance's hub. Fuel inside the robot is simulated as soft foam that collides with the real CAD geometry and squashes when pressed.
- **Explore robot:** orbit the CAD, click any part to see its name, show, hide or isolate subsystems, explode the model, and run the intake, hood, indexer, flywheels and swerve modules by hand or with the full shot cycle.
- **Robot behavior follows [frc1880/pyrebuilt](https://github.com/frc1880/pyrebuilt):** the Xbox button layout, field-oriented drive with exponential stick shaping, 4.0 m/s and 0.75 rot/s limits, the ballistics table (hood angle and flywheel rps by distance), the 48° to 70° hood, intake carry and retract positions, and the "chortle" agitation while feeding.

## Settings

Opponents (none, scorer, scorer + defender), drive speed and turn speed are in the menu.

## Controls

| Action | Xbox controller | Keyboard |
|---|---|---|
| Drive / turn | Left stick / right stick | WASD / Q E |
| Intake (deploy + rollers) | LT | F (toggle) |
| Shoot | RT | Space |
| Carry / retract intake | LB / D-pad down | C / Z |
| Outtake | A | X |
| Flywheel on/off | B | B |
| Reset pose | X | R (resets the field) |
| Field / robot-oriented | View | G |
| Camera / auto-aim | Y / left stick click | V / T |
| Slow mode | RB | Shift |
| Run selected auto (practice) | | P |
| Agitate intake while shooting | | H |

## Notes

- Physics is a demo, not calibrated to the real robot.
- The CAD has no bumpers, so the simulator draws them.
- Everything runs in the browser from static files; three.js loads from the jsDelivr CDN.

## Credits

- Field, hub and fuel models: [AdvantageScope](https://github.com/Mechanical-Advantage/AdvantageScope) by Littleton Robotics (FRC 6328), BSD-3-Clause. See `LICENSE-AdvantageScope.txt`.
- Field physics constants follow the open-source [frc-simulator](https://github.com/Codemaster145/frc-simulator).
- 3D rendering: [three.js](https://threejs.org/) (MIT).
