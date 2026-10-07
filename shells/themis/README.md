# themis

**Class:** UGV (unmanned ground vehicle)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Milrem Robotics<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Modular, tracked hybrid-electric unmanned ground vehicle for combat support, intelligence, surveillance, reconnaissance (ISR), logistics, casualty evacuation (CASEVAC), and ordnance disposal. The THeMIS is a cost-effective, advanced multi-role defence platform designed to support troops in high-threat environments, reducing risks to human lives by entering situations before human forces are exposed. It is the first fully modular hybrid robotics combat vehicle in the world that can be equipped with various payloads like large and small caliber weapons and utilized as an ISR platform. Acquired by 20 nations, including 8 NATO members (Estonia, France, Germany, the Netherlands, Norway, Spain, the UK, and the US), and operationally proven in Ukraine and during the anti-insurgency operation Barkhane in Mali.

**Environment** — Designed to support missions in severe climate conditions, withstanding the extremes of both desert and Arctic environments. Operates in all-terrain, all-weather conditions including ice, snow, sub-zero temperatures, sandy, rocky, and mountainous topography. The THeMIS can ford water obstacles up to 60 cm deep and negotiate 60% slopes. Air transportable according to STANAG 3542, with helicopter under-slung and internal airlift capability.

**Mission** — Primary roles: (1) **Combat** — provide commanders the ability to enter high-threat situations to identify and engage threats prior to human intervention, enhancing the effectiveness of manned assets by creating momentum that human troops can leverage with fewer casualties. (2) **Logistics** — transport supplies and equipment to hard-to-reach locations. (3) **ISR** — reconnaissance and surveillance with modular sensor payloads. (4) **CASEVAC** — casualty evacuation from contested environments. (5) **C-UAS** — counter-aerial threats with modular sensors and effectors including radars, EO/IR systems, electronic warfare payloads, and weapon stations.

**Operator** — Remote operation with supervised autonomy. The vehicle is controlled through a variety of teleoperation options, with the most multifunctional being a smart tablet developed by Rheinmetall that allows the operator to control any Mission Master platform and payload through a single interface. Line-of-sight control range up to 1.5 km. The THeMIS's open architecture enables easy configuration changes and rapid integration of third-party payloads.

**Reusability** — Commercial defence platform. Fielded modular UGV with active procurement across 20 nations. Not a DIY build. The THeMIS is designed for high-volume production, with Milrem Robotics and partners delivering over 150 units to Ukraine alone.

---

## Spec

**Physical** — Dimensions 2.47 × 2.04 × 1.17 m (length × width × height). Curb weight 1,630 kg. Rated payload weight 750 kg, maximum payload weight 1,200 kg. Ground clearance up to 60 cm. Fording depth 60 cm. Maximum grade 60% (31°). Maximum side slope 30%. Gap crossing 90 cm. Turning radius 0 m (pivot steering capability). Pull force 15,000 N. Towing speed up to 80 km/h.

**Kinematic** — Tracked configuration. Rubber tracks with high ground clearance for terrain adaptability. The tracked design provides superior off-road mobility compared to wheeled platforms of equivalent weight, with the ability to pivot-steer in place (turning radius 0 m). The track configuration distributes weight over a larger ground contact area than wheels, reducing ground pressure and improving traction on soft terrain. The THeMIS can climb over obstacles up to 90 cm (gap crossing) and negotiate vertical steps.

**Dynamic** — Maximum speed 20 km/h. Run time hybrid (diesel + electric) up to 15 hours. Run time electric (battery only) up to 1.5 hours. Maximum speed without load 22 km/h, with full load 14 km/h. Payload capacity of 750 kg is the rated continuous payload; 1,200 kg is the maximum payload achievable. The hybrid powertrain enables near-silent movement in electric-only mode for stealth missions, and the diesel engine extends operational range to 15 hours when using both power sources.

**Power** — Hybrid diesel-electric powertrain. Diesel engine coupled to an electric generator, with lithium-ion battery pack for silent operation and silent watch. The diesel engine provides extended range (up to 15 hours hybrid), while the battery pack enables up to 1.5 hours of silent electric-only operation. The THeMIS can also serve as a mobile power source, providing 3 kW at 28 Vdc with a peak of 125 A. This enables the platform to power external systems, charge batteries for other equipment, or support dismounted soldier systems. Battery pack options include lead-acid and lithium-ion, with the specific chemistry selected based on mission requirements.

**Thermal** — Passive cooling via vehicle-level thermal management. The hybrid-electric powertrain reduces thermal signature compared to conventional diesel vehicles, which is critical for stealth operations. In electric-only mode, the THeMIS produces minimal acoustic and thermal signatures. The diesel engine is liquid-cooled. The lithium-ion batteries are managed with thermal controls to operate in extreme hot and cold conditions. No active thermal management details are publicly specified.

**Environmental** — Armoured up to STANAG 4569 Level 3. This provides protection against 7.62×51 mm armor-piercing rounds, anti-tank mines, and 155 mm high-explosive artillery shell fragments at 60 m. The vehicle is designed for air transportability according to STANAG 3542, with both internal airlift and helicopter under-slung capability. IP radio 2.4 GHz MIMO Mesh, 4 W, AES256 encryption, frequency hopping supported.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The vehicle is purchased as a complete system with modular payload integration.

| Component | Notes |
|:---|:---|
| THeMIS tracked chassis | 1,630 kg curb weight, 2.47 × 2.04 × 1.17 m, STANAG 4569 L3 armored |
| Hybrid diesel-electric powertrain | Diesel engine + electric generator + Li-ion battery pack |
| Rubber tracks | High-mobility tracked configuration with 60 cm ground clearance |
| Lithium-ion battery pack | Up to 1.5 h silent electric-only operation, 3 kW 28 Vdc output |
| Payload interface | Modular, open architecture, 750 kg rated / 1,200 kg max payload |
| Autonomy kit | LiDARs, cameras (1080p), GNSS, IMU, velocity radar |
| Smart tablet controller | Single interface for platform and payload control |
| Remote weapon station (optional) | Various options: 7.62 mm, 12.7 mm, 40 mm GMG, 30 mm autocannon, ATGM |
| C-UAS payload (optional) | Radars, EO/IR, EW payloads, weapon stations |
| Cargo module | Flat-deck or containerized payload for logistics |
| CASEVAC module | Stretcher and medical equipment for casualty evacuation |

**Structure** — Tracked chassis with rubber tracks and a modular payload deck. The open architecture enables rapid reconfiguration from transport to strike, from CASEVAC to ordnance disposal, or to support intelligence operations. The platform is designed to accept modular payloads that are preconfigured on sturdy plates, ready to be bolted and plugged into the base platform within minutes. The vehicle shares common subsystems with other Milrem platforms to reduce development costs and streamline maintenance logistics.

**Actuation** — Hybrid diesel-electric. Diesel engine drives an electric generator, which powers electric motors driving the tracks. The battery pack buffers peak power demands and enables silent electric-only operation. The exact motor and engine specifications are not publicly disclosed, but the hybrid system delivers sufficient torque for 60% grade climbing and 15,000 N pull force.

**Locomotion** — Tracked. Rubber tracks with high ground clearance (60 cm). Pivot steering (turning radius 0 m). Maximum speed 20 km/h. Capable of negotiating 60% gradients (31°), 30% side slopes, 90 cm gap crossing, and 60 cm fording depth.

**Manipulation** — None. The vehicle is a payload and weapons platform. The optional remote weapon station provides the effector capability: various weapons including light or heavy machine guns, 40 mm grenade launchers, 30 mm autocannons, and anti-tank guided missiles can be integrated.

**Power system** — Hybrid diesel-electric with lithium-ion battery pack. Diesel engine + electric generator for extended range (up to 15 hours hybrid). Battery pack for silent electric-only operation (up to 1.5 hours). The THeMIS can also provide 3 kW at 28 Vdc with a peak of 125 A as a mobile power source for external systems.

**Wiring** — Internal only. Not user-accessible. Payload integration via standardized interfaces on the modular payload deck. The open architecture enables rapid integration of third-party payloads.

**Custom parts** — None. All components are Milrem Robotics proprietary or certified third-party. Payloads mount on the modular payload deck within the 750 kg rated / 1,200 kg maximum payload limit.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and maintenance. The modular payload system allows rapid payload changes with basic tools.

---

## Systems

**Manifest** — Milrem Robotics autonomy ecosystem. The THeMIS uses intelligent functions and AI for high-tech performance. The vehicle can be equipped with the SteerAI CoreX AI-powered autonomy kit, which enables autonomous navigation using advanced perception sensors, cameras, and LiDAR. The CoreX system converts existing fleets into autonomous systems.

**Firmware** — Proprietary. The vehicle runs AI-driven navigation software with perception sensors, cameras, and LiDAR. The autonomy kit includes LiDARs, day and night cameras, and thermal imagers. The THeMIS was instrumented with three cameras, lidar, GNSS, an IMU, velocity radar, and a common time server mounted on a shared front sensor frame in research configurations.

**Middleware** — Proprietary. No public ROS 2 or open middleware information. The vehicle is networked with both Rheinmetall's soldier system and the Rheinmetall Command and Control Software for certain configurations, and is fully compatible with NATO-standard battle management systems. The THeMIS supports an IP radio 2.4 GHz MIMO Mesh, 4 W, with AES256 encryption and frequency hopping.

**Perception** — Autonomy kit comprising: (1) LiDARs for 3D mapping and obstacle detection, (2) cameras (1080p) for visual perception, (3) day/night/thermal imagers for night operations, (4) GNSS for global positioning, (5) IMU for orientation and motion estimation, (6) velocity radar for ground speed measurement. The research configuration mounted these sensors on a shared front sensor frame with a common time server for sensor synchronization. For C-UAS missions, the THeMIS can integrate radars, EO/IR systems, and electronic warfare payloads to detect and track aerial threats.

**Control** — AI-driven navigation with advanced autonomy. The THeMIS can navigate autonomously in different terrains and conditions, with intelligent functions for route planning, 2D and 3D LiDAR mapping, and follow-me mode. The operator can monitor camera feeds or direct a weapon station, then quickly program the platform to navigate itself autonomously to a desired location, all from the same device. The vehicle has a line-of-sight control range of up to 1.5 km.

**Planning** — Autonomous route planning and navigation. The THeMIS plans and navigates routes with 2D and 3D LiDAR mapping. Follow-me mode enables the vehicle to autonomously follow dismounted troops or a lead vehicle. The open architecture allows integration with higher-level command and control systems for mission planning.

**Learning** — None publicly disclosed. The platform uses AI-driven navigation but no learning-based control is mentioned for safety-critical functions. The SteerAI CoreX kit uses AI for perception and navigation but no online learning is described.

**Teleoperation** — Remote operation with supervised autonomy. The vehicle is controlled through a variety of teleoperation options, with the most multifunctional being a smart tablet that allows the operator to control any Mission Master platform and payload through a single interface. The operator can monitor camera feeds, direct a weapon station, and program navigation from the same device. For weapon release, human-in-the-loop authorization is required. The THeMIS has been demonstrated with BVLOS (beyond line of sight) combat capability in live-fire exercises.

**Safety** — Human-in-the-loop for weapons release. The vehicle is designed to reduce risks to human lives by entering high-threat situations before human forces are exposed. STANAG 4569 Level 3 armour provides crew survivability if the vehicle is operating in proximity to troops. The hybrid powertrain enables silent movement and silent watch, reducing the risk of detection. Emergency stop capability via the operator control interface.

**Logging** — Mission data, sensor data, and weapons employment logs. Specific logging details are not publicly disclosed. The research configuration includes a common time server for sensor data synchronization, which is essential for data logging and post-mission analysis.

**Networking** — IP radio 2.4 GHz MIMO Mesh, 4 W, AES256 encryption, frequency hopping supported. The vehicle is fully compatible with NATO-standard battle management systems and is networked with Rheinmetall's soldier system and Command and Control Software. Line-of-sight control range up to 1.5 km.

**Config files** — Proprietary. No user-accessible config files.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Milrem Robotics autonomy stack. SteerAI CoreX (optional). Rheinmetall Command and Control Software. Various weapon station software (EOS R400, BURIA RWS, ADDER DM RWS, etc.).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Milrem autonomy stack | Proprietary | Milrem | Autonomy/Navigation |
| SteerAI CoreX | Proprietary | SteerAI | Autonomy/AI |
| Rheinmetall C2 | Proprietary | Rheinmetall | Command/Control |
| Weapon station software | Proprietary | Various | Weapons/RCWS |
| Battle management system | NATO-standard | Various | Command/Control |

---

## Interface

**Emits** — Sensor data: LiDAR point clouds, camera feeds (day/night/thermal), GNSS position, IMU data, velocity radar data. Vehicle telemetry: speed, heading, battery state, fuel state, system health, payload status.

**Accepts** — Navigation commands (waypoints, routes, follow-me). Weapons authorization (human-in-the-loop). Payload commands. Sensor tasking. Teleoperation commands via smart tablet.

**Serves** — Autonomy services (navigation, obstacle avoidance, route planning). Payload services (weapons employment, sensor tasking). Power services (3 kW 28 Vdc output for external systems).

**Executes** — Autonomous navigation to waypoints. Route following. Follow-me mode. 2D and 3D LiDAR mapping. Payload deployment. Weapon station control (with human authorization). CASEVAC operations. Cargo transport.

**Extensions** — Modular payloads up to 1,200 kg. Various weapon stations: 7.62 mm, 12.7 mm, 40 mm GMG, 30 mm autocannon, ATGM. C-UAS payloads: radars, EO/IR, EW, weapon stations. ISR sensors. CBRN detection. Communication relay. Medical evacuation module. Cargo module.

**Frame conventions** — Military grid reference system (MGRS) for position. Vehicle body frame for local navigation. Sensor frames for LiDAR, cameras, and thermal imagers.

**Units** — SI and military standard. Meters, kilometers, kilometers per hour, degrees, kilograms, Newtons.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for LiDAR, cameras, thermal imagers, GNSS, IMU, and velocity radar. The research configuration uses a common time server for sensor synchronization. Specific calibration procedures are not publicly disclosed.

**Dynamics** — Proprietary. Vehicle dynamics model for autonomy and navigation. Weight 1,630 kg curb weight. Pull force 15,000 N. Maximum grade 60% (31°). Maximum side slope 30%. Ground clearance up to 60 cm. Gap crossing 90 cm. Fording depth 60 cm.

**Sensor transforms** — LiDARs, cameras, and thermal imagers positioned across the platform body. GNSS, IMU, and velocity radar for navigation. Common time server for sensor synchronization.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — Payload integration up to 1,200 kg. Weapon station integration (7.62 mm, 12.7 mm, 40 mm GMG, 30 mm autocannon, ATGM). Sensor integration (LiDAR, cameras, thermal, GNSS, IMU, velocity radar). Autonomy kit integration (SteerAI CoreX). C-UAS payload integration. CASEVAC module integration.

**Field** — Off-road mobility: 60% grade, 30% side slope, 90 cm gap crossing, 60 cm fording. Speed: 20 km/h. Range: 15 hours hybrid, 1.5 hours electric. Silent watch: electric-only operation for up to 1.5 hours. Pull force: 15,000 N. Towing speed: up to 80 km/h. BVLOS combat demonstrated during live fire exercises. Operationally deployed in Ukraine and during Operation Barkhane in Mali.

**Endurance** — Hybrid run time up to 15 hours. Electric-only run time up to 1.5 hours. Continuous operation until fuel or battery cutoff.

**Environmental** — STANAG 4569 Level 3 armour: 7.62×51 mm AP rounds, anti-tank mines, 155 mm HE fragments at 60 m. Designed for severe climate conditions including desert and Arctic extremes. Air transportable according to STANAG 3542, with internal airlift (CH-47, CH-53, C-130) and helicopter under-slung capability.

**Known limitations** — The vehicle weighs 1,630 kg (curb weight), requiring significant logistical support for transport and deployment. Maximum speed of 20 km/h is slower than wheeled UGVs of comparable size. The tracked configuration, while highly mobile, is not as fast as wheeled platforms on road. The hybrid powertrain adds complexity and maintenance requirements compared to conventional diesel. The 750 kg rated / 1,200 kg maximum payload is substantial but finite; heavier weapon systems or armour packages may exceed it. Human-in-the-loop weapons release means the vehicle cannot engage targets fully autonomously. The open architecture and modular payload system, while a strength, require careful integration testing for each new payload configuration. NBC protection details not publicly disclosed.

---

## Log

**Build history** — THeMIS developed by Milrem Robotics (Estonia). First fully modular hybrid robotics combat vehicle in the world. Acquired by 20 nations, including 8 NATO members: Estonia, France, Germany, the Netherlands, Norway, Spain, the UK, and the US. Operationally proven in Ukraine (over 150 units delivered) and during the anti-insurgency operation Barkhane in Mali. Partnerships with SteerAI (CoreX autonomy kit), EOS (R400 RWS), Frontline (BURIA RWS), ST Engineering (ADDER DM RWS), and others for payload integration.

**Open issues** — Full autonomy level (human-in-the-loop for weapons). NBC protection details. Export control and ITAR restrictions for certain weapon systems. Integration with non-NATO battle management systems. Battery endurance for sustained silent watch operations. Maintenance logistics for the hybrid powertrain in austere environments.

**Changelog** — THeMIS 4.5 research configuration instrumented with three cameras, LiDAR, GNSS, IMU, velocity radar, and common time server for autonomous operations research. SteerAI CoreX integration for UAE Land Forces (20 units) announced IDEX 2025. Continuous payload integration with new weapon stations and C-UAS systems.

**Lessons learned** — Modularity and open architecture are essential for a multi-role UGV; the THeMIS can be reconfigured from transport to strike, from CASEVAC to ordnance disposal, or to support intelligence operations. Hybrid-electric powertrain enables silent movement and silent watch, critical for modern battlefield engagements. High payload capacity (750 kg rated / 1,200 kg max) enables the platform to serve as a power source (3 kW 28 Vdc), transport supplies, carry weapon systems, and evacuate casualties. Operationally proven in Ukraine and Mali, demonstrating reliability in real combat conditions. The THeMIS is the most widely acquired Western UGV, with 20 nations operating the platform.

**Cost actual** — Not publicly disclosed. Defence procurement pricing varies by configuration, quantity, and offset agreements. The THeMIS is positioned as a cost-effective platform relative to larger UGVs and robotic combat vehicles.

---

## Status

**Condition** — operational.<br>

**Blockers** — None. Fielded defence product with active procurement across 20 nations.<br>

**Next steps** — Integration with emerging payloads (C-UAS, loitering munitions, advanced ISR). Expansion of autonomy capabilities (SteerAI CoreX and successor systems). Continued operational deployment and feedback collection. Production scaling to meet demand from existing and new customers. Integration with next-generation battle management systems.

---

**Note on this Shell:** The themis (Milrem THeMIS) is a distinct class in the library: a modular, tracked, hybrid-electric UGV designed for combat support, ISR, logistics, CASEVAC, and ordnance disposal. Unlike the HAVOC (a larger 8×8 robotic combat vehicle with a 30 mm autocannon and 5-tonne payload), the THeMIS is optimized for modularity and multi-role flexibility at a lower weight (1,630 kg) and with a smaller footprint. Its hybrid powertrain enables silent electric-only operation for stealth missions and extended 15-hour hybrid range. The open architecture has enabled integration with a wide range of third-party payloads, from weapon stations (EOS R400, BURIA, ADDER DM) to autonomy kits (SteerAI CoreX). With 20 nations operating the platform and operational deployments in Ukraine and Mali, the THeMIS is the most widely acquired Western UGV of its class. This Shell is the reference for a modular hybrid-electric tracked UGV with STANAG 4569 Level 3 protection, 1,200 kg maximum payload, and proven operational capability.
