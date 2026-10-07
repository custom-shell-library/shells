# evo-le

**Class:** aerial (VTOL fixed-wing)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** DeltaQuad<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Long-endurance electric fixed-wing VTOL unmanned aerial system for ISTAR (Intelligence, Surveillance, Target Acquisition, and Reconnaissance) missions in remote and contested environments. Combines vertical take-off and landing with fixed-wing cruise efficiency, eliminating the need for runways or launch infrastructure while delivering flight times and ranges that rival much larger platforms. Carries modular EO/IR sensor payloads for persistent surveillance, border protection, and tactical reconnaissance.

**Environment** — Outdoor, open air, day and night operations. IP54 environmental rating. Operating temperature −20 °C to +45 °C. Maximum wind speed for launch and recovery: 12 m/s (design limit). Cruise altitude up to 3,000 m MSL. Not for indoor flight, heavy precipitation, or icing conditions without additional protection.

**Mission** — Persistent surveillance, reconnaissance, border patrol, maritime monitoring, and ISTAR. The Evo-LE is designed for missions where endurance and range are the primary requirements, offering up to eight hours of continuous flight and a maximum range of 480 km depending on payload, mission profile, and operating conditions. Its vertical take-off and landing capability allows deployment from confined areas, vehicles, or ships without runway infrastructure.

**Operator** — Two-person team for deployment. Single operator for flight control via ground control station. The system can be deployed from a vehicle in under 3 minutes per DeltaQuad specifications for the Evo platform family. Control via DeltaQuad's ground control software on a ruggedized laptop or tablet.

**Reusability** — Commercial product. Modular payload bay accepts interchangeable sensor packages. The Evo-LE is a variant of the Evo platform, using the reinforced DeltaQuad Block 3 airframe constructed from advanced composite materials.

---

## Spec

**Physical** — Wingspan 2.69 m. Length 0.75 m. Maximum take-off weight 13 kg. Payload capacity up to 1.5 kg. The airframe is constructed from advanced composite materials (carbon fibre reinforced polymer) for high strength-to-weight ratio. The Evo-LE uses the reinforced DeltaQuad Block 3 airframe, which is also used in the current Evo platform.

**Kinematic** — Hybrid VTOL fixed-wing configuration. Four vertical lift rotors for take-off, hover, and landing. One pusher propeller for efficient forward cruise flight. Fixed wings generate lift during cruise, allowing the lift rotors to shut down. Control surfaces: ailerons, elevator, rudder for fixed-wing flight. Transition between hover and cruise is managed by the autopilot.

**Dynamic** — Maximum flight endurance up to 8 hours. Maximum range up to 480 km. Radio range up to 120 km. Cruise speed: approximately 22 m/s (based on comparable VTOL fixed-wing platforms). Maximum speed: approximately 25–30 m/s. Stall speed: approximately 12 m/s. Rate of climb: 3–5 m/s. Maximum altitude: 3,000 m MSL (operational limit for launch and recovery). Endurance and range figures depend on payload configuration, mission profile, and operating conditions.

**Power** — Electric propulsion. Dual-battery configuration for extended endurance. Battery chemistry: lithium-ion polymer (LiPo) or lithium-ion (Li-ion) for higher energy density. Cruise power draw: approximately 150–250 W depending on speed and payload. Hover power draw: approximately 800–1,200 W. Battery capacity: approximately 1,500–2,000 Wh (estimated based on endurance and power draw). Charging time: 1–2 hours with a high-rate charger.

**Thermal** — −20 °C to +45 °C operating temperature. Passive cooling. Motors and ESCs are mounted in the airflow for convective cooling. The avionics bay is insulated and uses the composite airframe as a heat sink. No active thermal management. Battery temperature is monitored; cold-weather operation may require battery pre-heating for full performance.

**Environmental** — IP54 environmental rating (dust-protected and splash-resistant). Not submersible. Not for flight in icing conditions. The composite airframe is resistant to UV degradation and salt spray for maritime operations.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The Evo-LE is purchased as a complete system with modular payload integration.

| Component | Notes |
|:---|:---|
| DeltaQuad Block 3 airframe | Composite construction, 2.69 m wingspan, 13 kg MTOW |
| Lift motors (4×) | Brushless DC outrunner motors for vertical flight |
| Pusher motor (1×) | Brushless DC outrunner for forward cruise |
| ESCs (5×) | Electronic speed controllers for lift and pusher motors |
| Flight controller | ArduPilot or PX4-based autopilot with VTOL transition logic |
| GNSS receiver | GPS/GLONASS/Galileo/BeiDou with CRPA anti-jamming capability |
| GNSS anti-jamming antenna | Controlled Radiation Pattern Antenna for GPS-denied environments |
| Visual navigation sensor | Optical flow or visual odometry for GPS-denied navigation |
| Airspeed sensor | Pitot-static tube for cruise flight |
| IMU | 9-DOF inertial measurement unit |
| Barometer | Altitude sensing |
| Telemetry radio | 120 km range radio link |
| Dual battery pack | LiPo or Li-ion, estimated 1,500–2,000 Wh total |
| Automatic retractable landing gear | Keeps sensors clear for unobstructed 360° field of view |
| EO/IR sensor payload | NextVision Raptor (stabilized RGB + thermal imaging) |
| Ground control station | Ruggedized laptop or tablet with DeltaQuad GCS software |

**Structure** — Composite airframe (carbon fibre reinforced polymer) with reinforced wing spar and fuselage. The Block 3 airframe is designed for durability and repeated deployment. The wings are removable for transport. The fuselage houses the avionics, batteries, and payload bay. The four lift motors are mounted on booms extending from the fuselage. The pusher motor is mounted at the rear of the fuselage. The automatic retractable landing gear retracts into the fuselage during flight to minimize drag and provide an unobstructed 360° view for the payload sensors.

**Actuation** — Four brushless DC outrunner motors for vertical lift, mounted on booms. One brushless DC outrunner motor for forward cruise, mounted at the rear. Control surfaces (ailerons, elevator, rudder) actuated by digital servos. Motor ESCs are located in the fuselage and booms for cooling.

**Locomotion** — Hybrid VTOL. Vertical take-off and landing using four lift rotors. Transition to forward flight using the pusher motor. Cruise flight using the fixed wings and pusher motor. The lift rotors shut down during cruise to save power. Landing approach transitions back to hover mode for vertical landing.

**Manipulation** — None. Payload is sensor only.

**Power system** — Dual-battery configuration. Battery capacity estimated at 1,500–2,000 Wh based on endurance and power draw. Power distribution board routes battery power to the lift motor ESCs, pusher motor ESC, and avionics. 5V and 12V regulated rails for sensors and payload. All power wiring sized for peak current (approximately 60–80 A at full hover power).

**Wiring** — Internal only. Not user-accessible. Payload integration via standardized connector on the payload bay. The automatic retractable landing gear and gimbal are controlled via the autopilot.

**Custom parts** — None. All components are DeltaQuad proprietary or certified third-party. Payloads mount in the modular payload bay.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The system is designed for rapid deployment by a two-person team.

---

## Systems

**Manifest** — DeltaQuad proprietary software stack with ArduPilot or PX4-based autopilot.

**Firmware** — The flight controller runs a VTOL-capable autopilot firmware. ArduPilot QuadPlane is the reference firmware for this class of platform, supporting both tilt-rotor and separate-lift-motor configurations. The autopilot manages the transition between hover and forward flight, including tilt scheduling (if applicable), airspeed monitoring, and failsafe behavior during transition. The autopilot also manages the automatic retractable landing gear and the gimbal stabilization.

**Middleware** — MAVLink over telemetry radio for command and telemetry. Optional ROS 2 via companion computer for advanced payload control and data processing. The ground control station software provides mission planning, telemetry display, and payload control.

**Perception** — NextVision Raptor EO/IR sensor payload: stabilized RGB and thermal imaging for long-range surveillance and tracking. The automatic retractable landing gear provides an unobstructed 360° field of view for the sensors. For navigation, the Evo-LE can carry anti-jamming CRPA GNSS and visual navigation sensors for GPS-denied situations. The CRPA (Controlled Radiation Pattern Antenna) GNSS system provides resilience against jamming and spoofing. Visual navigation (optical flow or visual odometry) enables continued operation when GNSS is unavailable.

**Control** — The autopilot runs the VTOL transition logic, hover controller, and fixed-wing controller. The operator commands waypoints or direct flight via the ground control station. The gimbal is stabilized independently to keep the sensor pointed at the target regardless of aircraft motion. PID tuning for hover, cruise, and transition phases is performed separately. The Evo-LE's dual-battery configuration provides power redundancy for the avionics and payload.

**Planning** — Autonomous waypoint missions via the ground control station. VTOL take-off, transition to cruise, waypoint navigation, transition to hover, VTOL landing. Real-time terrain following for low-altitude surveillance. Geofencing for safety. Return-to-launch on failsafe. The operator can also command direct flight via joystick or on-screen controls.

**Learning** — None in the base platform. The EO/IR payload may include automated target tracking (a form of classical control, not learning). Optional: onboard AI processing for object detection and classification can be added via a companion computer (e.g., NVIDIA Jetson) running YOLO or similar models. The Quantum Systems Reliant, a comparable platform, uses 2× NVIDIA Jetson Orin for AI processing.

**Teleoperation** — Ground control station (ruggedized laptop or tablet) with DeltaQuad GCS software. The operator commands waypoints or direct flight. Video feed from the EO/IR payload displayed in real time. Telemetry includes attitude, position, airspeed, battery state, and payload status. Radio range up to 120 km.

**Safety** — Autopilot failsafe: return-to-launch on radio link loss, low battery, or geofence breach. VTOL transition failsafe: if transition fails, aircraft returns to hover and lands. GNSS jamming resilience: CRPA antenna and visual navigation provide continued operation in GPS-denied environments. Geofence and altitude limits. Arming checks. Automatic landing gear prevents damage on belly landings. The dual-battery configuration provides power redundancy.

**Logging** — Flight data logged to SD card on the flight controller. Payload data (video, thermal imagery) logged to the ground control station or onboard storage. Data includes attitude, position, airspeed, battery state, motor outputs, and transition state.

**Networking** — Telemetry radio at 2.4 GHz or 5.8 GHz for command and control. Video link for EO/IR payload. Optional 4G/LTE module for beyond-line-of-sight operation. Wi-Fi for payload data download after landing.

**Config files** — Autopilot parameter file (VTOL transition, PID gains, failsafe settings). Mission files (waypoints, geofence, payload commands). Ground control station configuration.

**Launch files** — N/A (firmware-based). Optional ROS 2 launch files for companion computer payload processing.

**Dependencies** — DeltaQuad GCS software. ArduPilot or PX4 firmware. Optional: MAVROS, ROS 2 Jazzy, OpenCV for payload processing, NVIDIA Jetson for AI inference.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ArduPilot QuadPlane | 4.5+ | ardupilot.org | Middleware/Autopilot |
| PX4 | 1.15+ | px4.io | Middleware/Autopilot |
| DeltaQuad GCS | Latest | DeltaQuad | GCS |
| Mission Planner | Latest | ardupilot.org | GCS |
| QGroundControl | Latest | qgroundcontrol.com | GCS |
| MAVROS (optional) | Latest | ROS 2 | Middleware/MAVROS |
| ROS 2 (optional) | Jazzy | ros.org | Middleware/ROS2 |
| OpenCV (optional) | Latest | opencv.org | Perception |
| YOLO (optional) | Latest | github | Perception/AI |

---

## Interface

**Emits** — MAVLink telemetry: attitude, position, airspeed, battery, GPS, flight mode, VTOL transition state. Video feed from EO/IR payload. Payload telemetry (gimbal angles, sensor status).

**Accepts** — RC commands via RC link (optional). MAVLink commands via telemetry radio. Mission upload and download. Payload commands (gimbal pointing, zoom, mode selection).

**Serves** — Arming, calibration, parameter access via MAVLink. Mission upload and download. Payload control services.

**Executes** — VTOL take-off, transition to cruise, waypoint navigation, transition to hover, VTOL landing, return-to-launch. Guided mode for operator-directed flight. Payload pointing and tracking.

**Extensions** — Modular payload bay for interchangeable sensors. Optional SATCOM for beyond-line-of-sight operation. Optional SIGINT or EW payloads (as demonstrated on comparable platforms like the Quantum Systems Reliant).

**Frame conventions** — NED (North-East-Down) for navigation. FRD (Forward-Right-Down) for body. Airspeed in m/s. Altitude in meters MSL or AGL.

**Units** — SI. Meters, meters/second, radians, seconds, kilograms.

---

## Model

**URDF / Xacro** — Not typically used for fixed-wing VTOL. ArduPilot uses its own internal model for simulation.

**SDF** — Used for Gazebo simulation with ArduPilot SITL (Software In The Loop).

**Calibration** — Accelerometer, gyroscope, compass, level horizon, airspeed sensor. ESC calibration. Control surface range calibration. Pitot tube zero calibration. Gimbal calibration. CRPA antenna calibration (if fitted). Visual navigation sensor calibration (if fitted).

**Dynamics** — ArduPilot QuadPlane uses a physics model for simulation. Real-world dynamics identified through flight testing. PID tuning for hover, cruise, and transition phases. Center of gravity measured and adjusted by battery placement. The dual-battery configuration shifts the CG; this is accounted for in the airframe design.

**Sensor transforms** — GNSS antenna on the fuselage. CRPA antenna (if fitted) on the fuselage. Airspeed sensor on the nose. IMU at the flight controller location. EO/IR payload in the belly bay, gimbal-stabilized. Visual navigation sensor (if fitted) on the fuselage.

**Collision geometry** — Simple boxes for simulation.

**Visual geometry** — STL meshes from the composite airframe.

---

## Trials

**Bench** — Motor direction, ESC calibration, control surface direction, airspeed sensor reading, GPS fix, IMU calibration, gimbal function. Pass/fail, measured values, date.

**Integration** — Hover test. Transition test at safe altitude. Cruise test. Waypoint mission test. Return-to-launch test. Failsafe test (radio loss, low battery, geofence). GNSS jamming test (if CRPA fitted). Pass/fail, measured values, date.

**Field** — Endurance test: full battery cruise to verify 8-hour endurance. Range test: maximum distance before failsafe. Surveillance test: fly a pattern and verify EO/IR imagery quality. GPS-denied navigation test (if visual navigation fitted). Pass/fail, measured values, date.

**Endurance** — Continuous cruise until battery cutoff. Expected endurance: up to 8 hours depending on payload and conditions. Motor temperature at end. Battery temperature at end.

**Environmental** — Tested in calm to moderate wind (up to 12 m/s). Not for rain or icing. IP54 rating verified for dust and splash resistance. Operating temperature −20 °C to +45 °C.

**Known limitations** — The 1.5 kg payload capacity limits the size and complexity of sensor packages. Heavy or power-hungry payloads reduce endurance. The 8-hour endurance and 480 km range are maximum figures achievable only with optimal payload, mission profile, and conditions. The electric propulsion system requires battery charging infrastructure in the field, which may limit sustained operations in remote areas. The VTOL transition is the most critical and failure-prone phase; it requires adequate altitude and airspeed. The Evo-LE cannot carry the same sensor suite as a larger Group 3 or Group 4 UAV, but it offers comparable endurance at a fraction of the size and cost.

---

## Log

**Build history** — DeltaQuad Evo-LE launched September 2026 at EUDEX 2026. It is a long-endurance variant of the Evo platform, using the reinforced Block 3 airframe. The Evo-LE was developed in response to demand for longer surveillance coverage across remote and contested areas.

**Open issues** — Payload capacity limitations. Battery charging infrastructure in austere environments. GNSS jamming and spoofing resilience (addressed with CRPA and visual navigation). Export control and ITAR restrictions for certain sensor payloads.

**Changelog** — Evo-LE: initial production configuration. Block 3 airframe: reinforced composite construction for durability. Dual-battery configuration: standard.

**Lessons learned** — The combination of VTOL and fixed-wing flight is the optimal configuration for expeditionary surveillance. Runway independence is critical for operations in remote and contested areas. Electric propulsion reduces acoustic and thermal signatures compared to internal combustion engines. The automatic retractable landing gear provides an unobstructed 360° sensor field of view, which is essential for persistent surveillance. The dual-battery configuration provides both endurance and power redundancy.

**Cost actual** — Not publicly disclosed. DeltaQuad is a commercial manufacturer; pricing is available on request and varies by configuration, payload, and quantity.

---

## Status

**Condition** — operational.

**Blockers** — None. Commercial product available from DeltaQuad.

**Next steps** — Payload selection based on mission profile (EO/IR, SAR, SIGINT). Ground control station setup and operator training. Field trials for endurance and range verification. Integration with higher-level command and control systems. Optional: AI processing module for automated target detection.

---

**Note on this Shell:** The evo-le is a distinct class in the library: a long-endurance electric VTOL fixed-wing UAS designed for ISTAR missions where runway independence and persistence are the primary requirements. Unlike multirotor drones (limited endurance) or large fixed-wing UAVs (require runways), the Evo-LE combines the best of both: vertical take-off and landing from confined areas, with fixed-wing efficiency for 8-hour endurance and 480 km range. Its 1.5 kg payload capacity is sufficient for a stabilized EO/IR sensor for surveillance, and the automatic retractable landing gear provides an unobstructed 360° field of view. The CRPA GNSS and visual navigation options provide resilience against jamming and GPS-denied environments, which is critical for operations in contested areas. This Shell is the reference for a portable, long-endurance, VTOL surveillance drone with modular payloads, electric propulsion, and expeditionary deployment capability.
