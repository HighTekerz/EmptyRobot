# EmptyRobot

An intentionally empty WPILib (2026, Java) robot program for **bench tests**.

It controls no hardware. Deploy it to a roboRIO so that:

- the Driver Station shows **Robot Code** green and lets you **Enable**, and
- CTRE devices (TalonFX, etc.) that are FRC-locked can be commanded from
  Phoenix Tuner X's Control tab while the Driver Station is enabled.

The Phoenix 6 vendor library is included (`vendordeps/Phoenix6-26.1.1.json`)
so the project matches the robot's library version, but no Phoenix code is
used.

## Use

1. Clone this repo and open it in WPILib VS Code.
2. Set your team number in `.wpilib/wpilib_preferences.json` (currently 3574).
3. Connect to the roboRIO (USB or network) and run **WPILib: Deploy Robot
   Code** (or `./gradlew deploy`).
4. Open the Driver Station and confirm **Communications** and **Robot Code**
   are green.
5. Connect Phoenix Tuner X to the roboRIO. To spin a motor, click
   **DISABLED** in Tuner X so it reads **ENABLED**, then **Enable** in the Driver
   Station. Disable the robot in the Driver Station when you're done.

You only need to redeploy if you (or someone else) have deployed a different
program to the roboRIO since — for example, the full robot code.

## Build

- `./gradlew build` — compile
- `./gradlew deploy` — build and deploy to the roboRIO
