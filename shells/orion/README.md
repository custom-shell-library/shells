# orion

**Class:** aerial (tethered persistent surveillance UAS)  
**Generation:** 1  
**Version:** 2.2  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Elistair  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Tethered hexacopter UAS designed for persistent, uninterrupted ISR (Intelligence, Surveillance, Reconnaissance) and tactical telecommunications relay. Unlike conventional battery-powered drones that must land every 20–40 minutes to swap batteries, the Orion 2.2 TE receives continuous power through a micro-tether connected to a ground station, enabling **50 hours of uninterrupted flight** from a single deployment. It is a “drone mast” — a rapidly deployable 100 m variable-height antenna and sensor platform that can be erected in seconds and left to watch a perimeter, border, or incident scene for days.

**Environment** — Outdoor, all-weather, day and night operations. The drone is powered and controlled through the tether, which provides unlimited energy transmission and secure data transfer, protecting against jamming and interference. Operating temperature range not publicly specified. The tether is 100 m (328 ft), which limits the drone to a fixed overhead position or a small station-keeping envelope. Not for flight beyond the tether length or in high winds that exceed the hexacopter’s station-keeping capability.

**Mission** — Persistent perimeter and border surveillance, incident overwatch, tactical communications relay, event security, and critical infrastructure protection. The Orion 2.2 TE is designed for defense, homeland security, and civil organizations. Its 50-hour endurance means a single system can provide continuous coverage of a 10 km radius for two full days without landing. It can identify, locate, and track targets day and night within that radius, and can also act as an automated variable-height antenna to extend radio networks and improve communication between units.

**Operator** — Single operator via a hardened ground control station (GCS) running Elistair’s proprietary **T-Planner** software. The software is push-button: the operator can automatically take off within minutes of arriving on the scene and focus on the mission rather than piloting. The GCS is a hardened PC designed to resist shocks, water, and dust. The operator can define points of interest in a single click, localize targets, launch automated routines, and determine GPS or MGRS coordinates by clicking on a visual in T-Planner.

**Reusability** — Commercial product. The Orion 2.2 TE is the tactical upgrade of the Orion 2, backed by six years of Orion deployments for defense and security operations worldwide. It is non-ITAR, which expands the addressable market. The 2-in-1 design allows the operator to switch between standard and heavy-lift configurations within seconds, without tools.

---

## Spec

**Physical** — The Orion 2.2 TE is a hexacopter (six rotors) with a robust airframe designed for field deployment. Overall length 1.19 m, diameter 43 cm, wingspan 1.63 m. The system packs into two cases for transport, giving it a low logistical footprint. The airframe is ruggedized and automated, with multiple redundancies. The drone can be configured in **standard** or **heavy-lift** mode by changing the arms; heavy-lift mode features more powerful motors and can carry payloads up to 5 kg.

**Kinematic** — Hexacopter configuration. Six brushless DC motors driving six rotors. The hexacopter layout provides redundancy: if one motor or rotor fails, the aircraft can maintain controlled flight and land safely. The drone is fully automated, with automated take-off, altitude setting, and station-keeping. The operator does not manually pilot the aircraft; they command mission functions via T-Planner.

**Dynamic** — **50 hours of continuous flight** (proved). The drone is powered through the micro-tether, so endurance is limited only by the ground station’s power supply, not by battery capacity. Detection range up to 10 km. Payload capacity: 4 kg at 70 m altitude, or 5 kg at 50 m altitude, for the full 50-hour duration. The drone can also operate as a telecommunications relay, extending radio networks with a 100 m variable-height antenna.

**Power** — Powered and controlled through the **micro-tether**. The tether transmits unlimited electrical power from the ground station (Safe-T 2) to the drone, eliminating battery constraints. The tether also provides secure, high-speed data transfer. The Safe-T 2 ground station is IP54-rated and features an automated winding system for the 100 m micro-tether. Power consumption is not publicly specified, but the ground station draws from a standard power source (vehicle, generator, or mains) and converts it to the voltage required by the drone.

**Thermal** — Passive cooling. The hexacopter’s motors are air-cooled by the rotor wash. The avionics and payload are housed in the airframe with adequate ventilation. No active thermal management is required for the operating envelope. Continuous 50-hour operation is sustained by the unlimited power through the tether; thermal limits are managed by the motor design and the ground station’s power delivery.

**Environmental** — The Orion 2.2 TE is ruggedized and automated, designed to resist changes in weather conditions. The tether is a physical link that protects against jamming and interference, which is critical in contested electronic warfare environments. The ground station is IP54-rated (dust-protected and splash-resistant). The drone is not rated for extreme icing conditions or severe turbulence. Exact operating temperature and wind limits are not publicly specified.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The Orion 2.2 TE is purchased as a complete system with the drone, tether, ground station, and T-Planner software.

| Component | Notes |
|:---|:---|
| Orion 2.2 TE hexacopter | Six rotors, ruggedized airframe, 1.19 m length, 1.63 m wingspan |
| Heavy-lift arms (optional) | Quick-swap arms with more powerful motors for 5 kg payloads |
| Safe-T 2 ground station | 100 m micro-tether with automated winding, IP54 hardened |
| Micro-tether | 100 m (328 ft) power and data tether |
| T-Planner software | Push-button mission planning, image analysis, target localization |
| Ground Control System | Hardened PC, shock/water/dust resistant |
| ISR payload options | Raptor EO/IR sensor, XQT LRF camera (laser range finder up to 3,000 m) |
| Telecommunications payload | Tactical radio relay, 4G cells, third-party payloads via PDK |
| Payload Development Kit (PDK) | Standard interface for third-party payload integration |

**Structure** — Hexacopter airframe with a ruggedized, automated design. The tether connects to the drone through a winding system on the ground station. The drone is designed for rapid deployment and recovery. The heavy-lift configuration is achieved by swapping the standard arms for more powerful arms, which takes seconds and requires no tools. The airframe has multiple redundancies for flight-critical systems.

**Actuation** — Six brushless DC motors driving six rotors. The heavy-lift configuration uses more powerful motors to lift the 5 kg payload. The drone is fully automated: the operator does not manually control the motors. The flight control system manages station-keeping, altitude hold, and automated routines.

**Locomotion** — Rotary-wing flight. The drone is tethered, so it does not fly long distances; it ascends to a commanded altitude (up to 100 m) and holds position. It can adjust altitude within the tether length and station-keep against wind. The 100 m tether allows the drone to act as a variable-height antenna, which is useful for overcoming terrain masking and extending radio line-of-sight.

**Manipulation** — None. The drone is a sensor and communications platform. The payload is the effector: EO/IR cameras, laser range finders, or communications relay equipment.

**Power system** — Powered through the micro-tether from the Safe-T 2 ground station. The ground station converts input power (vehicle, generator, or mains) to the voltage required by the drone and transmits it through the tether. The automated winding system manages the tether during ascent and descent. The IP54 ground station is designed for field operations.

**Wiring** — The micro-tether is the primary wiring, carrying power and data. It is 100 m long and designed for rugged field use. The ground station has an automated winding system to manage the tether. Internal wiring in the drone is not user-accessible. Payload integration uses the Payload Development Kit (PDK), which provides a standard interface for third-party payloads.

**Custom parts** — None. All components are Elistair proprietary or certified third-party. The PDK enables integration of custom payloads, but the airframe, tether, and ground station are factory-built.

**Fasteners** — Proprietary. Not user-serviceable. The system is designed for field deployment and recovery by a small crew; maintenance is at the module level (arms, payload, tether).

**Tools required** — None for assembly (factory-built). The heavy-lift arm swap requires no tools. Standard tools for payload integration and field maintenance.

---

## Systems

**Manifest** — Elistair proprietary software stack with T-Planner mission software and PDK for third-party payload integration.

**Firmware** — The drone runs a proprietary flight control system with automated take-off, altitude setting, station-keeping, and automated routines. The system is designed for push-button operation: the operator arrives on scene, deploys the system, and presses a button to launch. The flight control system handles all aspects of flight, including station-keeping in wind and automatic landing. Multiple redundancies are built into the flight-critical systems.

**Middleware** — Proprietary. The drone communicates with the ground station through the micro-tether, which provides secure, high-speed data transfer. The tether also protects against jamming and interference because the data link is physical, not wireless. T-Planner runs on the hardened GCS and provides the operator interface.

**Perception** — Comprehensive range of ISR sensors:
- **Raptor EO/IR sensor**: Best-in-class infrared sensor with X80 EO zoom, classification and tracking functions, providing actionable intelligence.
- **XQT LRF camera**: AI identification and tracking, with laser range finder option determining exact distance of an object up to 3,000 meters.
- **3 ISR sensors compatible**: The drone can carry multiple sensors simultaneously, depending on the payload configuration.
- **Payload Development Kit (PDK)**: Standard interface for third-party payloads, including tactical communication relays, 4G cells, and other sensors.

The operator can define points of interest in a single click within T-Planner to localize a target and launch automated routines. The software also enables geolocation functions: the operator can determine the GPS or MGRS position of an object of interest by clicking on its visual in T-Planner.

**Control** — Fully automated flight control. The operator does not manually pilot the drone. T-Planner provides push-button mission control: automated take-off, altitude setting, station-keeping, and landing. The operator focuses on the mission (identifying, locating, and tracking targets) rather than flying. The drone can also be configured for telecommunications relay, in which case it acts as a variable-height antenna for radio networks.

**Planning** — T-Planner provides mission planning and execution. The operator can define points of interest, launch automated routines, and localize targets. The software supports geolocation (GPS or MGRS) by clicking on the video feed. For telecommunications missions, the drone’s altitude can be adjusted to optimize radio coverage. The system is designed for rapid deployment: the operator can take off within minutes of arriving on scene.

**Learning** — None publicly disclosed. The system uses automated flight control, image analysis, and target tracking. No learning-based control is mentioned.

**Teleoperation** — Single operator via the hardened GCS running T-Planner. The GCS is a ruggedized PC designed to resist shocks, water, and dust. The operator interacts with T-Planner through a graphical interface, defining points of interest and launching automated routines. The drone is not manually piloted; the operator commands mission functions.

**Safety** — Multiple redundancies in flight-critical systems. The tether protects against jamming and interference, which is a safety and security advantage in contested environments. The hexacopter configuration provides motor redundancy: if one motor fails, the aircraft can still land safely. The automated flight control system reduces operator workload and the risk of human error. The ground station is IP54-rated for field operations.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The T-Planner software enables intelligent image analysis and simplified payload control. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — The micro-tether provides secure, high-speed data transfer between the drone and the ground station. The tether also carries power. For telecommunications relay missions, the drone can carry radio relays, 4G cells, or other communications payloads via the PDK. The drone acts as an automated variable-height antenna, extending radio networks and improving communication between units.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through T-Planner.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — Elistair T-Planner software. Safe-T 2 ground station. Payload-specific software (Raptor EO/IR, XQT LRF, third-party payloads via PDK).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| T-Planner | Proprietary | Elistair | Mission/Mission Planning |
| Flight control | Proprietary | Elistair | Control/Flight |
| Raptor EO/IR software | Proprietary | Various | Sensors/EOIR |
| XQT LRF software | Proprietary | Various | Sensors/LRF |
| PDK integration software | Proprietary | Elistair | Payload/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, tether status, system health. Sensor data: EO/IR imagery, LRF distance measurements, target tracks. Communications relay signals (if configured).

**Accepts** — Mission commands (take-off, altitude, land, automated routines). Payload tasking commands. Points of interest and geolocation requests. Telecommunications relay configuration.

**Serves** — Persistent ISR services. Target identification, location, and tracking. Geolocation (GPS/MGRS). Telecommunications relay services.

**Executes** — Automated take-off, altitude hold, station-keeping, landing. ISR missions (perimeter surveillance, border monitoring, incident overwatch). Target tracking. Communications relay. Geolocation.

**Extensions** — Payload Development Kit (PDK) for third-party payloads. Heavy-lift configuration (5 kg). Raptor EO/IR, XQT LRF, tactical radio relay, 4G cells. Multiple ISR sensors compatible.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). MGRS for military grid reference. NED for navigation. FRD for body. Airspeed not applicable (tethered, station-keeping).

**Units** — SI and military standard. Metres, feet, kilometres, kilograms, degrees, metres per second.

---

## Model

**URDF / Xacro** — Not applicable (proprietary commercial platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR and LRF payloads. Tether tension and winding system calibration.

**Dynamics** — Proprietary. The hexacopter’s aerodynamic model is used for station-keeping and wind rejection. The tether introduces a physical constraint and a tension force that the flight control system must account for. The heavy-lift configuration changes the mass and inertia of the aircraft, requiring different control gains.

**Sensor transforms** — EO/IR and LRF sensors mounted in the payload bay. The tether attach point is at the centre of the drone.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motors, tether, ground station, and payloads.

**Integration** — Payload integration via PDK. Tether and ground station integration. T-Planner software verification. Heavy-lift configuration verification.

**Field** — 50-hour continuous flight endurance (proved). Deployment from difficult-to-access areas. Perimeter and border surveillance missions. Target identification, location, and tracking day and night within 10 km radius. Telecommunications relay missions. Six years of Orion deployments for defense and security operations worldwide.

**Endurance** — 50 hours continuous flight (proved). Powered through the tether, so endurance is limited only by the ground station’s power supply.

**Environmental** — Ruggedized and automated, designed to resist changes in weather conditions. Not for extreme icing or severe turbulence. IP54 ground station.

**Known limitations** — The Orion 2.2 TE is tethered, so it cannot fly beyond the 100 m tether length. It is a persistent surveillance platform, not a wide-area search platform. The 10 km detection range is impressive for a tethered drone but limited compared to larger MALE/HALE drones. The 5 kg payload capacity is sufficient for EO/IR and LRF sensors, but not for large radar systems. The system requires a ground station and a power source (vehicle, generator, or mains), which adds logistics footprint compared to battery-powered drones. It is not a stealth platform; it is a visible, tethered aircraft. The tether is a physical link that can be cut or damaged in contested environments, though it also protects against jamming.

---

## Log

**Build history** — Orion 2 developed by Elistair, launched November 2020. Orion 2.2 TE is the tactical upgrade, backed by six years of Orion deployments worldwide. Deployed by allied forces and public security units in more than 70 countries since 2014. Non-ITAR. The Orion 2.2 TE is designed for defense, homeland security, and civil organizations.

**Open issues** — Expansion of payload options via PDK. Integration with emerging tactical communication systems. Operation in extreme weather. Counter-UAS threats against tethered drones. Regulatory approval for tethered UAS operations in different countries.

**Changelog** — Orion 2: launched 2020, 24-hour endurance, 2 kg payload, 100 m tether. Orion 2.2 TE: tactical upgrade, 50-hour endurance, 5 kg payload (heavy-lift), ruggedized and automated, T-Planner software, PDK for third-party payloads.

**Lessons learned** — The tethered drone concept eliminates the endurance limitation of battery-powered drones. Continuous 50-hour flight from a single deployment is a game-changer for persistent surveillance. The tether also provides a secure, jam-resistant data link, which is critical in contested electronic warfare environments. The 2-in-1 design (standard/heavy-lift) provides flexibility without the need for two separate aircraft. The push-button T-Planner software reduces operator workload and training requirements, allowing security teams to respond rapidly without continuous manual control.

**Cost actual** — Not publicly disclosed. Elistair is a commercial manufacturer; pricing is available on request and varies by configuration, payload, and quantity.

---

## Status

**Condition** — operational. Deployed by allied forces and public security units in more than 70 countries.

**Blockers** — None. Commercial product with active deployments.

**Next steps** — Expansion of payload options via PDK. Integration with emerging tactical communication systems. Continued deployment for perimeter security, border surveillance, and critical infrastructure protection. Development of successor systems with longer tethers or higher payload capacity.

---

**Note on this Shell:** The orion is a distinct class in the library: a tethered persistent surveillance UAS that achieves 50-hour endurance by receiving continuous power through a micro-tether. Unlike battery-powered drones (Hummingbird, Evo-LE, etc.) that must land every 20–40 minutes, or large MALE/HALE drones (SeaGuardian, Zephyr) that operate at high altitude over vast areas, the Orion provides continuous, persistent overwatch of a specific location — a perimeter, border crossing, incident scene, or critical infrastructure site — from a 100 m altitude. Its tether also provides a jam-resistant data link, which is a significant advantage in electronic warfare environments. The 10 km detection range and comprehensive EO/IR sensor suite enable target identification, location, and tracking day and night. The 5 kg heavy-lift payload capacity supports multiple ISR sensors or a tactical communications relay. With six years of deployments in more than 70 countries and a non-ITAR designation, the Orion 2.2 TE is the reference for a tethered, persistent surveillance and telecommunications relay UAS.

**Reference: Counter-UAS interceptor.** For the opposing side of the drone threat, the Fortem DroneHunter 5.0 is a comparable “aerial robotics” platform worth noting. It is a fully autonomous airborne counter-UAS interceptor that uses onboard radar (TrueView, 500 m range) and a high-powered net gun (80 mph launch, 25 ft effective range, 8 ft net radius) to capture hostile drones and carry them away by tether or parachute. The fifth-generation DroneHunter 5.0 features dual onboard cameras, enhanced computing for autonomous engagement of multiple targets, and an optional four-net-gun configuration for counter-swarm missions. It integrates with the SkyDome command-and-control system, which can coordinate up to five interceptors against five simultaneous threats. The DroneHunter is a counter-UAS effector, not a surveillance platform, but it completes the picture of modern aerial robotics: persistent surveillance (Orion), long-endurance ISR (Evo-LE, Raybird), strategic ISR (SeaGuardian, Zephyr), and counter-UAS interception (DroneHunter).
