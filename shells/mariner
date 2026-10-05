# mariner

**Class:** aquatic<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Small catamaran unmanned surface vessel (USV) for autonomous bathymetric mapping, water quality monitoring, and environmental survey in lakes, rivers, harbors, and shallow coastal waters. Drives on the surface, carries a sonar and sensor payload, follows waypoint missions autonomously, and relays telemetry to a shore operator via long-range Wi-Fi or cellular link.<br>

**Environment** — Freshwater and saltwater. Lakes, rivers, harbors, estuaries, shallow coastal. Max sea state 2 (wave height up to 0.5 m). Operating temperature 0–40 °C water. Not for open ocean, high currents, or breaking waves.<br>

**Mission** — Autonomous waypoint navigation for bathymetric survey, water quality sampling, environmental monitoring, and search and recovery. Manual teleoperation for close inspection. Return-to-home on link loss. The USV is semi-autonomous: it follows a pre-planned mission but the operator monitors and can override at any time.<br>

**Operator** — Single operator at shore via laptop, tablet, or RC transmitter. Real-time telemetry and video feed via Wi-Fi or cellular. Mission upload via QGroundControl or Mission Planner.<br>

**Reusability** — Fully open-source design. All structural components either 3D-printable or off-the-shelf. Repeatable build. Based on the open-source BlueBoat architecture and the ArduRover autopilot ecosystem.<br>

---

## Spec

**Physical** — Target 15 kg all-up weight (AUW) without batteries. 120 × 93 × 46 cm deployed (L×W×H). 120 × 71 × 24 cm folded. Two rotomolded HDPE hulls (or 3D-printed PA12-CF hulls) secured by a foldable aluminum frame. Draft 15 cm. Payload capacity 15 kg including batteries, sensors, and sampling equipment.<br>

**Kinematic** — Catamaran, differential thrust steering. No rudder. Two thrusters, one per hull, mounted at the stern. Turning by differential thrust between the two thrusters. Max speed 3 m/s (6 knots) with two batteries. Cruise speed 1 m/s for maximum endurance. The catamaran hull form provides high transverse stability and resists roll better than a monohull of equivalent displacement.<br>

**Dynamic** — Payload capacity 15 kg (batteries + sensors + sampling gear). Endurance: 18 hours at 1 m/s with 2 batteries (532 Wh), 62 hours with 8 batteries (2,128 Wh). Range: 65 km with 2 batteries, 220 km with 8 batteries. The M200 thrusters are the propulsion units, each with a weedless propeller design for shallow-water operation.<br>

**Power** — 4S–6S Li-ion (12–26 VDC input range). Baseline: 2× 4S 18 Ah Li-ion batteries (532 Wh total). Expandable to 8 batteries (2,128 Wh). XT90 connectors. 5V 5A regulated output for onboard computer, 5V 3A for sensors. Direct battery voltage available at 60 A for high-power payloads. Fuse board provides battery voltage at 10 A per port.<br>

**Thermal** — 0–40 °C water operating. Passive cooling. Electronics are housed in sealed compartments within the hulls. Thrusters are water-cooled by immersion.<br>

**Environmental** — IP68 for sealed electronics compartments. Hulls are watertight. Not for submergence. Designed for surface operation only.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $3,500–$5,000.<br>

**Structure** — Twin rotomolded HDPE hulls (or 3D-printed PA12-CF hulls). Foldable aluminum frame connects the two hulls and provides mounting for payload and cross members. The frame uses 20×20 mm aluminum extrusion and 3D-printed PA12-CF brackets. Each hull contains a sealed electronics compartment accessible via quick-opening hatches. The catamaran configuration provides a stable platform for sonar and sensor payloads. The design follows the BlueBoat architecture, which is commercially available and has been deployed in research and commercial applications, including integration with MOOS-IVP for multi-agent operations.<br>

**Actuation** — 2× Blue Robotics M200 motors with weedless propellers, one per hull. The M200 is a brushless motor designed for marine environments with a fully-flooded stator, coated magnets, and rotor for corrosion resistance. Each M200 is paired with an ESC (electronic speed controller) inside the hull. The M200 produces over 5 kgf of thrust at 16V, sufficient for the 15 kg catamaran at speeds up to 3 m/s. The weedless propeller design prevents entanglement with vegetation, making the USV suitable for shallow, plant-filled waters.<br>

**Locomotion** — Surface vessel. Catamaran hull with differential thrust steering. No rudder. Turning by varying thrust between the two M200 motors. The BlueBoat's differential thrust steering is well-suited to autonomous waypoint navigation because it allows zero-radius turns and precise heading control.<br>

**Manipulation** — None. Payload is sensor and sampling equipment only. Optional winch for deploying water sampling probes or CTD (conductivity, temperature, depth) sensors.<br>

**Power system** — 4S–6S Li-ion batteries. Baseline 2× 4S 18 Ah (532 Wh). Expandable to 8 batteries. The power system provides battery voltage direct at 60 A for high-power payloads, battery voltage at 10 A through the fuse board, and regulated 5V at 5 A for the onboard computer. All power wiring 12 AWG for main battery leads, 16 AWG for thruster power, 22 AWG for sensor power.<br>

**Wiring** — Thruster power: 16 AWG silicone wire. Ethernet and USB for payload. Serial UART for GPS and telemetry. All wiring routed through watertight cable penetrators. Cable management with service loops and strain relief at all hull penetrations.<br>

**Custom parts** — 3D-printed hull end caps and cable penetrators (PA12-CF or PETG). 3D-printed payload mounting brackets (PETG). 3D-printed antenna mounts (TPU). 3D-printed sensor mounts (PETG). Aluminum frame brackets (6061-T6).<br>

**Fasteners** — M4 and M5 stainless steel (316 marine grade for saltwater). M4 for frame connections. M5 for thruster mounts. All fasteners stainless steel to resist corrosion. Nylon insert lock nuts for vibration-prone connections.<br>

**Tools required** — 3D printer (PA12-CF or PETG capable), hex drivers (2.5 mm, 3 mm, 4 mm), soldering iron, wire crimper, multimeter, marine-grade sealant, torque wrench.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Rotomolded HDPE hull, 1.2 m (or PA12-CF printed) | 2 | Blue Robotics / custom | ~$400 each | Structure/Hull |
| Blue Robotics M200 motor with weedless propeller | 2 | Blue Robotics | ~$250 each | Actuators/BLDC |
| Blue Robotics Basic ESC | 2 | Blue Robotics | ~$25 each | Actuators/ESC |
| Navigator flight controller | 1 | Blue Robotics | ~$200 | Compute/FC |
| Raspberry Pi 4 (2 GB) with BlueOS | 1 | Raspberry Pi | ~$45 | Compute/SBC |
| mRo M10034-M9N GPS | 1 | mRobotics | ~$60 | Sensors/GPS |
| 6-DOF IMU (Navigator onboard) | 1 | Blue Robotics | included | Sensors/IMU |
| Dual 3-DOF compasses (Navigator onboard) | 1 | Blue Robotics | included | Sensors/Compass |
| Barometer (Navigator onboard) | 1 | Blue Robotics | included | Sensors/Barometer |
| 4S 18 Ah Li-ion battery | 2–8 | Various | ~$120 each | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 5V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT90 connector pairs | 4 | Various | ~$5 each | Power/connector |
| Fuse board | 1 | Blue Robotics | ~$40 | Power/distribution |
| 12 AWG, 16 AWG, 22 AWG marine-grade wire | assorted | Various | ~$40 | Wiring |
| Cable penetrators (potting or compression) | 8 | Blue Robotics | ~$10 each | Enclosure |
| Aluminum extrusion frame, 20×20 mm | 2 m | Misumi / 80/20 | ~$25 | Structure |
| 3D-printed frame brackets (PA12-CF or PETG) | 8 | Custom | ~$20 | Custom parts |
| Wi-Fi antenna, 7 dBi omnidirectional | 2 | Various | ~$15 each | Comms/Antenna |
| Ethernet tether (optional for high-bandwidth) | 1 | Various | ~$30 | Comms/Tether |
| 4G/LTE modem (optional for beyond-line-of-sight) | 1 | Various | ~$80 | Comms/Cellular |
| Sonar or depth sounder (optional) | 1 | Various | ~$200–$2,000 | Sensors/Sonar |
| Water quality sensor suite (optional) | 1 set | Atlas Scientific / In-Situ | ~$500–$2,000 | Sensors/WaterQuality |
| M4, M5 stainless steel fasteners | assorted | McMaster | ~$35 | Fasteners |
| PA12-CF filament | ~1 kg | Bambu / Shapeways | ~$100 | Custom parts |
| PETG filament | ~250 g | Prusament | ~$15 | Custom parts |
| TPU filament | ~100 g | Prusament | ~$10 | Custom parts |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — ArduRover 4.6+ on the Navigator flight controller. ArduRover is the ArduPilot firmware variant with dedicated boat support, used on the BlueBoat and other USV platforms. It supports differential thrust steering, waypoint navigation, guided mode, loiter (position hold), and return-to-home. The Navigator runs the real-time control loop at 400 Hz. The Raspberry Pi 4 runs BlueOS, an open-source operating system for marine robotics that manages the flight controller, payload integration, and communication.<br>

**Middleware** — MAVLink over Wi-Fi for command and telemetry. BlueOS provides the bridge between the flight controller and the ground station. Optional ROS 2 via the companion computer for advanced payload control and data processing. The Navigator flight controller communicates with the Raspberry Pi over USB or UART.<br>

**Perception** — mRo M10034-M9N GPS (NEO-M9N chipset, IST8308 magnetometer) for position and heading. The Navigator flight controller provides a 6-axis IMU, dual 3-DOF compasses for redundancy, and a barometer for altitude (useful for altitude hold and wave monitoring). Optional sonar or depth sounder for bathymetric mapping. Optional water quality sensor suite for pH, dissolved oxygen, conductivity, and temperature.<br>

**Control** — ArduRover differential thrust steering. The flight controller sends PWM commands to the two ESCs, which drive the M200 thrusters. Steering is achieved by varying the thrust ratio between the two thrusters. PID controllers for heading, speed, and position. ArduRover's L1 controller (based on Park et al., 2012) provides path following for boats and other platforms. Tuning requires careful adjustment of ATC_STR_RAT_P, ATC_STR_RAT_I, ATC_STR_RAT_D, and ATC_STR_RAT_FF parameters for stable steering without oscillation. The steering feed-forward (ATC_STR_RAT_FF) is particularly important for boats with differential thrust.<br>

**Planning** — Autonomous waypoint missions via QGroundControl or Mission Planner. Mission upload, waypoint navigation, loiter, return-to-home. For bathymetric survey, the operator defines a survey grid and the USV follows it at constant speed, logging sonar data with GPS position. Real-time terrain following is not applicable on water, but constant-speed grid following is standard for bathymetric survey.<br>

**Learning** — None initially. Mission data (GPS track, sonar, sensor readings) logged for post-mission analysis. Optional: use the collected data to train obstacle avoidance or adaptive speed control policies.<br>

**Teleoperation** — Wi-Fi link for telemetry and control up to 250 m with included antennas, >800 m with directional antennas. Manual control via joystick or on-screen controls in QGroundControl. RC transmitter for direct manual override via SBUS receiver input on the Navigator. Optional 4G/LTE modem for beyond-line-of-sight operation.<br>

**Safety** — ArduRover failsafe: return-to-home on Wi-Fi link loss. Low battery failsafe: return-to-home or hold position. Geofence: maximum distance from home and no-go zones. Leak detection: the Navigator has built-in leak detection for 2 probes, with alarm on water ingress. Motor stop on disarm. Arming checks.<br>

**Logging** — ArduRover logs all flight data to SD card on the Navigator. BlueOS logs system data. Sonar and water quality data logged on the companion computer. Data includes GPS position, heading, speed, battery voltage, thruster outputs, and sensor readings.<br>

**Networking** — 802.11a/b/g/n Wi-Fi (2,412–2,462 MHz) via the onboard Raspberry Pi 4. 7 dBi omnidirectional antenna included. Optional 4G/LTE modem for cellular connectivity. Optional satellite modem for remote operations.<br>

**Config files** — ArduRover parameter file (`rover.param`), PID tuning for steering and speed, mission files (`.waypoints`), BlueOS configuration.<br>

**Launch files** — BlueOS provides web-based configuration. Optional ROS 2 launch files for companion computer payload processing.<br>

**Dependencies** — QGroundControl or Mission Planner for mission planning and telemetry. BlueOS for onboard system management. ArduRover 4.6+ firmware. Optional: ROS 2 Jazzy, MAVROS, OpenCV for payload processing.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ArduRover | 4.6+ | ardupilot.org | Middleware/Autopilot |
| BlueOS | Latest | bluerobotics.com | OS/Marine |
| QGroundControl | Latest | qgroundcontrol.com | GCS |
| Mission Planner | Latest | ardupilot.org | GCS |
| MAVROS (optional) | Latest | ROS 2 | Middleware/MAVROS |
| ROS 2 (optional) | Jazzy | ros.org | Middleware/ROS2 |
| OpenCV (optional) | Latest | opencv.org | Perception |
| MOOS-IVP (optional) | Latest | mit.edu | Autonomy/MultiAgent |

---

## Interface

**Emits** — MAVLink telemetry: attitude (roll, pitch, yaw), position (lat/lon/alt), heading, speed, battery voltage, GPS status, thruster outputs, leak status. Sensor data via companion computer (sonar depth, water quality parameters).<br>

**Accepts** — RC commands via SBUS receiver. MAVLink commands via Wi-Fi or cellular. Joystick input via QGroundControl. Mission waypoints and commands.<br>

**Serves** — Arming, calibration, parameter access via MAVLink. Mission upload and download. BlueOS web interface for system management.<br>

**Executes** — Auto mode (waypoint navigation), Guided mode (click-to-navigate), Loiter (position hold), Return-to-Home, Manual mode (direct thruster control).<br>

**Extensions** — Payload-specific MAVLink messages via companion computer. Custom mission commands. Winch control for sampling.<br>

**Frame conventions** — NED (North-East-Down) for navigation. FRD (Forward-Right-Down) for body. Heading in degrees (0 = north, clockwise positive). Speed in m/s. Depth in meters.<br>

**Units** — SI. Meters, meters/second, radians (or degrees for heading), seconds.

---

## Model

**URDF / Xacro** — Not typically used for USV. BlueOS and ArduRover use their own internal models for simulation.<br>

**SDF** — Used for Gazebo simulation with ArduRover SITL (Software In The Loop). The BlueBoat can be simulated on an Ubuntu laptop using SITL and controlled from ROS.<br>

**Calibration** — Accelerometer, gyroscope, compass, level horizon. ESC calibration. Thruster direction verification. GPS antenna position relative to center of gravity. Compass offset if magnetic interference is present.<br>

**Dynamics** — ArduRover uses a physics model for simulation. Real-world dynamics identified through lake or harbor testing. The catamaran hull form has high transverse stability. PID tuning for heading rate, speed, and position. The L1 controller handles path following. Steering parameters require significant reduction from default values for stable boat operation; ATC_STR_RAT_P must often be reduced from 0.2 to 0.05 to stop oscillation in steering on large USVs.<br>

**Sensor transforms** — GPS antenna on a mast above the frame. IMU and compasses on the Navigator flight controller. Optional sonar mounted on the hull bottom or towed behind.<br>

**Collision geometry** — Simple boxes for hulls and frame in simulation.<br>

**Visual geometry** — Hull mesh, frame mesh, thruster meshes.

---

## Trials

**Bench** — Thruster direction, ESC calibration, GPS fix, compass reading, IMU calibration, leak detection test. Pass/fail, measured values, date. Expected: both thrusters respond to PWM commands and spin in correct direction, GPS acquires fix outdoors, compass reads heading within 5° of magnetic north, IMU reports attitude within 2° accuracy.<br>

**Integration** — BlueOS bring-up. Wi-Fi link establishment. MAVLink telemetry to QGroundControl. Arming and disarming. Manual control via joystick. Pass/fail, measured values, date.<br>

**Field** — Manual driving test in calm water. Waypoint navigation test with simple mission (3–5 waypoints). Loiter test (position hold within 2 m radius). Return-to-home test. Failsafe test (turn off Wi-Fi, verify RTH). Endurance test: full battery run at 1 m/s. Pass/fail, measured values, date.<br>

**Endurance** — Continuous operation until battery cutoff at 3.3V per cell. Expected endurance: 18 hours with 2 batteries at 1 m/s. Motor temperature at end (water-cooled, expected <40 °C).<br>

**Environmental** — Tested in freshwater lake and shallow saltwater harbor. Max sea state 2 (0.5 m waves). Not tested in high currents or open ocean.<br>

**Known limitations** — Not for open ocean or high currents. Sonar and water quality sensors are optional and add significant cost. Wi-Fi range limited to 250 m with included antennas; longer range requires directional antennas or cellular modem. Catamaran hulls are susceptible to pitch oscillation in choppy water, which can degrade sonar data quality. Corrosion requires regular maintenance in saltwater environments. No autonomous obstacle avoidance in the base build.

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

**Next steps** — Finalise BOM, order components, assemble hulls and frame, wire electronics. Milestone 1: bench test thrusters and sensors. Milestone 2: manual driving in pool or calm lake. Milestone 3: waypoint navigation with simple mission. Milestone 4: endurance and range test. Milestone 5: payload integration (sonar or water quality sensors). Milestone 6: optional ROS 2 and MOOS-IVP integration for multi-agent operations.
