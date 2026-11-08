# Triple Threat Simulator

A browser simulator for FRC 1880's HtH V2 robot in the 2026 game, REBUILT.

**Live site:** https://jay-1880.github.io/frc-simulator/

## What it does

- **Title screen:** a live exhibition between top teams plays behind the menu, with a cinematic camera, crowd, ribbon boards and video boards over the driver stations. Watch it with one click.
- **Quick match:** build a 3v3 with real 2026 teams from Long Island, Gotham and Daly. Presets (Even match, each event, Rookie scrim, Boss: HighTide) or click any slot to pick a team. Shows each alliance's EPA and your win chance. Drive Triple Threat or spectate. Alliance intro and countdown, pause menu, and a results screen with fuel by robot.
- **Robots scale with EPA:** speed, hopper size, intake rate, fire rate, accuracy and strategy all come from each team's 2026 Statbotics EPA. Elite teams feed fuel into their zone while their hub is off, stage in their own lanes before it switches, and shoot on the move; weak robots miss more, cycle slowly and sometimes break down. A 377-EPA HighTide alliance is not beatable by a 90-EPA robot.
- **Other teams' robots are generic designs** (turret, drum + turret, dual shooter, tall shooter, kit bot), never 1880's CAD. Turrets and drums go to high-EPA teams.
- **Competitions:** the 2026 FIRST Long Island Regional, Gotham Regional or Championship Daly Division with their real team lists. Qualification schedule, match list, rankings by ranking points, serpentine alliance selection (captains pick by EPA; your value comes from how you score in the sim), and a double-elimination bracket with best-of-3 finals. Play your own matches live, watch others (1× to 8×), sim them, or skip to your next match. Progress is saved in your browser.
- **LEDs from pyrebuilt `leds.py`:** green in range, red out of range, flashing near shift changes, pulsing in transition if you lost auto, rainbow when disabled.
- **Matches:** 20 s auto, then 2:20 teleop with REBUILT hub shifts (timing from pyrebuilt's `game.py`; the auto winner's hub goes inactive first). Fuel in an inactive hub doesn't count.
- **Autos from pyrebuilt:** Shoot, Shoot + Gobbler (left / right) and Gobbler only (left / right), with the waypoints, headings and state machines from `autonomous/routines.py`.
- **Practice:** drive on the 2026 field with no clock. Fuel inside the robot is soft foam that collides with the CAD and squashes. Robots are 63 kg rigid bodies with traction-limited pushing; AI robots plan with A*.
- **Garage:** orbit the CAD, click parts, show, hide or isolate subsystems, explode the model, and run the intake, hood, indexer, flywheels and swerve by hand or with the full shot cycle.
- **Robot behavior follows [frc1880/pyrebuilt](https://github.com/frc1880/pyrebuilt):** Xbox layout, field-oriented drive with stick shaping, 4.0 m/s and 0.75 rot/s limits, the hood and flywheel table, intake positions, and the "chortle" agitation.

## Settings

Graphics (Performance, Balanced, Ultra), the live match behind the menus (on/off), drive speed and turn speed. The practice screen sets your alliance and the practice opponents.

## Controls

| Action | Xbox controller | Keyboard |
|---|---|---|
| Drive / turn | Left stick / right stick | WASD / Q E |
| Intake (deploy + rollers) | LT | F (toggle) |
| Shoot | RT | Space |
| Carry / retract intake | LB / D-pad down | C / Z |
| Outtake | A | X |
| Flywheel on/off | B | B |
| Reset pose | X | R (resets the field in practice) |
| Pause / menus | Start / D-pad, A, B | Esc |
| Field / robot-oriented | View | G |
| Camera (driver, 3rd person, 3rd person close, orbit, top, stands) / auto-aim | Y / left stick click | V / T |
| Follow next robot while spectating | | N |
| Slow mode | RB | Shift |
| Run selected auto (practice) | | P |
| Agitate intake while shooting | | H |

## Notes

- Physics is a demo, not calibrated to the real robot.
- The CAD has no bumpers, so the simulator draws them.
- Everything runs in the browser from static files; three.js loads from the jsDelivr CDN.

## Notes on the competition model

- Ranking points approximate REBUILT: win 3, tie 1, +1 at 100 alliance fuel, +1 more at 360, +1 for 50 tower points.
- AI robots score roughly their EPA in fuel per match; instant sims use the same scale so played and simmed matches rank fairly.
- Team EPAs: [Statbotics](https://www.statbotics.io/). Event entries: [FIRST](https://frc-events.firstinspires.org/2026/team/1880).

## Credits

- Field, hub and fuel models: [AdvantageScope](https://github.com/Mechanical-Advantage/AdvantageScope) by Littleton Robotics (FRC 6328), BSD-3-Clause. See `LICENSE-AdvantageScope.txt`.
- Field physics constants follow the open-source [frc-simulator](https://github.com/Codemaster145/frc-simulator).
- 3D rendering: [three.js](https://threejs.org/) (MIT).
