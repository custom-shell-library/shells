# puma

**Class:** aerial (Group 2 hand-launched fixed-wing UAS)  
**Generation:** 1  
**Version:** LE (Long Endurance)  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** AeroVironment  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Hand-launched, man-portable Group 2 fixed-wing unmanned aircraft system designed for persistent local ISR and precision targeting at the platoon, company, and special operations level. The Puma is not a strategic asset; it is a **small unit organic ISR platform** that two soldiers can carry in two cases, assemble and launch by hand or bungee in minutes, and leave airborne for up to 6.5 hours — more than double the endurance of a typical Group 1 aircraft. Its defining characteristics are **Group 2 capabilities in a Group 1 footprint**, **modular open payload bay** for rapid field reconfiguration, and **GNSS-denied navigation** via visual-inertial odometry. It is one of the most combat-proven small UAS in the world, with over 500,000 cumulative flight hours across US military users alone.

**Environment** — Outdoor, all-environment, day and night operations. Rated for land and maritime operations, including landing in water. Deployed from forward positions, confined spaces, and small boats. Operating altitude 300–3,000 ft AGL typical, maximum launch 10,000 ft MSL. Endurance up to 6.5 hours with the Puma Smart 2500 battery. Not for operations in icing conditions or severe turbulence without additional protection. The airframe is reinforced for durability and all-environment rated.

**Mission** — Persistent local ISR, route reconnaissance, force protection, overwatch, target acquisition, and precision laser designation for guided munitions. The Puma LE carries the Mantis i45 gimbaled EO/IR payload with dual 15 MP EO cameras, IR, and low-light cameras, and supports a laser target designator for STANAG 3733-compliant precision targeting. The secondary payload bay enables rapid integration of mission-specific sensors including SIGINT, electronic warfare, RF geolocation, and communications relay. It is designed for tactical units and special operations, combining long dwell time with ease of deployment.

**Operator** — Two-person team. The aircraft packs into two cases, assembles and launches by hand or bungee, and recovers by autonomous or manual skid landing. A single operator controls the aircraft via the Tomahawk GCS; the second person assists with launch and recovery. The aircraft is inaudible at 500 feet.

**Reusability** — Commercial defence platform with active production and global service. Over 500,000 cumulative flight hours across US military users. Deployed by every branch of the US military — Army, Navy, Air Force, Marines, and Special Operations Command — and more than 45 allied nations. The Puma LE is the newest member of the Puma All Environment family, leveraging existing Puma RQ-20B and Puma 3 AE line-replaceable units for easy upgrade. The US Army awarded an $874.26 million five-year IDIQ contract in October 2025 for Puma 3 AE, Puma LE, and Puma AE/LE Hybrid systems for Foreign Military Sales.

---

## Spec

**Physical** — Wingspan 15 ft (4.6 m) for Puma LE. Length 7.3 ft (2.2 m). Weight 23.8 lb (10.8 kg), with 27.3 lb (12.4 kg) maximum gross take-off weight. Payload capacity 5.5 lb (2.5 kg). The airframe is constructed from lightweight composite materials with a reinforced fuselage and center wing to accommodate heavier configurations. The Puma LE uses the same cases as the Puma 3 AE with custom foam inserts, packing into two cases for transport. The system is hand-launched or bungee-launched, requiring no runway or launch gear.

**Kinematic** — Fixed-wing, hand-launched or bungee-launched. Recovery by autonomous or manual precision skid landing. The aircraft can operate in all environments, including landing in water. Optional Puma VTOL Kit provides vertical take-off and landing in urban environments. Optional Puma VNS (Visual Navigation System) provides GPS-denied navigation in contested environments. The flight control system manages all phases of flight autonomously. Cruise speed 44 km/h (24 kts), dash speed 76 km/h (41 kts).

**Dynamic** — Endurance 5.5 hours with Mantis i45 (Puma LE) or up to 6.5 hours with the Puma Smart 2500 battery. Link range 20 km standard, 40 km with ERA, 60 km with LRTA. Operating altitude 300–500 ft AGL typical, maximum launch 10,000 ft MSL. Maximum flight altitude 10,500 ft MSL. The extended endurance provides long-dwell ISR coverage over areas of interest, increasing time on station and improving situational awareness for tactical planners and operators.

**Power** — Electric propulsion. Puma Smart Battery or PS2500 Battery. The Puma LE achieves 5.5 hours endurance with the Mantis i45 payload; up to 6.5 hours with the Puma Smart 2500 battery. The aircraft is hand-launched or bungee-launched, with no fuel logistics required. Battery options support diverse missions, and the aircraft is all-environment rated.

**Thermal** — Passive cooling. The electric motor is air-cooled by ram air in forward flight. The low thermal signature reduces detectability compared to internal combustion engines. The aircraft is inaudible at 500 feet, making it difficult to detect by acoustic sensors.

**Environmental** — All-environment rated, including landing in water. Reinforced fuselage and center wing accommodate heavier configurations. The aircraft operates in extreme environments from desert heat to Arctic cold. Not rated for icing conditions without additional protection. The composite airframe is resistant to salt spray and UV degradation.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Puma LE is purchased as a complete system with ground control station and modular payload integration.

| Component | Notes |
|:---|:---|
| Puma LE airframe | Composite construction, 4.6 m wingspan, 10.8 kg weight, 12.4 kg MGTOW |
| Electric motor | Brushless DC, pusher propeller |
| Puma Smart Battery / PS2500 Battery | 5.5–6.5 hours endurance |
| Mantis i45 gimbaled payload | Dual 15 MP EO, IR, low-light cameras, laser illuminator |
| Mantis i45 N | Enhanced nighttime payload (LWIR/5 MP low-light) |
| HD59-LD laser designator payload | Trillium Engineering, 50mJ STANAG 3733-compliant laser, 64 MP EO, MWIR, SWIR |
| Universal Gimbal Kit | Field-swappable gimbaled payloads, max 4.6 lb (2100 g) |
| Secondary payload bay | Dedicated power and Ethernet for SIGINT, EW, RF geolocation, communications relay |
| Puma VTOL Kit | Vertical take-off and landing in urban environments |
| Puma VNS (Visual Navigation System) | Computer vision and inertial data fusion for GNSS-denied navigation |
| Tomahawk GCS | Ground control station, common with Puma 3, Raven, Wasp AE |
| Enhanced Digital Data Link | AES-256 bit encryption, more frequencies |

**Structure** — Lightweight composite airframe with high aspect ratio wing. The fuselage houses the electric motor, battery, avionics, and modular payload bays. The aircraft is designed for hand or bungee launch and skid landing. The Puma LE features a modular open payload bay with dedicated power and Ethernet connections, allowing rapid integration of mission-specific sensors without tools for rapid field changes. The system leverages existing Puma RQ-20B and Puma 3 AE line-replaceable units (LRUs), allowing any current Puma AE user to easily upgrade fielded systems.

**Actuation** — Single brushless DC electric motor driving a pusher propeller. Control surfaces actuated by electromechanical actuators. The Puma VTOL Kit provides vertical take-off and landing capability for urban environments. The flight control system manages all phases of flight autonomously. The aircraft is inaudible at 500 feet.

**Locomotion** — Fixed-wing flight. Hand-launched or bungee-launched. Recovery by autonomous or manual precision skid landing. The Puma VTOL Kit adds vertical take-off and landing capability. The Puma VNS kit enables GNSS-denied navigation via visual-inertial odometry. Cruise speed 44 km/h, dash speed 76 km/h.

**Manipulation** — None. The aircraft is a sensor and precision targeting platform. The payload is the effector: EO/IR cameras, laser designator, SIGINT, electronic warfare, RF geolocation, or communications relay. The modular open payload bay allows rapid reconfiguration for different mission profiles.

**Power system** — Electric propulsion with Puma Smart Battery or PS2500 Battery. The Puma LE achieves 5.5 hours endurance with the Mantis i45 payload; up to 6.5 hours with the Puma Smart 2500 battery. No fuel logistics required. The aircraft is hand-launched or bungee-launched, with no launch equipment needed.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular open payload bay with dedicated power and Ethernet. The Universal Gimbal Kit allows operators to rapidly integrate a variety of gimbaled payloads in the field without depot-level support.

**Custom parts** — None. All components are AeroVironment proprietary or certified third-party. The modular open payload bay enables integration of third-party payloads including SIGINT, EW, RF geolocation, and communications relay.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid deployment and recovery by a two-person team, with modular components for field assembly and maintenance. Field-swappable Mantis payloads for day and night operations.

**Tools required** — None for assembly (factory-built). No tools required for payload changes. Standard tools for field maintenance.

---

## Systems

**Manifest** — AeroVironment proprietary software stack with modular open payload bay and GNSS-denied navigation.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation, including hand or bungee launch, waypoint-controlled skid landing, and autonomous navigation. The Puma VNS (Visual Navigation System) uses computer vision and inertial data fusion to enable GNSS-denied navigation in contested environments. It automatically transitions between GNSS-enabled and GNSS-denied modes with zero pilot input, ensuring uninterrupted mission continuity. The VNS kit was first introduced in 2022 for the Puma 2 AE and Puma 3 AE, and was expanded to Puma LE in 2025.

**Middleware** — AeroVironment proprietary. The Enhanced Digital Data Link covers more frequencies and supports AES-256 bit encryption. The aircraft uses the Tomahawk GCS, common with Puma 3, Raven, and Wasp AE, allowing operators to control the aircraft manually or program it for GPS-based autonomous navigation. The common GCS reduces training burden across the AeroVironment family of systems.

**Perception** — Modular payload suite with 5.5 lb (2.5 kg) capacity and dedicated power and Ethernet:
- **Mantis i45**: Dual 15 MP EO cameras, IR camera, low-light camera, and high-power laser illuminator. Gimbaled with 360° continuous pan and +10 to −90° tilt.
- **Mantis i45 N**: Enhanced nighttime payload with LWIR and 5 MP low-light camera.
- **HD59-LD laser designator**: Trillium Engineering, 50mJ STANAG 3733-compliant laser designator, 64 MP EO camera, narrow field-of-view MWIR sensor, and see-spot SWIR. Weighs under 2 kg.
- **Secondary payload bay**: Dedicated power and Ethernet for SIGINT, electronic warfare, RF geolocation, and communications relay.
- **See Spot capability**: Laser spot detection.

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft can be manually or autonomously navigated while gaining real-time situational awareness and actionable intelligence through the Tomahawk GCS. The Puma VNS enables GNSS-denied navigation with automatic transitions between GNSS-enabled and GNSS-denied modes.

**Planning** — Mission planning is performed at the Tomahawk GCS. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The aircraft can be retasked in flight. Hand or bungee launch and autonomous skid landing enable rapid deployment from forward positions or confined spaces.

**Learning** — None publicly disclosed. The aircraft uses classical control, autonomous navigation, and computer vision (via VNS) for GNSS-denied navigation. No learning-based control is mentioned for safety-critical functions.

**Teleoperation** — Two-person launch and recovery team, single operator for flight control via the Tomahawk GCS. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and autonomous recovery. The common GCS with Raven and Wasp AE reduces training burden across the AeroVironment family.

**Safety** — The aircraft is all-environment rated, including landing in water. The Puma VNS enables GNSS-denied navigation in contested environments, reducing the risk of loss due to jamming or spoofing. The aircraft is inaudible at 500 feet, reducing the risk of detection. The reinforced fuselage and center wing improve durability. The Precision navigation system with secondary GPS provides greater positional accuracy and reliability.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The Puma family has accumulated over 500,000 cumulative flight hours across US military users alone. Specific logging details are not publicly disclosed, but the system is designed for ISR and precision targeting missions where evidence capture and target tracking are important.

**Networking** — Enhanced Digital Data Link with AES-256 bit encryption, covering more frequencies. Link range 20 km standard, 40 km with ERA, 60 km with LRTA. The aircraft can carry communications relay payloads for network extension via the secondary payload bay.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the Tomahawk GCS.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — AeroVironment Tomahawk GCS software. Puma VNS (visual-inertial odometry). Payload-specific software (Mantis i45, HD59-LD laser designator, SIGINT, EW, communications relay).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| AeroVironment flight control | Proprietary | AeroVironment | Control/Flight |
| Puma VNS (Visual Navigation System) | Proprietary | AeroVironment | Navigation/GNSS-Denied |
| Tomahawk GCS | Proprietary | AeroVironment | GCS |
| Mantis i45 software | Proprietary | AeroVironment | Sensors/EOIR |
| HD59-LD laser designator software | Proprietary | Trillium Engineering | Sensors/Laser |
| Payload integration software | Proprietary | Various | Payload/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, system health. Sensor data: EO/IR imagery, laser designation status, SIGINT/EW data. Network data: datalink status, relay node status.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Laser designation commands.

**Serves** — Persistent ISR services. Target acquisition and tracking. Precision laser designation for guided munitions. Communications relay. Electronic warfare.

**Executes** — Autonomous hand/bungee launch, transition to forward flight, persistent ISR over a local area, target acquisition, laser designation, autonomous skid landing. Return-to-base in comms-denied environment. GNSS-denied navigation via VNS.

**Extensions** — Modular open payload bay (5.5 lb capacity). Mantis i45, Mantis i45 N, HD59-LD laser designator, SIGINT, EW, RF geolocation, communications relay payloads. Puma VTOL Kit for vertical take-off and landing. Puma VNS for GNSS-denied navigation. Universal Gimbal Kit for field-swappable payloads.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL or AGL.

**Units** — SI and aviation standard. Metres, feet, knots, kilometres, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for Mantis i45, Mantis i45 N, and HD59-LD laser designator. Flight control system calibrated for hand/bungee launch and skid landing. Puma VNS calibrated for visual-inertial odometry.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and autonomy. The high aspect ratio wing provides efficient cruise and long endurance. The reinforced fuselage and center wing accommodate heavier configurations. The upgraded motor provides up to 26% increased climb rate in heavier configurations.

**Sensor transforms** — Payload sensors mounted in the modular open payload bay and Universal Gimbal Kit. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motor, battery, flight control system, and payloads.

**Integration** — Payload integration in the modular open payload bay. Flight control system verification. Puma VNS integration and GNSS-denied navigation verification. Universal Gimbal Kit verification. HD59-LD laser designator integration and STANAG 3733 compliance verification.

**Field** — Over 500,000 cumulative flight hours across US military users. Deployed by every branch of the US military and more than 45 allied nations. Operationally proven in Ukraine since 2022; Puma LE received laser target designator and Universal Gimbal Kit upgrades for combat conditions (October 2025). Ukraine purchasing 11 PUMA-LE systems (June 2026). $874.26 million US Army IDIQ contract for Puma 3 AE, Puma LE, and Puma AE/LE Hybrid systems for Foreign Military Sales (October 2025). US Marine Corps contract for Puma 3 AE (June 2022). US Navy and Marine Corps small tactical UAS program (April 2020). US Air Force orders (July 2021). US Army orders (July 2022).

**Endurance** — 5.5 hours with Mantis i45 (Puma LE), up to 6.5 hours with Puma Smart 2500 battery. Link range 20 km standard, 40 km with ERA, 60 km with LRTA. Operating altitude 300–500 ft AGL typical, maximum launch 10,000 ft MSL.

**Environmental** — All-environment rated, including landing in water. Operates in extreme environments from desert heat to Arctic cold. Not for icing conditions without additional protection.

**Known limitations** — The Puma LE is a Group 2 UAS with a 5.5 lb payload capacity; it cannot carry large sensors or heavy weapons. The 5.5–6.5 hour endurance is impressive for its size but limited compared to larger MALE/HALE platforms. The aircraft requires a two-person team for launch and recovery. The hand or bungee launch requires open space; the Puma VTOL Kit addresses this limitation for urban environments. The aircraft is not stealth; it relies on low acoustic and thermal signatures, altitude, and GNSS-denied navigation for survivability in contested airspace. The 60 km link range with LRTA requires the LRTA antenna, which adds to the system’s logistics footprint.

---

## Log

**Build history** — Puma developed by AeroVironment. Puma AE (RQ-20A) ordered by US Army in March 2012; US Marine Corps and US Air Force ordered in April 2012. Puma AE (RQ-20B) introduced with upgraded precision navigation and secondary GPS. Puma 3 AE introduced with reinforced fuselage, upgraded motor (26% increased climb rate), and field-swappable Mantis payloads. Puma LE (Long Endurance) introduced as the newest member of the Puma All Environment family, delivering Group 2 capabilities in a Group 1 footprint with 5.5 hours endurance. Puma VNS introduced in 2022 for Puma 2 AE and Puma 3 AE; expanded to Puma LE in 2025. Universal Gimbal Kit and HD59-LD laser designator introduced September 2025. US Army $874.26 million IDIQ contract awarded October 2025.

**Open issues** — Expansion of payload options (SIGINT, EW, RF geolocation, communications relay). Integration with emerging battle-management systems. Continued deployment in Ukraine. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — Puma AE (RQ-20A): initial production configuration. Puma AE (RQ-20B): upgraded precision navigation, secondary GPS. Puma 3 AE: reinforced fuselage, upgraded motor, field-swappable Mantis payloads. Puma LE: 5.5 hours endurance, modular open payload bay, 60 km range with LRTA. Puma VNS: GNSS-denied navigation (2022, expanded to LE in 2025). Universal Gimbal Kit and HD59-LD laser designator: September 2025. Puma VTOL Kit: vertical take-off and landing in urban environments.

**Lessons learned** — The hand-launched, man-portable design is the key enabler of small unit organic ISR. The modular open payload bay and Universal Gimbal Kit enable rapid field reconfiguration, allowing operators to swap between day/night sensors and precision targeting payloads without depot-level support. The Puma VNS provides GNSS-denied navigation, which is critical for operations against peer adversaries in contested electromagnetic environments. The common GCS with Raven and Wasp AE reduces training burden across the AeroVironment family of systems. The Puma family has accumulated over 500,000 flight hours, validating the platform’s reliability and effectiveness.

**Cost actual** — US Army $874.26 million five-year IDIQ contract for Puma 3 AE, Puma LE, and Puma AE/LE Hybrid systems for Foreign Military Sales. Unit cost varies by configuration, payload, and quantity. The Puma LE is positioned as a cost-effective, attritable ISR asset for tactical and special operations.

---

## Status

**Condition** — operational. Fielded with every branch of the US military and more than 45 allied nations. Over 500,000 cumulative flight hours. US Army $874.26 million IDIQ contract active.

**Blockers** — None. Active production and global service.

**Next steps** — Integration of new payloads (SIGINT, EW, RF geolocation, communications relay). Continued fielding with US Army, US Marine Corps, US Navy, US Air Force, and USSOCOM. Expansion of Foreign Military Sales to allied and partner forces under the $874.26 million IDIQ contract. Continued deployment in Ukraine with laser target designator and Universal Gimbal Kit upgrades. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The puma is a distinct class in the library: a Group 2 hand-launched fixed-wing UAS designed for **small unit organic ISR** with 5.5–6.5 hours of endurance and a 5.5 lb modular payload capacity. Unlike the v-bat (ducted-fan, heavy-fuel, 13-hour endurance, Group 3), the stalker (hybrid VTOL, propane fuel cell, 8+ hours, Group 2), or the scaneagle (conventional fixed-wing, heavy-fuel, 18+ hours, Group 2), the Puma is a hand-launched, man-portable aircraft that a two-soldier team can carry in two cases and launch without any equipment. Its Group 2 capabilities in a Group 1 footprint make it uniquely suited for platoon and company-level operations where portability and ease of deployment are paramount. The Puma VNS provides GNSS-denied navigation via visual-inertial odometry, which is critical for operations against peer adversaries. The Universal Gimbal Kit and HD59-LD laser designator (September 2025) transform the Puma LE into a precision targeting platform capable of marking targets for guided munitions. With over 500,000 flight hours across every branch of the US military and more than 45 allied nations, and an $874.26 million US Army IDIQ contract active, the Puma is the reference for a combat-proven, hand-launched, man-portable, long-endurance ISR and precision targeting platform.
