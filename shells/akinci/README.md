# akinci

**Class:** aerial (MALE UCAV)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Baykar  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Twin-engine Medium-Altitude Long-Endurance (MALE) Unmanned Combat Aerial Vehicle (UCAV) designed for strategic-class ISR and strike missions. The Akıncı is the successor to the Bayraktar TB2 and the largest drone in Baykar's catalogue. It is designed to conduct operations traditionally performed by fighter jets: air-to-ground strike, air-to-air engagement, electronic warfare, and persistent surveillance. Its defining characteristic is the dual artificial intelligence avionics architecture that fuses sensor data for real-time situational awareness, and the 1,500 kg payload capacity across five hardpoints that allows it to carry a wider range of munitions than any other drone in its class.

**Environment** — Runway-operated, all-weather, day and night operations. Service ceiling 40,000 ft. Maximum speed 195–240 KTAS. Endurance 24+ hours. Operational range 6,000 km. The aircraft is not stealth; it relies on altitude, endurance, electronic warfare systems, and standoff weapons for survivability. Not for operations in icing conditions or severe turbulence without additional protection.

**Mission** — Strategic ISR, air-to-ground strike, air-to-air engagement, electronic warfare, maritime patrol, and communications relay. The Akıncı is capable of conducting operations performed with fighter jets, including air-to-ground and air-to-air attack missions. It carries electronic support systems, dual satellite communication systems, air-to-air radar, collision avoidance radar, and synthetic aperture radar. In February 2026, an Akıncı successfully conducted an air-to-air firing test with the EREN high-speed multi-purpose loitering munition, scoring a direct hit on an airborne target UAV.

**Operator** — Ground control station crew: pilot, payload operator, and image exploitation console. The Ground Control Station is a NATO-spec ACE-III shelter with NBC filtration, military air conditioning units, and a full suite of radio systems and consoles. The aircraft is controlled via LOS and BLOS (SATCOM) data links.

**Reusability** — Commercial defence platform with active production and export. Over 60 units built. In service with the Turkish Air Force, Turkish Land Forces, Turkish Navy, and multiple export customers. The aircraft was inducted into Turkish Land Forces service in April 2026.

---

## Spec

**Physical** — Length 12.2–12.3 m. Height 4.1 m. Wingspan 20 m. Maximum takeoff weight 6,000 kg (13,227 lb). Payload capacity 1,500 kg across five hardpoints. The airframe features a unique fuselage and wing design with a "bent" wing shape that distinguishes it from the TB2. The structure is optimised for the twin-engine configuration and the large payload capacity.

**Kinematic** — Twin turboprop engines driving pusher propellers. Engine options: 2 × 450 HP, 2 × 750 HP, or 2 × 850 HP turboprop engines. The aircraft is runway-operated with fully automatic takeoff and landing capability, including precise auto takeoff and landing with built-in sensor fusion, and fully automatic taxi and parking. The twin-engine configuration provides redundancy: if one engine fails, the aircraft can continue flight on the remaining engine.

**Dynamic** — Endurance 24+ hours. Maximum speed 195–240 KTAS. Cruise speed 150 KTAS. Service ceiling 40,000 ft. Operational altitude 30,000 ft. Operational range 6,000 km. Maximum altitude demonstrated: 45,118 ft. The twin turboprop engines provide sufficient thrust for the 6,000 kg MTOW and the 1,500 kg payload, while the high aspect ratio wing provides efficient cruise for long endurance.

**Power** — 2 × turboprop engines (450–850 HP each). The engines drive generators that provide electrical power to the avionics, sensors, and payloads. The aircraft carries sufficient fuel for 24+ hours of flight at cruise speed. The twin-engine configuration provides power redundancy for the flight-critical avionics and the payload suite.

**Thermal** — Passive cooling. The engine exhaust is routed to minimise infrared signature, though the Akıncı is not a stealth aircraft. The avionics bay is cooled by ram air and forced convection. The composite airframe acts as a heat sink for distributed electronics. No active refrigeration is required for the operating envelope.

**Environmental** — Designed for operation in all-weather conditions. Not rated for icing conditions without additional anti-ice systems. Operating temperature range not publicly specified, but the aircraft is deployed in diverse climates from the Middle East to North Africa and beyond.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build.

| Component | Notes |
|:---|:---|
| Baykar Akıncı airframe | Composite construction, 12.3 m length, 20 m wingspan, 6,000 kg MTOW |
| 2× turboprop engines | 450 HP, 750 HP, or 850 HP options |
| Aselsan CATS EO/IR system | Common Aperture Targeting System for ISTAR |
| AESA radar | Multi-function: air-to-air, synthetic aperture, weather |
| Dual SATCOM | Beyond-line-of-sight control and video transmission |
| Dual LOS data link | Line-of-sight control and video transmission |
| Electronic support systems | Electronic warfare and signals intelligence |
| Collision avoidance radar | Air-to-air collision avoidance |
| Triple redundant autopilot | Fault-tolerant flight control |
| Redundant servo actuator units | Unique redundant design for flight control |
| Redundant lithium-based battery units | Power redundancy for critical systems |
| Ground Control Station | NATO-spec ACE-III shelter with NBC filtration |
| 5× hardpoints | 1,500 kg total payload capacity |

**Structure** — Composite airframe with a unique fuselage and wing design. The "bent" wing shape is a distinguishing feature. The internal structure houses the avionics, fuel, and payload bays. The five hardpoints are distributed across the wings and fuselage for flexible munitions carriage. The aircraft is designed for ease of maintenance and rapid turnaround.

**Actuation** — Twin turboprop engines. Control surfaces actuated by redundant servo actuator units. The triple redundant autopilot system provides fault tolerance: if one autopilot channel fails, the remaining channels maintain control. The cross-redundant YKI system provides additional fault tolerance.

**Locomotion** — Fixed-wing flight. Runway takeoff and landing. Fully automatic takeoff and landing without dependence on ground systems, using built-in sensor fusion for precise auto takeoff and landing.

**Manipulation** — None. The aircraft is a weapons and sensor platform. The five hardpoints provide the effector capability: MAM-L, MAM-C, MAM-T, Cirit, L-UMTAS, Bozok, MK-81/82/83 JDAM, Wing Assisted Guided Bomb MK-82, Gokdogan and Bozdogan air-to-air missiles, SOM-A stand-off missile, and the EREN loitering munition.

**Power system** — Twin turboprop engines driving generators. The electrical system provides power to the avionics, sensors, payloads, and redundant battery units. The redundant lithium-based battery units provide backup power for flight-critical systems in the event of generator failure.

**Wiring** — Internal only. Not user-accessible. Payload integration via five hardpoints and the internal payload bay. The aircraft has triple-redundant electronics hardware and software systems for the flight-critical functions.

**Custom parts** — None. All components are Baykar proprietary or certified third-party (Aselsan, Roketsan, TÜBİTAK SAGE).

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting, munitions loading, and field maintenance.

---

## Systems

**Manifest** — Baykar proprietary software stack with dual artificial intelligence avionics and triple-redundant flight control.

**Firmware** — The aircraft runs dual artificial intelligence avionics that support signal processing, sensor fusion, and situational awareness in real time. The fully automatic flight control system with three redundant autopilot channels provides fault tolerance. The aircraft can navigate with internal sensor fusion without dependency on GPS. The AI system offers improved flight and diagnostic functions.

**Middleware** — Baykar proprietary. The aircraft uses triple bands for LOS control and video transmission. BLOS control and video transmission via SATCOM. BLOS operations can be supported over existing worldwide satellite networks and attendant ground data terminals, or alternatively, SATCOM data terminals can be supplied.

**Perception** — Multi-sensor suite:
- **Aselsan CATS**: Common Aperture Targeting System EO/IR for ISTAR.
- **AESA Radar**: Multi-function radar for air-to-air, synthetic aperture, and weather estimation.
- **Collision Avoidance Radar**: Air-to-air collision avoidance.
- **Electronic Support Systems**: Electronic warfare and signals intelligence.
- **Dual SATCOM**: Beyond-line-of-sight communication.
- **Dual Redundant LOS**: Line-of-sight communication.

**Control** — The triple-redundant autopilot manages all flight control functions. The aircraft supports semi-autonomous flight modes and fully automatic navigation and route tracking. The dual AI avionics fuse sensor data for real-time situational awareness. The pilot in the Ground Control Station provides mission-level command; the aircraft handles flight control, navigation, and sensor fusion autonomously.

**Planning** — Fully automatic navigation and route tracking. The aircraft supports precise auto takeoff and landing with built-in sensor fusion, and fully automatic taxi and parking. The Ground Control Station provides mission planning, payload control, and image exploitation.

**Learning** — The dual AI avionics system provides situational awareness and diagnostic functions, but no learning-based control is publicly disclosed for safety-critical weapons release. The AI is used for sensor fusion, signal processing, and improved flight and diagnostic functions.

**Teleoperation** — Ground Control Station crew: pilot console, payload operator console, and image exploitation console. The Ground Control Station is a NATO-spec ACE-III shelter with NBC filtration system, military-type air conditioning units, power systems, filters, and rack-type cabinets. The aircraft is controlled via triple-band LOS and SATCOM BLOS data links.

**Safety** — Triple redundant autopilot system. Cross-redundant YKI system. Unique redundant servo actuator units. Redundant lithium-based battery units. Fault-tolerant and 3-redundant sensor fusion application. Fully automatic takeoff and landing without dependence on ground systems. Navigation with internal sensor fusion without dependency on GPS. Human-in-the-loop for weapons release.

**Logging** — Mission data, sensor data, and weapons employment logs. The Ground Control Station includes an image exploitation console for data analysis. Specific logging details are not publicly disclosed.

**Networking** — Triple-band LOS control and video transmission. BLOS control and video transmission via SATCOM. The Ground Control Station is networked with radio systems, internal conversation systems, and power systems.

**Config files** — Proprietary. No user-accessible config files.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Baykar Ground Control Station software. Aselsan CATS software. AESA radar software. Roketsan munitions integration. TÜBİTAK SAGE munitions integration. EREN loitering munition integration.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Baykar flight control | Proprietary | Baykar | Control/Flight |
| Dual AI avionics | Proprietary | Baykar | Autonomy/AI |
| CATS EO/IR software | Proprietary | Aselsan | Sensors/EOIR |
| AESA radar software | Proprietary | Aselsan | Sensors/Radar |
| Electronic support software | Proprietary | Aselsan | Sensors/EW |
| Munitions integration software | Proprietary | Roketsan / TÜBİTAK | Weapons/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, airspeed, altitude, fuel state, engine status, system health. Sensor data: EO/IR imagery, AESA radar tracks, SIGINT data, SATCOM/LOS video. Weapons status.

**Accepts** — Navigation commands (waypoints, routes, semi-autonomous flight modes). Weapons authorization (human-in-the-loop). Sensor tasking commands. Payload commands. Munitions selection and release commands.

**Serves** — Mission planning, sensor tasking, data exploitation, image exploitation.

**Executes** — Autonomous navigation. Air-to-ground strike. Air-to-air engagement. ISR. Electronic warfare. Maritime patrol. Communications relay. Fully automatic takeoff and landing.

**Extensions** — Five hardpoints for munitions. AESA radar. Electronic support systems. Dual SATCOM. Air-to-air missiles. Stand-off missiles. Loitering munitions.

**Frame conventions** — Military grid reference system (MGRS) for position. NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL.

**Units** — SI and military standard. Meters, kilometres, knots, feet, kilograms, pounds.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for CATS EO/IR, AESA radar, and electronic support systems. Munitions calibration for the five hardpoints.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and simulation. The twin turboprop engines provide sufficient thrust for the 6,000 kg MTOW and the 1,500 kg payload.

**Sensor transforms** — CATS EO/IR, AESA radar, and electronic support systems mounted at optimised locations on the airframe. Five hardpoints for munitions.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — Payload integration on five hardpoints. Sensor calibration and verification. Munitions integration (MAM-L, MAM-C, MAM-T, Cirit, L-UMTAS, Bozok, JDAM, SOM-A, EREN). Dual SATCOM and triple-band LOS data link verification. Triple redundant autopilot verification.

**Field** — Endurance test: 24+ hour flight. Altitude test: 40,000 ft service ceiling. Range test: 6,000 km. Air-to-ground firing tests. Air-to-air firing test (February 2026): EREN loitering munition scored a direct hit on an airborne target UAV. Semi-autonomous flight mode testing. GPS-denied navigation testing.

**Endurance** — Maximum endurance 24+ hours. Maximum altitude 45,118 ft (demonstrated). Maximum speed 195–240 KTAS. Operational range 6,000 km.

**Environmental** — All-weather operations. Deployed in diverse climates. Not for icing conditions without additional protection.

**Known limitations** — The Akıncı is not a stealth aircraft; it relies on altitude, electronic warfare systems, and standoff weapons for survivability in contested airspace. The 1,500 kg payload capacity is substantial but finite; heavier weapon systems or additional fuel for extended endurance may exceed it. The twin turboprop engines provide redundancy but add complexity and maintenance requirements compared to single-engine drones. The aircraft requires a runway for takeoff and landing, limiting deployment options compared to VTOL platforms. The EREN loitering munition air-to-air test was a significant milestone but represents a new capability that requires further operational validation. Export control and ITAR restrictions may apply to certain munitions and sensor systems.

---

## Log

**Build history** — Bayraktar Akıncı developed by Baykar. First engine test September 2019. Maiden flight December 2019. PT-1 second flight January 2020. PT-2 testing completed August 2020. System identification test March 2021. PT-3 first flight March 2021. First firing test April 2021. First mass-produced flight test May 2021. Delivered to Türkiye August 2021. Over 60 units built. Surpassed 100,000 flight hours by March 2025. Air-to-air firing test with EREN loitering munition February 2026. Inducted into Turkish Land Forces service April 2026. In service with Turkish Air Force, Turkish Land Forces, Turkish Navy, and multiple export customers.

**Open issues** — EREN air-to-air capability operational validation. Export control and ITAR restrictions for certain munitions. Integration with non-NATO command and control systems. Production scaling to meet export demand.

**Changelog** — Akıncı A: initial production configuration with 450 HP engines. Akıncı B: 750 HP engines. Akıncı C: 850 HP engines and expanded payload options. EREN loitering munition integration (2026). Air-to-air missile trials (2026).

**Lessons learned** — The dual AI avionics architecture provides enhanced situational awareness and diagnostic functions, improving mission effectiveness and flight safety. The triple-redundant autopilot and cross-redundant YKI system provide the fault tolerance required for 24+ hour missions over contested territory. The 1,500 kg payload capacity across five hardpoints allows the aircraft to carry a wider range of munitions than any other drone in its class, enabling air-to-ground and air-to-air missions from a single platform. The fully automatic takeoff and landing capability reduces the ground crew workload and enables operations from austere runways.

**Cost actual** — Not publicly disclosed. The Akıncı is positioned as a cost-effective alternative to fighter jets for ISR and strike missions. Unit cost is expected to be a fraction of a modern fighter aircraft. Export pricing varies by configuration, munitions, and quantity.

---

## Status

**Condition** — operational. In service with Turkish Air Force, Turkish Land Forces, Turkish Navy, and multiple export customers.

**Blockers** — None. Active production and export.

**Next steps** — EREN air-to-air capability operational deployment. Integration with additional munitions (SOM-A, Gokdogan, Bozdogan). Continued export campaigns. Production scaling to meet demand. Development of successor platforms (Bayraktar TB3, Kızılelma).

---

**Note on this Shell:** The akinci is a distinct class in the library: a strategic-class MALE UCAV designed for missions traditionally performed by fighter jets. Unlike the evo-le (tactical ISTAR UAS), the seaguardian (maritime HALE RPAS), or the raybird (deep-reconnaissance tactical UAS), the Akıncı is a multirole combat aircraft with a 1,500 kg payload across five hardpoints, capable of air-to-ground strike, air-to-air engagement, electronic warfare, and persistent surveillance. Its twin turboprop engines provide redundancy and sufficient thrust for the 6,000 kg MTOW. The dual AI avionics and triple-redundant autopilot provide the fault tolerance required for 24+ hour missions. The Ground Control Station is a NATO-spec ACE-III shelter with NBC filtration, indicating the system is designed for operations in contaminated environments. With over 60 units built, 100,000+ flight hours, and service with multiple nations, the Akıncı is the reference for a Turkish strategic UCAV that has redefined the MALE drone class.
