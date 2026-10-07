# raybird

**Class:** aerial (tactical fixed-wing ISR UAS)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Skyeton  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Long-endurance tactical fixed-wing unmanned aircraft system for deep reconnaissance, signals intelligence, and battlefield surveillance. The Raybird is a modular platform that can switch roles in the field: it functions as an FPV strike drone mothership, provides laser targeting, deploys ELINT/RF locators for tracking enemy emitters, and utilises synthetic aperture radar for imaging in poor weather. It is designed to operate deep behind enemy lines, providing persistent intelligence that has helped destroy billions of dollars' worth of Russian military equipment during the war in Ukraine. The US Army awarded Skyeton a $10.64 million firm-fixed-price contract for Raybird UAS hardware and services in September 2026. 

**Environment** — Outdoor, all-weather, day and night operations. Designed for contested electronic warfare environments with resistance to GNSS jamming. Operating altitude up to 21,000 ft launch altitude and 27,000 ft service ceiling. Endurance up to 24–28 hours. Not for indoor flight. The aircraft is designed for expeditionary deployment from austere locations with minimal launch infrastructure.

**Mission** — Deep reconnaissance, battlefield surveillance, target acquisition, laser designation, signals intelligence (ELINT/RF locating), synthetic aperture radar imaging, and FPV strike drone mothership operations. The Raybird has accrued over 350,000 combat hours in Ukraine and is claimed to provide intelligence that has enabled strikes on high-value Russian targets. 

**Operator** — Small crew for launch and recovery. Single operator for flight control via ground control station. The aircraft is catapult-launched and recovered by parachute or deep-stall landing, requiring no runway. The modular payload bay allows rapid reconfiguration in the field.

**Reusability** — Commercial defence platform with battlefield-proven modularity. The aircraft is designed for rapid role-switching in the field without returning to depot. Open architecture enables integration of sovereign payloads. Production is expanding to the UK through a joint venture with Prevail Partners, and the system has been offered as a potential successor to the British Army's Watchkeeper WK45. 

---

## Spec

**Physical** — Wingspan 2.96 to 4.2 m (variable depending on configuration). Maximum take-off weight 23 kg (50 lbs). The airframe is constructed from composite materials for high strength-to-weight ratio. The modular design enables different wing configurations for different mission profiles. 

**Kinematic** — Fixed-wing configuration optimised for long-endurance cruise. The aircraft is catapult-launched from a pneumatic or bungee launcher and recovered by parachute or deep-stall landing, eliminating the need for runways or arresting gear. Control surfaces: ailerons, elevator, rudder. The airframe is designed for efficient cruise at low speed, maximising endurance.

**Dynamic** — Maximum flight endurance up to 24 hours (ICE version: 28+ hours). Maximum flight range 2,500 km (1,550+ miles). Data link range 200+ km (125+ miles). Maximum speed 140 km/h. Cruise speed approximately 110 km/h. The aircraft is designed for persistent surveillance over vast distances, with the ability to loiter on station for extended periods. 

**Power** — Internal combustion engine (ICE) version for maximum endurance, or hybrid-electric/hydrogen fuel cell for reduced thermal signature. The hydrogen-powered variant has been deployed in combat, offering a "negligible" thermal signature. The ICE version achieves 28+ hours endurance; the hydrogen version trades some endurance (12 hours) for stealth. 

**Thermal** — The hydrogen fuel cell variant produces a negligible thermal signature, making it significantly harder to detect by infrared sensors than conventional internal combustion engines. The ICE version has a conventional thermal signature mitigated by exhaust routing and engine shielding. 

**Environmental** — Designed for operation in contested electronic warfare environments with resistance to GNSS jamming through high autonomy. Operating temperature range not publicly specified, but the aircraft is deployed in all seasons in Ukraine. The composite airframe is resistant to environmental degradation.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Raybird is purchased as a complete system with ground control station, launcher, and modular payloads.

| Component | Notes |
|:---|:---|
| Raybird airframe | Composite construction, 2.96–4.2 m wingspan, 23 kg MTOW |
| Internal combustion engine (ICE version) | Endurance 28+ hours |
| Hydrogen fuel cell (hybrid version) | Endurance 12 hours, negligible thermal signature |
| Modular payload bay | 5–10 kg payload capacity |
| EO/IR sensor payload | Stabilised day/night imaging |
| Synthetic aperture radar (SAR) | All-weather imaging |
| ELINT/RF locator | Signals intelligence and emitter tracking |
| Laser designator | Target designation for precision munitions |
| FPV mothership module | Carries and releases FPV strike drones |
| Ground control station | Ruggedized laptop or tablet with Skyeton GCS software |
| Pneumatic launcher | Catapult launch from austere locations |
| Parachute recovery system | Deep-stall landing or parachute recovery |
| SATCOM module | Beyond-line-of-sight control |

**Structure** — Composite airframe with modular wings and payload bay. The wingspan is configurable from 2.96 to 4.2 m depending on mission requirements. The fuselage houses the engine, fuel, avionics, and payload bay. The modular design enables rapid role-switching in the field: the same airframe can be configured as an ISR platform, an ELINT collector, a SAR imaging platform, a laser designator, or an FPV mothership. The aircraft is designed for expeditionary deployment from a single transit case, reducing the logistics footprint. 

**Actuation** — Internal combustion engine driving a pusher propeller (ICE version), or hydrogen fuel cell powering an electric motor (hydrogen version). Control surfaces actuated by digital servos. The hydrogen variant uses a fuel cell to generate electricity, which powers the electric motor and avionics, producing only water vapour as exhaust. 

**Locomotion** — Fixed-wing flight. Catapult launch, parachute or deep-stall recovery. The aircraft cruises at approximately 110 km/h, optimised for endurance rather than speed. 

**Manipulation** — None. The payloads are sensors and electronic warfare systems. The FPV mothership module releases small strike drones, but the Raybird itself does not manipulate objects.

**Power system** — Internal combustion engine (ICE) for maximum endurance, or hydrogen fuel cell for reduced thermal signature. The ICE version carries sufficient fuel for 28+ hours of flight. The hydrogen version carries compressed hydrogen gas and a fuel cell stack, trading endurance for stealth. Power distribution includes redundant buses for flight-critical avionics and payloads. 

**Wiring** — Internal only. Not user-accessible. Payload integration via standardized connector in the modular payload bay. The open architecture enables integration of third-party sensors and electronic warfare payloads. 

**Custom parts** — None. All components are Skyeton proprietary or certified third-party. Payloads mount in the modular payload bay. 

**Fasteners** — Proprietary. Not user-serviceable. 

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The system is designed for rapid deployment by a small crew.

---

## Systems

**Manifest** — Skyeton proprietary software stack with modular payload integration. The aircraft uses high autonomy for GNSS-denied navigation, enabling continued operation in contested electronic warfare environments. 

**Firmware** — The flight controller runs a proprietary autopilot with GNSS-denied navigation capability. The aircraft can operate with high autonomy, meaning it can complete missions without continuous GNSS or operator input. This is critical for operations in contested electronic warfare environments where GNSS jamming and spoofing are prevalent. 

**Middleware** — Proprietary. The aircraft communicates via line-of-sight data link (200+ km range) and SATCOM for beyond-line-of-sight operations. The open architecture enables integration with third-party command and control systems. 

**Perception** — Modular sensor suite:
- **EO/IR sensor**: Stabilised day/night imaging with high-resolution cameras and thermal infrared.
- **Synthetic Aperture Radar (SAR)**: All-weather imaging through clouds, smoke, and darkness.
- **ELINT/RF locator**: Detects and geolocates enemy emitters (radars, radios, jammers).
- **Laser designator**: Designates targets for precision-guided munitions.
- **FPV mothership**: Carries and releases small FPV strike drones for one-way attack missions. 

**Control** — The autopilot manages navigation, GNSS-denied operation, and mission execution. The operator provides high-level commands (waypoints, search patterns, sensor tasking) and monitors the sensor feed. The aircraft has high autonomy, meaning it can adapt to changing conditions and complete missions with minimal operator intervention. 

**Planning** — Autonomous waypoint navigation with pre-programmed search patterns. The aircraft can loiter on station, perform grid searches, and execute deep-penetration missions. Mission planning includes sensor tasking, route planning, and electronic warfare threat avoidance. 

**Learning** — None in the base platform. The aircraft uses classical control and signal processing. Optional: onboard AI processing for automated target recognition can be added via a companion processor. 

**Teleoperation** — Single operator via ground control station. The operator commands waypoints or direct flight, monitors sensor feeds, and manages payloads. Data link range 200+ km, with SATCOM for beyond-line-of-sight. 

**Safety** — The aircraft has high autonomy for GNSS-denied operations, reducing the risk of loss in contested environments. The parachute recovery system enables safe recovery even in the event of engine failure. The aircraft is designed for operation in contested electronic warfare environments, with resistance to jamming and spoofing. 

**Logging** — Flight data and sensor data are logged onboard and transmitted to the ground control station. Data includes aircraft telemetry, sensor imagery, radar tracks, and ELINT data. 

**Networking** — Line-of-sight data link (200+ km) and SATCOM for beyond-line-of-sight operations. Optional 4G/LTE for operations in areas with cellular coverage. 

**Config files** — Proprietary. No user-accessible config files. 

**Launch files** — N/A (proprietary defence software). 

**Dependencies** — Skyeton ground control station software. Mission planning software. Payload software (EO/IR, SAR, ELINT, laser designator). 

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Skyeton flight control | Proprietary | Skyeton | Control/Flight |
| EO/IR software | Proprietary | Various | Sensors/EOIR |
| SAR software | Proprietary | Various | Sensors/SAR |
| ELINT software | Proprietary | Various | Sensors/ELINT |
| Laser designator software | Proprietary | Various | Sensors/Laser |
| GNSS-denied navigation | Proprietary | Skyeton | Navigation/GNSS-Denied |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, airspeed, altitude, fuel state, system health. Sensor data: EO/IR imagery, SAR imagery, ELINT data, laser designation status. 

**Accepts** — Navigation commands (waypoints, routes, search patterns). Sensor tasking commands. Payload commands. Laser designation commands. 

**Serves** — Mission planning, sensor tasking, data exploitation. 

**Executes** — Autonomous navigation, GNSS-denied navigation, deep-penetration missions, search patterns, laser designation, ELINT collection, FPV mothership operations. 

**Extensions** — Modular payload bay for interchangeable sensors. FPV mothership module. Additional electronic warfare payloads. 

**Frame conventions** — Military grid reference system (MGRS) for position. NED for navigation. FRD for body. Airspeed in km/h. Altitude in feet MSL. 

**Units** — SI and military standard. Meters, kilometres, kilometres per hour, feet, kilograms. 

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform). 

**SDF** — Not applicable. 

**Calibration** — Factory calibrated. Sensor calibration for EO/IR, SAR, ELINT, and laser designator. 

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and simulation. The high aspect ratio wing provides efficient cruise and long endurance. 

**Sensor transforms** — EO/IR, SAR, and ELINT sensors are mounted at optimised locations in the payload bay. 

**Collision geometry** — Proprietary. 

**Visual geometry** — Proprietary. 

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery. 

**Integration** — Payload integration in the modular payload bay. Sensor calibration and verification. GNSS-denied navigation verification. Data link range verification. 

**Field** — Endurance test: 24–28 hour flight. Range test: 2,500 km. GNSS-denied navigation test. ELINT collection test. SAR imaging test. Laser designation test. FPV mothership operation test. Combat deployment in Ukraine: 350,000+ combat hours. 

**Endurance** — Maximum endurance 24 hours (hydrogen version: 12 hours). Maximum range 2,500 km. 

**Environmental** — All-weather operations. Deployed in all seasons in Ukraine. Contested electronic warfare environments. 

**Known limitations** — The aircraft is not stealth; it relies on altitude, endurance, and electronic warfare resistance for survivability. The hydrogen version has reduced endurance (12 hours vs. 28 hours) but negligible thermal signature. The modular payload bay has a 5–10 kg capacity, limiting the size and complexity of individual sensor packages. The aircraft requires a catapult launcher and recovery system, which adds logistics footprint compared to VTOL platforms. GNSS-denied navigation depends on the aircraft's high autonomy; without it, the aircraft would be vulnerable to jamming. 

---

## Log

**Build history** — Raybird developed by Skyeton (Ukraine). Combat-proven in Ukraine with over 350,000 combat hours. US Army awarded $10.64 million contract for Raybird UAS hardware and services in September 2026. Production expanding to the UK through joint venture with Prevail Partners. Offered as potential successor to British Army Watchkeeper WK45. Considered for F-35 loyal wingman role. 

**Open issues** — Export control and ITAR restrictions. Integration with non-NATO command and control systems. Hydrogen fuel cell logistics in austere environments. Production scaling to meet international demand. 

**Changelog** — Raybird ICE version: 28+ hours endurance. Hydrogen version: 12 hours endurance, negligible thermal signature. SATCOM module added for beyond-line-of-sight control. Modular payload bay: EO/IR, SAR, ELINT, laser designator, FPV mothership. 

**Lessons learned** — Modularity is critical for battlefield adaptability; the Raybird can switch roles in the field without returning to depot. GNSS-denied navigation is essential for operations in contested electronic warfare environments. Endurance of 24–28 hours provides persistent coverage that reduces the number of aircraft required for continuous surveillance. Combat-proven performance in Ukraine has driven international demand. 

**Cost actual** — US Army contract: $10.64 million for an undisclosed quantity of Raybird UAS hardware and services. Unit cost varies by configuration, payload, and quantity. 

---

## Status

**Condition** — operational. Fielded with Ukrainian forces and ordered by the US Army. 

**Blockers** — None. Combat-proven defence product with active procurement. 

**Next steps** — Integration with emerging payloads (electronic warfare, SIGINT). Expansion of production to the UK. Continued delivery to international customers. Development of additional mission kits for maritime and littoral operations. 

---

**Note on this Shell:** The raybird is a distinct class in the library: a long-endurance tactical fixed-wing ISR UAS designed for deep reconnaissance in contested electronic warfare environments. Unlike the evo-le (VTOL fixed-wing with 8-hour endurance) or the seaguardian (MALE/HALE maritime RPAS with 40-hour endurance), the Raybird is optimised for battlefield reconnaissance at the tactical and operational level, with a 24–28 hour endurance, 2,500 km range, and modular payload bay that can be reconfigured in the field. Its GNSS-denied navigation and resistance to electronic warfare are critical for operations against peer adversaries. The hydrogen variant offers a negligible thermal signature, making it harder to detect by infrared sensors. With 350,000+ combat hours in Ukraine and a US Army contract, the Raybird is the reference for a combat-proven, long-endurance tactical ISR drone with modular payloads and GNSS-denied operation.
