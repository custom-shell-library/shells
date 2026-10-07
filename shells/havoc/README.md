# havoc

**Class:** UGV (robotic combat vehicle)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Milrem Robotics / EDGE Group<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Large 8×8 hybrid-electric Robotic Combat Vehicle (RCV) designed to act as a wingman for mechanized infantry units, supporting tanks and infantry fighting vehicles. Delivers superior firepower and real-time intelligence while keeping human soldiers at standoff distance from enemy forces. The HAVOC is a "wingman for mechanized units": it supports IFVs and battle tanks, enhances troop survivability by extending standoff distance, and is designed for easy upgrades and low maintenance.

**Environment** — All-terrain, all-weather, all-climate. Designed for offensive and defensive operations across diverse terrains including deserts, urban areas, mountainous regions, and European climate conditions. Operating temperature range not publicly specified; the hybrid-electric powertrain and lithium-ion batteries are built to work in extreme hot or cold conditions.

**Mission** — Provide a robotic wingman for mechanized formations. Primary roles: direct fire support (30 mm autocannon), anti-UAV defense (Frankenburg missile launchers), reconnaissance and surveillance, logistics support in contested environments, and casualty reduction by extending the standoff distance from enemy forces.

**Operator** — Remote operation with supervised autonomy. Operators can seamlessly integrate various weapons systems or sensor packages without impacting overall performance. The vehicle is equipped with advanced AI-driven navigation allowing it to operate in different terrains and conditions. Even with a turret, "pulling the trigger is the responsibility of a human supervisor."

**Reusability** — Commercial defence platform. Fielded modular UGV with active defence procurement and combat support use. Not a DIY build.

---

## Spec

**Physical** — Dimensions 6.8 × 2.8 × 2.7 m. Weight without payload ~15 tonnes. Curb weight 20 tonnes. Maximum payload weight up to 5 tonnes. Ground clearance 0.44 m. Fording depth 1 m. Vertical step climb 0.6 m. Normal turning radius 10 m (with pivot steering capability allowing dramatically reduced turning radius).

**Kinematic** — 8×8 all-wheel drive with hybrid-electric transmission (Timoney T-9000e). Four axles, each rated for 9,500 kg mass. Each axle has a peak output power of 280 hp. Electric motors operate at 650 V. The electric driveline delivers instantaneous torque for rapid acceleration and pivot steering. The 8-wheel configuration provides superior mobility, stability, and load-bearing capacity.

**Dynamic** — Maximum speed on road 110 km/h. Maximum speed off road 50 km/h. Operational range up to 600 km. Maximum grade 60%. Maximum side slope 40%. Power-to-mass ratio approximately 56 hp/t (17-tonne GVW). The hybrid-electric powertrain enables near-silent movement for stealth missions and prolonged silent watch capabilities.

**Power** — Hybrid-electric powertrain combining a diesel engine with electric motors. Integrated lithium-ion batteries facilitate silent missions and are built to work in extreme hot or cold conditions. Each axle is powered by a Timoney T-9000e electric powertrain rated for 9,500 kg mass, with electric motors operating at 650 V. The diesel engine acts as a range extender, recharging the batteries to extend operational range while allowing near-silent electric-only movement over medium distances.

**Thermal** — Passive cooling via vehicle-level thermal management. The hybrid-electric powertrain reduces thermal signature compared to conventional diesel vehicles, which is critical for stealth operations. No active thermal management details publicly specified.

**Environmental** — STANAG 4569 kinetic energy protection Level 3 (some sources cite Level 4, protecting against 14.5 mm bullets). STANAG 4569 artillery protection Level 3. STANAG 4569 mine protection Level 1. Designed for fording depth of 1 m. The 8×8 configuration and 0.44 m ground clearance provide off-road mobility in challenging terrain.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The vehicle is purchased as a complete system with modular payload integration.

| Component | Notes |
|:---|:---|
| HAVOC 8×8 RCV chassis | ~15 t without payload, 6.8 × 2.8 × 2.7 m |
| Timoney T-9000e hybrid-electric powertrain | Four axles, each 9,500 kg rated, 280 hp peak per axle |
| Diesel engine (range extender) | Recharges batteries for extended range |
| Lithium-ion battery pack | Enables silent movement and silent watch |
| 30 mm autocannon | Main armament, remote-controlled weapon station |
| Frankenburg Technologies missile launchers | Anti-UAV, 2,000 m effective range, 1,500 m ceiling |
| Metravib Defence PILAR V | Shot origin detection, GPS coordinates, threat identification |
| Vegvisir Remote | Mixed Reality-based 360° situational awareness system |
| Autonomy kit | AI-driven navigation, LiDAR, day/night cameras, thermal imagers |
| STANAG 4569 L3 armor | Kinetic energy and artillery protection |

**Structure** — Large 8×8 wheeled armored chassis. The roof has been designed to support any payload up to five tonnes. The vehicle shares common subsystems with Milrem's existing UGV platforms (THeMIS and Tracked RCV) to reduce development costs and streamline maintenance logistics.

**Actuation** — Timoney T-9000e electric powertrain. Four axles, each with a peak output of 280 hp and rated for 9,500 kg. Electric motors operating at 650 V. All-wheel hybrid-electric drive with pivot steering capability.

**Locomotion** — 8×8 wheeled. All-wheel drive. Pivot steering enables dramatically reduced turning radius. Normal turning radius 10 m. Capable of negotiating steep gradients (60%), side slopes (40%), and vertical steps (0.6 m).

**Manipulation** — None. The vehicle is a weapons and sensor platform. The 30 mm autocannon is the primary effector, mounted on a remote-controlled weapon station. Additional effectors include Frankenburg missile launchers for anti-UAV defense.

**Power system** — Hybrid-electric: diesel engine + electric motors + lithium-ion batteries. Each axle powered by a Timoney T-9000e electric powertrain. Electric motors at 650 V. The diesel engine acts as a range extender, providing 600 km total range with silent electric-only operation for medium distances.

**Wiring** — Internal only. Not user-accessible. Payload integration via standardized interfaces on the 5-tonne roof.

**Custom parts** — None. All components are Milrem/EDGE proprietary or certified third-party. Payloads mount on the flat deck and roof within the 5-tonne limit.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and maintenance.

---

## Systems

**Manifest** — Milrem Robotics autonomy ecosystem with SteerAI CoreX AI-powered autonomy kit (used on THeMIS; HAVOC likely uses similar or successor technology).

**Firmware** — Proprietary. The vehicle runs AI-driven navigation software with advanced perception sensors, cameras, and LiDAR. The autonomy kit includes sensors and electro-optical devices positioned across the platform's body, including LiDAR devices, day and night cameras, and thermal imagers.

**Middleware** — Proprietary. No public ROS 2 or open middleware information. The vehicle is networked with both Rheinmetall's soldier system and the Rheinmetall Command and Control Software for THeMIS; HAVOC likely uses Milrem's own command and control ecosystem.

**Perception** — Autonomy kit comprising: (1) LiDAR devices for 3D mapping and obstacle detection, (2) day and night cameras for visual perception, (3) thermal imagers for night operations, (4) Metravib Defence PILAR V for shot origin detection (provides GPS coordinates and identification of threats, good accuracy for determining shot origin, operates during attacks with multiple threat sources including small arms fire, RPGs, and mortars), (5) Vegvisir Remote for Mixed Reality-based 360° situational awareness (low-bandwidth system optimised for remote use, enables fleet observation when linked to Vegvisir Virtual Command Station).

**Control** — AI-driven navigation with advanced autonomy. The vehicle can navigate autonomously in different terrains and conditions. Operators can seamlessly integrate various weapons systems or sensor packages without impacting overall performance. Human-in-the-loop for weapons release: "even if it has a turret, pulling the trigger is the responsibility of a human supervisor."

**Planning** — Autonomous route planning and navigation. The vehicle plans and navigates routes with 2D and 3D LiDAR mapping. Milrem's intelligent functions kit (developed for THeMIS) includes: plan and navigate routes, 2D and 3D LiDAR mapping, and follow-me mode. HAVOC likely uses a more advanced version of this autonomy stack.

**Learning** — None publicly disclosed. The platform uses AI-driven navigation but no learning-based control is mentioned for safety-critical weapons release.

**Teleoperation** — Remote operation with supervised autonomy. The operator supervises the vehicle and authorizes weapons release. Vegvisir Remote provides a Mixed Reality-based 360° situational awareness system that enhances operator decision-making. The low-bandwidth system is optimised for remote use and connects operators in a unified digital hub.

**Safety** — Human-in-the-loop for weapons release. The vehicle is designed to keep human soldiers at standoff distance, enhancing troop survivability by extending standoff distance from enemy forces. STANAG 4569 protection levels provide crew survivability if the vehicle is occupied or operating in proximity to troops.

**Logging** — Mission data, sensor data, and weapons employment logs. Specific logging details not publicly disclosed.

**Networking** — Unified autonomy ecosystem. The vehicle is part of Milrem's unified autonomy ecosystem, sharing common subsystems with THeMIS and Tracked RCV platforms to reduce procurement and maintenance expenses.

**Config files** — Proprietary. No user-accessible config files.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Milrem Robotics autonomy stack. SteerAI CoreX (or successor). Metravib PILAR V. Vegvisir Remote. Frankenburg Technologies missile system. Remote-controlled weapon station software.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Milrem autonomy stack | Proprietary | Milrem | Autonomy/Navigation |
| SteerAI CoreX | Proprietary | SteerAI | Autonomy/AI |
| Metravib PILAR V | Proprietary | Metravib | Sensors/ShotDetection |
| Vegvisir Remote | Proprietary | Vegvisir | Sensors/SituationalAwareness |
| RCWS software | Proprietary | Various | Weapons/RCWS |

---

## Interface

**Emits** — Sensor data: LiDAR point clouds, camera feeds (day/night/thermal), PILAR V threat detection data (GPS coordinates, shot origin), Vegvisir 360° situational awareness feeds. Vehicle telemetry: speed, position, heading, battery state, fuel state, system health.

**Accepts** — Navigation commands (waypoints, routes, follow-me). Weapons authorization (human-in-the-loop). Payload commands. Sensor tasking.

**Serves** — Autonomy services (navigation, obstacle avoidance, route planning). Weapons employment services (with human authorization). Sensor fusion services.

**Executes** — Autonomous navigation to waypoints. Route following. Follow-me mode. 2D and 3D LiDAR mapping. Threat detection and reporting. Weapons employment (with human authorization). Anti-UAV engagement.

**Extensions** — Modular payloads up to 5 tonnes. Weapons stations (up to 30 mm). Multi Canister Launchers. Frankenburg missile launchers. Metravib PILAR V. Vegvisir Remote. Additional sensors and communication systems.

**Frame conventions** — Military grid reference system (MGRS) for position. Vehicle body frame for local navigation. Sensor frames for LiDAR, cameras, and thermal imagers.

**Units** — SI and military standard. Meters, kilometers, kilometers per hour, degrees, grams (warhead), meters (range).

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for LiDAR, cameras, and thermal imagers. Weapons calibration for the 30 mm autocannon. Specific details not publicly disclosed.

**Dynamics** — Proprietary. Vehicle dynamics model for autonomy and navigation. Power-to-mass ratio approximately 56 hp/t. Weight distribution across four axles.

**Sensor transforms** — LiDAR, cameras, and thermal imagers positioned across the platform body. PILAR V positioned for 360° shot detection coverage. Vegvisir positioned for 360° situational awareness.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — Payload integration up to 5 tonnes. Weapons system integration (30 mm autocannon, Frankenburg missiles). Sensor integration (PILAR V, Vegvisir). Autonomy stack integration.

**Field** — Off-road mobility: 60% gradient, 40% side slope, 0.6 m step climb, 1 m fording. Speed: 110 km/h on road, 50 km/h off road. Range: 600 km. Silent watch: electric-only operation for medium distances. Anti-UAV engagement: Frankenburg missile against <150 kg and <200 km/h targets with ≥70% success rate. Shot detection: PILAR V during attacks with multiple threat sources.

**Endurance** — Operational range 600 km. Continuous operation up to 15 hours (from Janes reporting on powerplant capability).

**Environmental** — STANAG 4569 L3 kinetic energy and artillery protection, L1 mine protection. Extreme hot and cold climate operation enabled by lithium-ion batteries.

**Known limitations** — The vehicle weighs 15 tonnes without payload, requiring significant logistical support for transport and deployment. It is a large, heavy platform not suitable for confined urban environments or narrow passages. The 8×8 wheeled configuration, while highly mobile, is not as agile as tracked platforms in extreme terrain. The hybrid-electric powertrain adds complexity and maintenance requirements compared to conventional diesel. The platform is designed for mechanized units and requires integration with existing command and control structures. Human-in-the-loop weapons release means the vehicle cannot engage targets fully autonomously. The 5-tonne payload capacity is substantial but finite; heavier weapon systems or armor packages may exceed it. Nuclear, biological, and chemical (NBC) protection details not publicly disclosed.

---

## Log

**Build history** — HAVOC 8×8 RCV developed by Milrem Robotics and EDGE Group. Unveiled at IDEX 2025 in Abu Dhabi, February 2025. Launched in Europe at DSEI 2025, September 2025. Shares common subsystems with THeMIS and Tracked RCV platforms. Designed as a wingman for mechanized units, supporting IFVs and battle tanks.

**Open issues** — Full autonomy level (human-in-the-loop for weapons). NBC protection details. Export control and ITAR restrictions. Integration with non-Milrem command and control systems. Battery endurance for sustained silent watch operations.

**Changelog** — Version 1.0: initial production configuration. IDEX 2025: first public unveiling. DSEI 2025: European launch.

**Lessons learned** — Shared subsystems with THeMIS and Tracked RCV reduce development costs and streamline maintenance logistics. Hybrid-electric powertrain enables silent movement and silent watch, critical for modern battlefield engagements. Modular 5-tonne payload capacity allows mission-specific configuration without impacting mobility. AI-driven navigation reduces operator workload while keeping humans in the loop for weapons release.

**Cost actual** — Not publicly disclosed. Defence procurement pricing varies by configuration, quantity, and offset agreements.

---

## Status

**Condition** — operational.<br>

**Blockers** — None. Fielded defence product with active procurement.

**Next steps** — Integration with mechanized unit command and control structures. Payload certification for mission-specific weapon systems. Field trials with mechanized formations. Export control and end-user certification. Production scaling with EDGE Group manufacturing.

---

**Note on this Shell:** The HAVOC 8×8 RCV is a distinct class in the library: a large, hybrid-electric, AI-navigated robotic combat vehicle designed for peer and near-peer conflict. Unlike the THeMIS (logistics and support) or Mission Master (multi-mission UGS), the HAVOC is purpose-built as a wingman for mechanized units, carrying a 30 mm autocannon and anti-UAV missiles on a 5-tonne modular payload deck. Its hybrid-electric powertrain enables silent movement and silent watch, reducing acoustic and thermal signatures for stealth operations. The STANAG 4569 protection levels (L3 kinetic/artillery, L1 mine) provide survivability in contested environments. The human-in-the-loop weapons release reflects the current state of military robotics: autonomy for navigation and targeting, human authorization for lethal action. This Shell is the reference for a large robotic combat vehicle with hybrid-electric propulsion, modular payload, and AI-driven navigation, following the architecture demonstrated by the THeMIS, Tracked RCV, and Mission Master family.
