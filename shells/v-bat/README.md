# v-bat

**Class:** aerial (Group 3 VTOL UAS)  
**Generation:** 1  
**Version:** 5.3  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Shield AI  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Single-engine, ducted-fan vertical take-off and landing (VTOL) unmanned aircraft system designed for long-endurance ISR and targeting in GPS-denied and communications-contested environments. The V-BAT is not a strategic asset; it is a **tactical, shipboard and expeditionary ISR platform** that a small team can launch from a 5 m² deck or clearing, leave airborne for over 13 hours, and recover without a runway, catapult, or arresting gear. Its defining characteristics are **unassisted VTOL from confined spaces**, **heavy-fuel engine endurance** (JP-5/JP-8), and **Hivemind AI autonomy** that allows it to navigate, complete missions, and return to base without reliance on GNSS or continuous remote control. It has been battle-proven in Ukraine, where it operates with impunity in contested electromagnetic environments that have grounded many traditional drones.

**Environment** — Outdoor, maritime, and expeditionary operations. All-weather, day and night. Designed for shipboard deployment (ship decks, rooftops) and austere land environments. Operating altitude up to 15,000 ft. Endurance up to 13+ hours depending on payload and fuel load. Not for operations in icing conditions or severe turbulence without additional protection. The ducted-fan design allows launch and recovery in confined spaces and high-wind maritime conditions that would prevent conventional fixed-wing or multirotor operations.

**Mission** — Long-range, long-endurance ISR; maritime domain awareness; border security; search and rescue; drug interdiction; and deep-penetration ISR-T (Intelligence, Surveillance, Reconnaissance, and Targeting) in GPS- and comms-denied environments. The V-BAT carries multi-INT payloads including EO/IR, synthetic aperture radar (SAR), passive broadband motion imaging (ViDAR), and electronic warfare (SIGINT, ELINT, COMINT) systems. It can be reconfigured for combat and strike missions, and has been integrated with the L-MDM laser-guided rocket for armed operations.

**Operator** — Two-person launch and recovery team. Single operator for flight control via ground control station. The V-BAT requires no runway, catapult, or launch gear; it launches and lands vertically from a 5 m² area (3.6 m × 3.6 m minimum landing zone). Transport configuration to launch-ready takes approximately 20 minutes. The aircraft is both Hivemind pilot-ready and has SATCOM integration, supporting beyond-line-of-sight control.

**Reusability** — Commercial defence platform with active production and export. Over 130 sorties in Ukraine. Contracts with the US Coast Guard ($198 million, 2024), US Navy, US Marine Corps, Japan Maritime Self-Defence Force, Netherlands Ministry of Defence (8 systems, 2025), Hellenic Army (Greece, 2026), and Indian Army (2026). Production Block 5.3 includes heavy-fuel engine, SATCOM, and Hivemind autonomy.

---

## Spec

**Physical** — Height 2.9 m (9 ft 6 in). Wingspan 3.8 m (12 ft 6 in). Length 2.74 m (9 ft). Maximum gross take-off weight 73 kg (161 lb). Payload capacity 18.1 kg (40 lb). The airframe uses a single-engine ducted-fan configuration, which provides the thrust for vertical flight and forward cruise without exposed rotors. The ducted fan also protects the rotor in shipboard and austere environments. The aircraft can be handled by two persons and transported in a compact configuration.

**Kinematic** — Single-engine ducted-fan VTOL. The ducted fan provides thrust for vertical take-off and landing, and the aircraft transitions to forward flight by tilting the entire airframe (tail-sitter configuration). The wings generate lift in forward flight, and the ducted fan provides forward thrust. Control is achieved through a combination of thrust vectoring, control surfaces, and differential thrust. The single-engine, ducted-fan design is unique among operational VTOL UAS and provides the compact footprint required for shipboard and confined-space operations.

**Dynamic** — Endurance 13+ hours (Block 5.3 with heavy-fuel engine; 12+ hours with EO/IR payload). Maximum speed 157 km/h (85 knots). Cruise speed approximately 47–90 knots depending on configuration. Maximum altitude 15,000 ft. Maximum range 130 km (81 miles) with MPU5 datalink. The heavy-fuel engine (JP-5, JP-8) averages 33 hp, up from 25 hp on previous Mogas-powered versions. The larger fuel tanks hold up to 40 lb (18.1 kg) of fuel, enabling the 13+ hour endurance. The aircraft has demonstrated over 130 sorties in Ukraine and 2,000 hours of flight testing on Block 5.3 prototypes.

**Power** — Single heavy-fuel engine (Suter TOA 288 twin-cylinder) optimised for JP-5 and JP-8. Average power output 33 hp. The engine drives the ducted fan and an integrated generator that provides electrical power to the avionics, sensors, and payloads. The heavy-fuel design is a requirement for US Navy shipboard operations, where JP-5 is the standard fuel. The engine is designed for reliability and ease of maintenance in austere environments. Fuel capacity 40 lb (18.1 kg).

**Thermal** — Passive cooling. The engine is air-cooled with a ram-air intake. The ducted fan provides cooling airflow over the engine and avionics. The exhaust is routed to minimise infrared signature. The heavy-fuel engine reduces the fire hazard compared to gasoline-powered engines, which is critical for shipboard operations.

**Environmental** — Designed for maritime and expeditionary operations. The ducted-fan design allows launch and recovery in confined spaces and high-wind maritime conditions. The aircraft operates in GPS-denied and comms-contested environments with Hivemind autonomy. Not rated for icing conditions without additional protection. Operating temperature range not publicly specified, but the aircraft is deployed in diverse climates including Ukraine (cold winter, hot summer), the Black Sea, the Indo-Pacific, and the Aegean Sea.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The V-BAT is purchased as a complete system with ground control station, datalink, and modular payload integration.

| Component | Notes |
|:---|:---|
| V-BAT airframe | Ducted-fan VTOL, 2.9 m height, 3.8 m wingspan, 73 kg MTOW |
| Suter TOA 288 heavy-fuel engine | Twin-cylinder, 33 hp average, JP-5/JP-8 |
| Ducted fan | Single rotor, enclosed in duct for safety and efficiency |
| Hivemind AI autonomy | GNSS-denied navigation, autonomous take-off/landing, mission execution |
| SATCOM integration | Beyond-line-of-sight control |
| Modular payload bay | 18.1 kg capacity, multi-INT payload integration |
| EO/IR sensor payload | Electro-optical and medium-wavelength infrared cameras |
| SAR payload | Synthetic aperture radar for all-weather imaging |
| ViDAR payload | Passive broadband motion imaging |
| EW payload | SIGINT, ELINT, COMINT for electronic warfare |
| MPU5 datalink | 130 km range mesh network radio |
| Ground control station | Operator interface for mission command and payload control |

**Structure** — Single-engine ducted-fan airframe with a tail-sitter VTOL configuration. The ducted fan is the central structural element, providing thrust for vertical flight and forward cruise. The wings are attached to the duct and generate lift in forward flight. The fuselage houses the engine, fuel tanks, avionics, and payload bay. The ducted-fan design provides several advantages: (1) the enclosed rotor is safer for shipboard operations, (2) the duct provides thrust augmentation at low speeds, and (3) the compact footprint allows launch and recovery from confined spaces. The aircraft packs into a transport configuration and can be assembled by two personnel in approximately 20 minutes.

**Actuation** — Single heavy-fuel engine driving a ducted fan. The ducted fan provides both vertical thrust (for VTOL) and forward thrust (for cruise). Control is achieved through a combination of thrust vectoring (tilting the ducted fan), control surfaces (elevons), and differential thrust. The tail-sitter configuration means the aircraft takes off and lands vertically with the nose pointing up, then transitions to horizontal flight by tilting forward. The Hivemind autonomy manages the transition automatically, and the aircraft can perform unassisted vertical launch and landing without an operator.

**Locomotion** — Ducted-fan VTOL with tail-sitter transition to forward flight. Vertical take-off and landing from a 5 m² area. Transition to forward flight for efficient cruise. The aircraft can loiter at 47 knots for maximum endurance or dash at 90 knots for transit. The ducted-fan design allows operation from ship decks, rooftops, and confined clearings without launch or recovery equipment.

**Manipulation** — None. The aircraft is a sensor and electronic warfare platform. The payload is the effector: EO/IR cameras, SAR, ViDAR, EW systems, or the L-MDM laser-guided rocket for armed configurations.

**Power system** — Single heavy-fuel engine with integrated generator. Fuel capacity 40 lb (18.1 kg) of JP-5 or JP-8. The engine drives the ducted fan and powers the avionics, sensors, and payloads. The heavy-fuel design is a US Navy requirement for shipboard operations. The engine is designed for reliability and ease of maintenance, with the aircraft requiring only two personnel for launch and recovery.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The V-BAT supports multi-payload integration and has been reconfigured for combat and strike missions.

**Custom parts** — None. All components are Shield AI proprietary or certified third-party. The modular payload bay enables rapid reconfiguration for different mission profiles, and the aircraft is both Hivemind pilot-ready and has SATCOM integration.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid deployment and recovery by a two-person team, with modular components for field assembly and maintenance.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The aircraft can be transported in a compact configuration and prepared for launch in approximately 20 minutes by two personnel.

---

## Systems

**Manifest** — Shield AI proprietary software stack with Hivemind AI autonomy and SATCOM integration.

**Firmware** — The aircraft runs Hivemind, Shield AI’s AI pilot software that enables operations in GPS-denied and communications-contested environments. Hivemind provides a GNSS-denied state estimator that merges sensor data to continue navigation in jammed areas. The AI manages autonomous take-off and landing (performed without an operator), autonomous mission execution, and return-to-base in a communications-denied environment. The V-BAT is the only single-engine ducted-fan VTOL UAS operationally deployed across multiple regions worldwide.

**Middleware** — Shield AI proprietary. The V-BAT integrates with the Hivemind autonomy stack and SATCOM for beyond-line-of-sight control. It has been integrated with Palantir’s mission autonomy and command-and-control software, demonstrating the ability to operate as a networked node in a larger force. The aircraft can also operate as an airborne mesh relay, maintaining datalink connectivity even when the direct path is blocked or jammed.

**Perception** — Multi-INT payload suite with 18.1 kg capacity:
- **EO/IR**: Electro-optical and medium-wavelength infrared cameras for day/night imaging and targeting.
- **SAR**: Synthetic aperture radar for all-weather imaging through clouds, smoke, and darkness.
- **ViDAR**: Passive broadband motion imaging for wide-area maritime surveillance.
- **EW**: SIGINT, ELINT, and COMINT payloads for electronic warfare and emitter geolocation.
- **AIS**: Automatic Identification System for maritime vessel tracking.
- **4G/LTE relay**: Communications relay payload for network extension.

**Control** — Hivemind AI autonomy manages flight control, navigation, and mission execution. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The AI handles autonomous take-off and landing, GNSS-denied navigation, and return-to-base. The V-BAT has demonstrated the ability to fly and complete missions in heavily jammed airspace without GPS or continuous communications. The Hivemind autonomy stack also supports swarming and teaming autonomy, with ongoing development for multi-aircraft operations.

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The AI autonomy assists in object detection and classification, providing actionable intelligence to the operator. The aircraft can be retasked in flight, and Hivemind manages the mission execution autonomously.

**Learning** — Hivemind is an AI pilot, but the specific learning architecture is not publicly disclosed. The system uses a GNSS-denied state estimator that merges sensor data, which is a form of sensor fusion rather than learning-based control. The autonomy is designed for reliability and predictability in safety-critical operations, not for online learning. Swarming and teaming autonomy are under development.

**Teleoperation** — Two-person launch and recovery team, single operator for flight control via ground control station. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and autonomous mission execution. SATCOM integration provides beyond-line-of-sight control. The V-BAT can also operate as a node in a larger networked force, with Palantir mission autonomy and command-and-control integration.

**Safety** — Hivemind autonomy enables the aircraft to complete missions and return to base in communications-denied environments, reducing the risk of loss. The ducted-fan design protects the rotor for safe shipboard operations. The heavy-fuel engine reduces fire hazard compared to gasoline-powered engines. The aircraft requires only a 5 m² landing zone (3.6 m × 3.6 m), reducing the risk of damage during recovery in confined spaces. The V-BAT has demonstrated 100% on all key performance parameters during US Coast Guard operational testing aboard National Security Cutters.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The V-BAT has conducted over 130 sorties in Ukraine and 2,000 hours of flight testing on Block 5.3 prototypes. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — MPU5 datalink with 130 km range mesh network radio. SATCOM for beyond-line-of-sight control. The aircraft can operate as an airborne mesh relay, maintaining datalink connectivity even when the direct path is blocked or jammed. It has been integrated with Palantir’s mission autonomy and command-and-control software for networked operations.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the ground control station.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — Shield AI ground control station software. Hivemind autonomy stack. SATCOM integration. Payload-specific software (EO/IR, SAR, ViDAR, EW). Palantir mission autonomy and C2 (optional).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Hivemind autonomy | Proprietary | Shield AI | Autonomy/AI |
| Hivemind Vision | Proprietary | Shield AI | Perception/Vision |
| Flight control | Proprietary | Shield AI | Control/Flight |
| Ground control station | Proprietary | Shield AI | GCS |
| Payload integration software | Proprietary | Various | Payload/Integration |
| Palantir mission autonomy | Proprietary | Palantir | Command/Control |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, fuel state, engine status, system health. Sensor data: EO/IR imagery, SAR imagery, ViDAR data, EW data, AIS tracks. Network data: MPU5 mesh status, SATCOM link status, relay node status.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Weapons authorization (human-in-the-loop, if armed). Datalink and network configuration.

**Serves** — Persistent ISR services. Maritime domain awareness. Target acquisition and tracking. Communications relay services. Electronic warfare services.

**Executes** — Autonomous navigation. Unassisted VTOL take-off and landing. GNSS-denied navigation. Persistent ISR over a local area. Maritime surveillance. Target acquisition. Communications relay. Electronic warfare. Return-to-base in comms-denied environment.

**Extensions** — Modular payload bay (18.1 kg capacity). EO/IR, SAR, ViDAR, EW, AIS, 4G/LTE relay payloads. L-MDM laser-guided rocket for armed configurations. Swarming and teaming autonomy (under development).

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL.

**Units** — SI and aviation standard. Metres, feet, knots, kilometres, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR, SAR, ViDAR, and EW payloads. Flight control system calibrated for ducted-fan VTOL and tail-sitter transition. Hivemind autonomy calibrated for GNSS-denied navigation and autonomous take-off/landing.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and autonomy. The ducted-fan configuration presents unique challenges during transition from vertical to forward flight; Hivemind manages this transition autonomously. The heavy-fuel engine provides sufficient thrust for the 73 kg MTOW and the 18.1 kg payload. The tail-sitter configuration requires precise control during hover and transition, which is achieved through a combination of thrust vectoring and control surfaces.

**Sensor transforms** — Payload sensors mounted in the modular payload bay. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of engine, ducted fan, flight control system, and Hivemind autonomy.

**Integration** — Payload integration in the modular bay. Flight control system verification. Hivemind autonomy verification. SATCOM and MPU5 datalink integration. Autonomous take-off and landing verification.

**Field** — 2,000 hours of flight testing on Block 5.3 prototypes. Over 130 sorties in Ukraine in partnership with Ukrainian forces. Project Convergence Capstone 5 (PC-C5, April 2025): demonstrated resilience to electronic warfare during long-range air assaults. NATO REPMUS 2024: month-long flight trial aboard HNLMS Johan de Witt, validating shipboard performance. US Coast Guard operational testing (July 2025): 100% on all key performance parameters aboard NSCs Midgett and Stone. Netherlands Ministry of Defence procurement (8 systems, July 2025). Hellenic Army order (Greece, June 2026). Indian Army selection (February 2026). Japanese Maritime Self-Defence Force selection (January 2025). US Coast Guard $198 million contract (July 2024).

**Endurance** — 13+ hours with heavy-fuel engine and EO/IR payload. 12+ hours with 40 lb fuel load. Maximum range 130 km (MPU5 datalink).

**Environmental** — All-weather maritime and expeditionary operations. Deployed in Ukraine (cold winter, hot summer), Black Sea, Indo-Pacific, and Aegean Sea. Not for icing conditions without additional protection. Ducted-fan design allows operation in high-wind maritime conditions.

**Known limitations** — The V-BAT is a Group 3 UAS with an 18.1 kg payload capacity; it cannot carry large sensors or heavy weapons. The single-engine design does not have the redundancy of multi-engine platforms, although the ducted-fan configuration provides some inherent safety. The heavy-fuel engine requires JP-5 or JP-8, which is available on US Navy ships but may not be available in all austere environments. The aircraft requires a 5 m² landing zone (3.6 m × 3.6 m) and two personnel for launch and recovery. The 13+ hour endurance is impressive but limited compared to larger MALE/HALE platforms. The Hivemind autonomy is designed for GPS-denied navigation but does not replace human judgment for weapons release. The aircraft is not stealth; it relies on altitude, endurance, and electronic warfare resilience for survivability in contested airspace.

---

## Log

**Build history** — V-BAT developed by Shield AI (originally Martin UAV). Block 5.3 upgrade unveiled April 2025 at Sea Air Space. Heavy-fuel engine (JP-5/JP-8), 33 hp average, 18.1 kg payload, 40 lb fuel capacity. Hivemind autonomy integration ongoing. Swarming and teaming autonomy under development. Over 130 sorties in Ukraine. US Coast Guard contract ($198 million, 2024). Netherlands (8 systems, 2025). Greece (2026). India (2026). Japan (2025).

**Open issues** — Swarming and teaming autonomy development. Integration with emerging payloads (L-MDM laser-guided rocket). Heavy-fuel logistics in austere environments. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — V-BAT Block 5.3: heavy-fuel engine (JP-5/JP-8), 33 hp, 18.1 kg payload, 40 lb fuel, 13+ hours endurance, unassisted VTOL, Hivemind autonomy, SATCOM integration. Previous versions: Mogas-powered, 25 hp, 11.3 kg payload, 57 kg MTOW.

**Lessons learned** — The single-engine ducted-fan VTOL design is the key enabler of shipboard and confined-space operations. The heavy-fuel engine is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. Hivemind autonomy enables operations in GPS-denied and comms-contested environments, which is critical for operations against peer adversaries. The V-BAT has been battle-proven in Ukraine, where it operates with impunity in contested electromagnetic environments that have grounded many traditional drones. The aircraft’s ability to operate as an airborne mesh relay maintains datalink connectivity even when the direct path is blocked or jammed.

**Cost actual** — US Coast Guard contract: $198 million for an undisclosed quantity of V-BAT systems (2024). Unit cost varies by configuration, payload, and quantity. The V-BAT is positioned as a cost-effective alternative to larger MALE/HALE platforms for shipboard and expeditionary ISR.

---

## Status

**Condition** — operational. Fielded with US Navy, US Marine Corps, US Coast Guard, Japan, Netherlands, Greece, India, and Ukraine.

**Blockers** — None. Active production and procurement.

**Next steps** — Integration of L-MDM laser-guided rocket for armed configurations. Swarming and teaming autonomy development. Expansion of export sales to allied and partner forces. Continued deployment in Ukraine and other contested environments. Production scaling to meet demand.

---

**Note on this Shell:** The v-bat is a distinct class in the library: a Group 3 VTOL UAS designed for **shipboard and expeditionary ISR** in GPS-denied and communications-contested environments. Unlike the k1000ule (solar-powered, 75-hour endurance, Group 2) or the orion (tethered, 50-hour endurance, fixed position), the V-BAT is a free-flying, heavy-fuel-powered aircraft with 13+ hours of endurance and an 18.1 kg multi-INT payload capacity. Its single-engine ducted-fan design is unique among operational VTOL UAS and provides the compact footprint required for launch and recovery from ship decks, rooftops, and confined clearings. The heavy-fuel engine (JP-5/JP-8) is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. Hivemind autonomy enables operations in GPS-denied and comms-contested environments, which is critical for operations against peer adversaries. With over 130 sorties in Ukraine, 2,000 hours of flight testing, and contracts with the US Coast Guard, US Navy, US Marine Corps, Japan, Netherlands, Greece, and India, the V-BAT is the reference for a battle-proven, shipboard-capable, long-endurance VTOL ISR platform.
