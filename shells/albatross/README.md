# albatross

**Class:** aerial<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Hybrid VTOL fixed-wing drone for long-range inspection, mapping, and surveillance. Takes off vertically like a multirotor, transitions to efficient forward flight like a fixed-wing aircraft, and lands vertically without a runway. Combines the convenience of a quadcopter with the endurance and range of a plane.<br>

**Environment** — Outdoor, open air, calm to moderate wind (up to 10 m/s). Not for indoor flight, dense urban canyons, or heavy precipitation. Operating temperature −10 °C to +45 °C. Not IP-rated for rain unless additional sealing is applied.<br>

**Mission** — Long-range autonomous mapping, pipeline inspection, wildlife survey, search and rescue, and perimeter patrol. Cruise at 15–20 m/s for 2–4 hours, covering 50–100 km per flight. Hover capability for close inspection at waypoints.<br>

**Operator** — Single operator via ground station (Mission Planner or QGroundControl). Fully autonomous waypoint missions with manual override. Optional FPV camera feed for real-time observation.<br>

**Reusability** — Repeatable build from off-the-shelf and 3D-printed components. Production candidate for commercial inspection and mapping.

---

## Spec

**Physical** — Target 6.5 kg all-up weight (AUW) with battery and payload. Wingspan 1,800 mm. Fuselage length 900 mm. Wing area 0.28 m². Aspect ratio 11.6. Airfoil: Clark Y or similar high-lift, low-Reynolds airfoil. Frame material: carbon fiber spar, EPO foam or 3D-printed PA12-CF fuselage and wing ribs, Kevlar-reinforced wing skins.<br>

**Kinematic** — 4 vertical lift rotors for hover and transition. 1 pusher propeller for forward flight. Control surfaces: ailerons, elevator, rudder for fixed-wing flight. Transition mechanism: the lift rotors tilt or the aircraft pitches forward to transition from hover to cruise. Tilt-rotor configuration is the baseline design.<br>

**Dynamic** — Cruise speed 15–20 m/s (54–72 km/h). Stall speed 8 m/s. Max speed 25 m/s. Endurance: 2–4 hours cruise, 20–30 minutes hover. Range: 50–100 km depending on battery and payload. Rate of climb: 5 m/s in hover, 3 m/s in forward flight. Payload capacity 1.5 kg (camera, LiDAR, or mapping sensor).<br>

**Power** — 6S LiPo (22.2V nominal, 16,000 mAh, 355 Wh) or 6S Li-ion (22.2V, 21,000 mAh, 466 Wh). Endurance is significantly better with Li-ion due to higher energy density. XT90 connector. 24V direct to ESCs for lift rotors and pusher motor. 5V 5A buck converter for flight controller and companion computer. 12V 3A buck for camera and payload.<br>

**Thermal** — −10 °C to +45 °C operating. Passive cooling. Motors have aluminum heat sinks. ESCs are mounted in the airflow for cooling.<br>

**Environmental** — Outdoor, open air. Not for rain, snow, or heavy dust without additional sealing. Not for indoor operation or dense urban environments.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $2,200–$3,000.<br>

**Structure** — Carbon fiber main spar running through the wing (10 mm outer diameter, 8 mm inner diameter, 1,000 mm length). 3D-printed PA12-CF wing ribs (12 ribs per wing). EPO foam wing skins for lightweight aerodynamic surface, or 3D-printed PA12-CF shells for durability. Fuselage 3D-printed in PA12-CF with carbon fiber reinforcement at the wing root and tail boom. Tail boom carbon fiber tube (12 mm outer diameter). V-tail or conventional tail configuration. The design follows the VTOL transition architecture used in ArduPilot's QuadPlane framework, which supports both tilt-rotor and separate-lift-motor configurations.<br>

**Actuation** — 4× brushless motors for vertical lift, mounted on tilt mechanisms. Selected motor: T-Motor MN4014 400KV or equivalent, ~180 g each, 400 KV, 6S compatible. Each lift motor paired with a 40A ESC. 1× pusher motor for forward flight: T-Motor AT4120 500KV or equivalent, ~250 g, 500 KV, 6S compatible, paired with a 60A ESC. 4× tilt servos for lift rotor tilt mechanism: Hitec HS-7954SH or equivalent, 24 kg-cm torque, metal gears, high voltage. 3× control surface servos for aileron, elevator, rudder: Hitec HS-5085MG or equivalent, 4.3 kg-cm torque, metal gears.<br>

**Locomotion** — Hybrid VTOL. Four lift rotors for vertical takeoff, hover, and landing. One pusher propeller for efficient forward flight. Fixed wings generate lift during cruise, allowing the lift rotors to shut down and the aircraft to fly as a conventional plane. Transition from hover to cruise: the aircraft pitches forward, lift rotors tilt forward (or shut down), and the pusher motor accelerates the aircraft to cruise speed. Transition from cruise to hover: the aircraft pitches up, lift rotors spin up, and the aircraft decelerates to a hover.<br>

**Manipulation** — None. Payload is sensor only.<br>

**Power system** — 6S Li-ion 21,000 mAh, XT90 connector. 24V direct to lift ESCs and pusher ESC. 5V 5A buck for flight controller (Pixhawk or equivalent). 12V 3A buck for camera and payload. Power distribution board with XT90 input and multiple XT60 outputs for ESCs. All power wiring 12 AWG for main battery leads, 16 AWG for ESC power, 20 AWG for signal.<br>

**Wiring** — Lift motor power: 16 AWG. Pusher motor power: 14 AWG. Signal wires: 26 AWG shielded. CAN bus for flight controller to ESCs (if using CAN ESCs) or PWM for standard ESCs. Telemetry and control link via RFD900x or similar long-range telemetry radio. GPS on a mast above the fuselage. Pitot tube for airspeed measurement.<br>

**Custom parts** — 3D-printed fuselage (PA12-CF). 3D-printed wing ribs (PA12-CF). 3D-printed tilt mechanisms (PA12-CF for structural parts, PETG for brackets). 3D-printed motor mounts (PA12-CF). 3D-printed tail mounts (PETG). 3D-printed payload bay (PETG). Carbon fiber spar and tail boom (cut to length).<br>

**Fasteners** — M3 and M4 stainless steel. M3 for servo mounting and brackets. M4 for motor mounts and structural connections. Nylon insert lock nuts for vibration-prone connections.<br>

**Tools required** — 3D printer (PA12-CF or PETG capable), hex drivers (2 mm, 2.5 mm, 3 mm), soldering iron, wire crimper, multimeter, CA glue for foam repairs, heat gun for heat shrink.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| T-Motor MN4014 400KV (lift motors) | 4 | T-Motor | ~$80 each | Actuators/BLDC |
| T-Motor AT4120 500KV (pusher motor) | 1 | T-Motor | ~$100 | Actuators/BLDC |
| 40A ESC (lift motors) | 4 | Various | ~$25 each | Actuators/ESC |
| 60A ESC (pusher motor) | 1 | Various | ~$35 | Actuators/ESC |
| Hitec HS-7954SH tilt servo | 4 | Hitec | ~$70 each | Actuators/Servo |
| Hitec HS-5085MG control surface servo | 3 | Hitec | ~$40 each | Actuators/Servo |
| Pixhawk 6X or equivalent flight controller | 1 | Holybro | ~$250 | Compute/FC |
| Raspberry Pi 5, 8 GB (companion computer) | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| RFD900x telemetry radio | 2 | RFDesign | ~$100 each | Comms/Telemetry |
| Here3+ GPS with compass | 1 | CubePilot | ~$150 | Sensors/GPS |
| Digital airspeed sensor | 1 | Holybro | ~$50 | Sensors/Airspeed |
| BNO085 IMU (redundant) | 1 | Adafruit | ~$25 | Sensors/IMU |
| 6S Li-ion 21,000 mAh | 1 | Various | ~$150 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 12V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT90 connector pair | 1 | Various | ~$5 | Power/connector |
| Power distribution board | 1 | Holybro | ~$25 | Power/distribution |
| Carbon fiber main spar (10 mm OD, 8 mm ID, 1 m) | 2 | CST The Composites Store | ~$25 each | Structure |
| Carbon fiber tail boom (12 mm OD, 10 mm ID, 500 mm) | 1 | CST | ~$15 | Structure |
| EPO foam wing skins or PA12-CF printed shells | 1 set | Various | ~$60 | Structure |
| 12 AWG, 16 AWG, 20 AWG, 26 AWG silicone wire | assorted | Various | ~$25 | Wiring |
| M3, M4 stainless screws, lock nuts | assorted | McMaster | ~$30 | Fasteners |
| PA12-CF filament | ~1 kg | Bambu / Shapeways | ~$100 | Custom parts |
| PETG filament | ~250 g | Prusament | ~$15 | Custom parts |
| Propellers (lift, 15-inch) | 4 pairs | T-Motor | ~$20/pair | Propulsion |
| Propeller (pusher, 14-inch) | 1 | T-Motor | ~$25 | Propulsion |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — ArduPilot QuadPlane firmware on Pixhawk 6X. QuadPlane is ArduPilot's VTOL framework, supporting both tilt-rotor and separate-lift-motor configurations. It handles the transition logic between hover and forward flight, including tilt scheduling, airspeed monitoring, and failsafe behavior during transition. The companion computer runs Ubuntu 24.04 LTS and ROS 2 Jazzy for advanced payload control and data processing.<br>

**Middleware** — MAVLink over telemetry radio for command and telemetry. Optional ROS 2 via companion computer for payload integration. The companion computer communicates with the flight controller over MAVLink (MAVROS) for high-level commands and telemetry.<br>

**Perception** — Here3+ GPS with compass for position and heading. Digital airspeed sensor for cruise flight (required for safe transition). BNO085 IMU as redundant sensor. Optional camera or LiDAR payload for mapping and inspection. Optional ADS-B receiver for traffic awareness.<br>

**Control** — ArduPilot QuadPlane flight controller. Hover mode: lift rotors provide vertical thrust, aircraft hovers like a multirotor. Forward flight mode: pusher motor provides thrust, wings generate lift, lift rotors shut down. Transition: aircraft pitches forward, airspeed increases, lift rotors tilt or shut down when sufficient airspeed is reached. ArduPilot handles the transition automatically based on airspeed and altitude. PID tuning for hover, cruise, and transition phases separately.<br>

**Planning** — Autonomous waypoint missions via Mission Planner or QGroundControl. VTOL takeoff, transition to cruise, waypoint navigation, transition to hover, VTOL landing. Real-time terrain following for mapping missions. Geofencing for safety. Return-to-launch on failsafe.<br>

**Learning** — None initially. Flight data logged for post-flight analysis and tuning.<br>

**Teleoperation** — Long-range telemetry radio (RFD900x) for command and telemetry up to 40 km line of sight. RC transmitter for manual override via a separate RC link (e.g., ExpressLRS or TBS Crossfire). Ground station laptop running Mission Planner or QGroundControl.<br>

**Safety** — ArduPilot failsafe: return-to-launch on radio loss, low battery, or geofence breach. Transition failsafe: if transition fails, aircraft returns to hover and lands. Airspeed sensor failure: aircraft reverts to GPS ground speed estimation. ADS-B In for traffic awareness (optional). Geofence and altitude limits. Arming checks.<br>

**Logging** — ArduPilot logs all flight data to SD card on flight controller. Companion computer logs payload data. Logs include attitude, position, airspeed, battery, motor outputs, and transition state.<br>

**Networking** — Long-range telemetry radio (RFD900x, 900 MHz) for command and telemetry. Optional 4G/LTE module for beyond-line-of-sight operation. Wi-Fi on companion computer for payload data download after landing.<br>

**Config files** — ArduPilot parameter file (`quadplane.param`), PID tuning for hover and cruise, transition parameters, mission files.<br>

**Launch files** — N/A (firmware-based). Optional ROS 2 launch files for companion computer payload.<br>

**Dependencies** — Mission Planner or QGroundControl. ArduPilot QuadPlane firmware. Optional: MAVROS, ROS 2 Jazzy, OpenCV for payload processing.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ArduPilot QuadPlane | 4.5+ | ardupilot.org | Middleware/Autopilot |
| Mission Planner | Latest | ardupilot.org | GCS |
| QGroundControl | Latest | qgroundcontrol.com | GCS |
| MAVROS (optional) | Latest | ROS 2 | Middleware/MAVROS |
| ROS 2 (optional) | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu (optional) | 24.04 LTS | ubuntu.com | OS/Linux |
| OpenCV (optional) | Latest | opencv.org | Perception |

---

## Interface

**Emits** — MAVLink telemetry: attitude, position, airspeed, battery, GPS, flight mode, transition state. Payload data via companion computer (camera, LiDAR).<br>

**Accepts** — RC commands via RC link. MAVLink commands via telemetry radio.<br>

**Serves** — Arming, calibration, parameter access via MAVLink. Mission upload and download.<br>

**Executes** — VTOL takeoff, transition to cruise, waypoint navigation, transition to hover, VTOL landing, return-to-launch. Guided mode for operator-directed flight.<br>

**Extensions** — Payload-specific MAVLink messages via companion computer. Custom mission commands.<br>

**Frame conventions** — NED (North-East-Down) for navigation. FRD (Forward-Right-Down) for body. Airspeed in m/s. Altitude in meters above mean sea level or above home.<br>

**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — Not typically used for fixed-wing VTOL. ArduPilot uses its own internal model for simulation.<br>

**SDF** — Used for Gazebo simulation with ArduPilot SITL (Software In The Loop).<br>

**Calibration** — Accelerometer, gyroscope, compass, level horizon, airspeed sensor. ESC calibration. Tilt servo range calibration. Control surface range calibration. Pitot tube zero calibration.<br>

**Dynamics** — ArduPilot QuadPlane uses a physics model for simulation. Real-world dynamics identified through flight testing. PID tuning for hover, cruise, and transition phases. Center of gravity measured and adjusted by battery placement.<br>

**Sensor transforms** — GPS on mast above fuselage. Airspeed sensor on nose. IMU at flight controller location. Companion computer in payload bay.<br>

**Collision geometry** — Simple boxes for simulation.<br>

**Visual geometry** — STL meshes from printed parts and foam.

---

## Trials

**Bench** — Motor direction, ESC calibration, servo direction, control surface range, airspeed sensor reading, GPS fix, IMU calibration. Pass/fail, measured values, date.<br>

**Integration** — Hover test. Transition test at safe altitude. Cruise test. Waypoint mission test. Return-to-launch test. Failsafe test (radio loss, low battery, geofence). Pass/fail, measured values, date.<br>

**Field** — Endurance test: full battery cruise. Range test: maximum distance before failsafe. Mapping test: fly a survey grid and check data quality. Payload test: verify camera or LiDAR performance.<br>

**Endurance** — Continuous cruise until battery cutoff at 3.3V per cell. Motor temperature at end. Expected endurance: 2–4 hours with Li-ion battery.<br>

**Environmental** — Tested in calm to moderate wind. Not for rain or heavy dust.<br>

**Known limitations** — Transition is the most critical and failure-prone phase; requires adequate altitude and airspeed. Hover endurance is significantly lower than cruise endurance. Requires larger area for takeoff and landing than a multirotor. Fixed-wing flight requires airspeed, making it unsuitable for confined spaces.

---

## Log

**Build history** — Dated entries, what changed, why.<br>

**Open issues** — Links, priority, status.<br>

**Changelog** — Version bumps, what triggered each.<br>

**Lessons learned** — What would be done differently.<br>

**Cost actual** — Final spend vs. BOM estimate.

---

## Status

**Condition** — draft.<br>

**Blockers** — None. Ready to order parts.<br>

**Next steps** — Finalise BOM, order components, print fuselage and wing ribs, cut carbon fiber spar. Milestone 1: bench test all motors and servos. Milestone 2: hover test in QuadPlane hover mode. Milestone 3: transition test at altitude. Milestone 4: cruise and waypoint mission. Milestone 5: endurance and range test. Milestone 6: payload integration (camera or LiDAR).
