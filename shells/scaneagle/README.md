# scaneagle

**Class:** aerial (Group 2 fixed-wing UAS)  
**Generation:** 1  
**Version:** 3.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Insitu (a Boeing Company)  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Small, long-endurance fixed-wing unmanned aircraft system designed for persistent maritime and land-based ISR (Intelligence, Surveillance, Reconnaissance). The ScanEagle is not a strategic asset; it is a **tactical, shipboard and expeditionary ISR platform** that two operators can launch from a ship deck or austere site using either a rail catapult or a vertical take-off and landing kit, leave airborne for 18+ hours, and recover without a runway. Its defining characteristics are **heavy-fuel endurance** (JP-5/JP-8, 18+ hours), **FLARES no-sacrifice VTOL** (vertical launch and recovery without reducing endurance or payload), and **resilient autonomy** in GPS-contested and communications-denied environments. It is the UAS that invented the agile ISR category, with over 1.6 million combat flight hours, more than 45 ship classes operated from, and service with 35+ international militaries. It is the reference platform for small, shipboard, long-endurance ISR.

**Environment** — Outdoor, maritime, and expeditionary operations. All-weather, day and night. Designed for shipboard deployment (from frigate to carrier decks) and austere land sites. Operating altitude up to 19,500 ft. Endurance 18+ hours. Temperature range −20 °C to +45 °C (FLARES VTOL kit). Wind range 0–30 knots with 10-knot gusts for VTOL operations. Not for operations in icing conditions or severe turbulence without additional protection.

**Mission** — Persistent maritime domain awareness, shipboard ISR, route monitoring, force protection, search and rescue, drug interdiction, border security, and ISR-T (Intelligence, Surveillance, Reconnaissance, and Targeting). The ScanEagle carries a modular payload suite including EO/IR, synthetic aperture radar (SAR), passive wide-area maritime search (AI-assisted), AIS, signals intelligence (SIGINT), electronic warfare (EW), communications relay, and laser designator targeting. It is designed for expeditionary operations from land or maritime platforms using the FLARES vertical take-off and landing kit or traditional rail launch and SkyHook recovery.

**Operator** — Two operators for launch and recovery. Single operator for flight control via ground control station. The ScanEagle is available with both traditional rail launch/Skyhook recovery and the FLARES Vertical Take-off and Landing kit. VTOL setup and launch in 30 minutes with only two operators, no aircraft modifications required. The aircraft packs into a 463L pallet for transport downrange.

**Reusability** — Commercial defence platform with active production and global service. Over 1.6 million combat flight hours. Operated from over 45 ship classes and land sites on six continents. Service with 35+ international militaries. Insitu provides Contractor-Owned, Contractor-Operated (COCO) ISR services to the US Navy since 2005 and US Marine Corps since 2004.

---

## Spec

**Physical** — Length 5.6 ft (1.71 m). Wingspan 10.2 ft (3.1 m). Maximum take-off weight 62 lb (28 kg). Maximum payload weight 17 lb (7.7 kg). On-board power up to 170 W for payload. The airframe is constructed from lightweight composite materials optimised for shipboard operations and long-endurance cruise. The FLARES VTOL kit is an electric battery-powered multicopter that provides vertical launch and recovery without aircraft modifications. The full mission set packs into a 463L pallet (108 × 88 × 62 in / 2.74 × 2.24 × 1.57 m).

**Kinematic** — Fixed-wing configuration with optional VTOL kit. Traditional launch is by pneumatic rail catapult; recovery is by SkyHook vertical wire capture. The FLARES VTOL kit eliminates the need for launch and recovery equipment: FLARES mates with the ScanEagle, climbs vertically to 500 ft AGL, dashes into the wind, and releases the ScanEagle into fixed-wing flight in under five minutes. FLARES then returns to land. Recovery: FLARES takes off vertically tethered, hosting a capture rope into the air at approximately 300 ft. The ScanEagle catches on the vertical line via a wing hook in under five minutes, and FLARES descends as the capture rope is wheeled onto a winch in the Mast Augmented Recovery System (MARS). The ScanEagle settles onto the top of the mast, and the unloaded FLARES lands.

**Dynamic** — Endurance 18+ hours. Ceiling 19,500 ft (5,950 m). Maximum horizontal speed 80 knots (41.2 m/s). Cruise speed 50–60 knots (25–30 m/s). Engine: heavy fuel (JP-5 or JP-8) or C-10 gasoline. The heavy-fuel engine is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. The 18+ hour endurance enables day-to-night ISR and targeting. PLEO SATCOM enables enhanced over-the-horizon operations.

**Power** — Single heavy-fuel engine (JP-5/JP-8) or C-10 gasoline engine. On-board power up to 170 W for payload. The FLARES VTOL kit is electric battery-powered. The heavy-fuel engine provides the endurance and logistics commonality required for shipboard operations. The aircraft has been certified by US and foreign military customers for flight operations.

**Thermal** — Passive cooling. The engine is air-cooled with a ram-air intake. The FLARES VTOL kit uses electric motors cooled by rotor wash. The aircraft's low thermal signature reduces detectability by infrared sensors compared to larger platforms. The heavy-fuel engine has a lower fire hazard than gasoline-powered engines, which is critical for shipboard operations.

**Environmental** — Designed for maritime and expeditionary operations. Battle-tested in extreme environments from the tropics to the Arctic. Award-winning mission readiness rate. Not rated for icing conditions without additional protection. The composite airframe is resistant to salt spray and UV degradation. The FLARES VTOL kit operates in temperatures from −20 °C to +45 °C and wind ranges of 0–30 knots with 10-knot gusts.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The ScanEagle is purchased as a complete system with ground control station, launch and recovery equipment, and modular payload integration.

| Component | Notes |
|:---|:---|
| ScanEagle airframe | Composite construction, 1.71 m length, 3.1 m wingspan, 28 kg MTOW |
| Heavy-fuel engine | JP-5/JP-8 or C-10 gasoline, 18+ hours endurance |
| FLARES VTOL kit | Electric battery-powered multicopter for vertical launch and recovery |
| SkyHook recovery system | Vertical wire capture for traditional recovery |
| Pneumatic rail launcher | Traditional launch from ship deck or land site |
| MARS (Mast Augmented Recovery System) | Winch-based recovery for FLARES operations |
| PLEO SATCOM | Proliferated Low-Earth Orbit satellite communication for beyond-line-of-sight control |
| Modular payload bay | 17 lb (7.7 kg) capacity, up to 170 W power |
| EO/IR sensor payload | Electro-optical camera and telescope, medium-wave infrared |
| SAR payload | Synthetic aperture radar: MMTI/GMTI, CCD |
| Passive wide-area maritime search | AI-assisted |
| AIS | Maritime vessel identification |
| Laser designator | STANAG-3733-compliant laser designator and pointer |
| SIGINT/EW payload | Signals intelligence and electronic warfare |
| Communications relay | Comms relay for network extension |
| Ground control station | Operator interface for mission command and payload control |

**Structure** — Lightweight composite airframe with a high aspect ratio wing for efficient cruise and long endurance. The fuselage houses the engine, fuel, avionics, and payload bay. The aircraft is designed for shipboard operations, with the FLARES VTOL kit providing vertical launch and recovery without aircraft modifications. The open architecture enables rapid integration with third-party mission and battle-management systems. Onboard autonomy includes automatic target recognition trained on decades of computer vision expertise and detect-and-advise functionality.

**Actuation** — Single heavy-fuel engine driving a pusher propeller. Control surfaces actuated by electromechanical actuators. The FLARES VTOL kit uses electric motors for vertical flight. The flight control system manages the transition between VTOL and forward flight automatically. The aircraft has been operating in GPS-contested and denied environments since 2018, with visual-based navigation and resilient datalinks.

**Locomotion** — Fixed-wing flight with optional VTOL capability. Traditional launch by pneumatic rail catapult; recovery by SkyHook vertical wire capture. FLARES VTOL kit provides vertical launch and recovery from confined spaces without launch or recovery equipment. The FLARES kit preserves full UAV endurance, payload capacity, and range; it is a no-sacrifice VTOL solution. Cruise speed 50–60 knots, maximum speed 80 knots.

**Manipulation** — None. The aircraft is a sensor and electronic warfare platform. The payload is the effector: EO/IR cameras, SAR, AIS, SIGINT/EW systems, communications relay, or laser designator for targeting. The modular payload bay allows rapid reconfiguration for different mission profiles.

**Power system** — Single heavy-fuel engine (JP-5/JP-8) or C-10 gasoline engine. On-board power up to 170 W for payload. The FLARES VTOL kit is electric battery-powered. The heavy-fuel engine provides 18+ hours of endurance and logistics commonality with US Navy ships. The aircraft has been certified by US and foreign military customers for flight operations.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The open architecture enables rapid integration with third-party mission and battle-management systems. PLEO SATCOM and resilient datalinks provide beyond-line-of-sight control and communication in degraded environments.

**Custom parts** — None. All components are Insitu proprietary or certified third-party. The modular payload bay and open architecture enable rapid integration of custom payloads. The FLARES VTOL kit requires no aircraft modifications.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid deployment and recovery by a two-person team, with modular components for field assembly and maintenance.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The aircraft assembles and launches in 30 minutes with two operators using the FLARES VTOL kit.

---

## Systems

**Manifest** — Insitu proprietary software stack with resilient autonomy and PLEO SATCOM integration.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation, including automatic VTOL launch and recovery, transition to forward flight, cruise, and recovery. The aircraft has been operating in GPS-contested and denied environments since 2018, with visual-based navigation and autonomous switching of frequency channels and bands for resilient communications. Onboard autonomy includes automatic target recognition trained on decades of computer vision expertise and detect-and-advise functionality.

**Middleware** — Insitu proprietary. PLEO SATCOM enables operators to control ScanEagle from global locations and extend mission range using satellite constellations rather than traditional line-of-sight communications. The system includes autonomous radio-frequency switching and visual navigation features to maintain operation in limited or degraded communications environments. The open architecture enables rapid integration with third-party mission and battle-management systems.

**Perception** — Modular payload suite with 17 lb (7.7 kg) capacity and up to 170 W power:
- **EO/IR**: Electro-optical camera and telescope, medium-wave infrared and EO for day-to-night operations.
- **SAR**: Synthetic aperture radar with MMTI/GMTI and CCD modes.
- **Passive wide-area maritime search**: AI-assisted.
- **AIS**: Maritime vessel identification.
- **Laser designator**: STANAG-3733-compliant laser designator and pointer for advanced targeting support.
- **SIGINT/EW**: Signals intelligence and electronic warfare.
- **Communications relay**: Comms relay for network extension.
- **Visual-based navigation**: For GPS-denied environments.

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft handles VTOL launch, transition to forward flight, navigation, station-keeping, and recovery autonomously. The PLEO SATCOM enables beyond-line-of-sight control from global locations. The aircraft has been operating in GPS-contested and denied environments since 2018, with resilient autonomy that maintains operation in degraded communications environments.

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The aircraft can be retasked in flight. The FLARES VTOL kit allows launch and recovery from confined locations, enabling operations from ships, rooftops, and austere clearings without runway infrastructure.

**Learning** — Onboard autonomy includes automatic target recognition trained on decades of computer vision expertise and detect-and-advise functionality. The AI-assisted wide-area maritime search capability is a form of learning-based perception, though the specific architecture is not publicly disclosed. The autonomy is designed for reliability and predictability in safety-critical operations.

**Teleoperation** — Two operators for launch and recovery, single operator for flight control via ground control station. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and VTOL transitions autonomously. PLEO SATCOM provides beyond-line-of-sight control. The ground control station integrates with third-party mission and battle-management systems through the open architecture.

**Safety** — The aircraft has been operating in GPS-contested and denied environments since 2018, with visual-based navigation and resilient datalinks. The FLARES VTOL kit eliminates the risk of launch or recovery failures associated with rail catapults and SkyHook systems in high sea states. The heavy-fuel engine reduces fire hazard compared to gasoline-powered engines. The aircraft has an award-winning mission readiness rate and has been battle-tested in extreme environments from the tropics to the Arctic.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The aircraft has accumulated over 1.6 million combat flight hours. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — PLEO SATCOM for beyond-line-of-sight control. Resilient datalinks with autonomous switching of frequency channels and bands for operation in degraded communications environments. The aircraft can carry communications relay payloads for network extension. The open architecture enables integration with third-party mission and battle-management systems.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the ground control station.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — Insitu ground control station software. Resilient autonomy stack. PLEO SATCOM integration. Payload-specific software (EO/IR, SAR, SIGINT, EW, laser designator). Third-party battle-management systems (via open architecture).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Insitu flight control | Proprietary | Insitu | Control/Flight |
| Resilient autonomy | Proprietary | Insitu | Autonomy/Resilience |
| PLEO SATCOM integration | Proprietary | Insitu | Comms/SATCOM |
| Ground control station | Proprietary | Insitu | GCS |
| Payload integration software | Proprietary | Various | Payload/Integration |
| Battle-management system interface | Open architecture | Insitu | Command/Control |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, fuel state, engine status, system health. Sensor data: EO/IR imagery, SAR imagery, AIS tracks, SIGINT/EW data, laser designation status. Network data: PLEO SATCOM link status, datalink status, relay node status.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Laser designation commands. VTOL launch and recovery commands.

**Serves** — Persistent ISR services. Maritime domain awareness. Search and rescue. Target acquisition and tracking. Communications relay. Electronic warfare. Laser designation for precision targeting.

**Executes** — Autonomous VTOL launch, transition to forward flight, persistent ISR over a local or regional area, maritime surveillance, signals intelligence collection, laser designation, autonomous recovery. Return-to-base in comms-denied environment.

**Extensions** — Modular payload bay (17 lb capacity, 170 W power). EO/IR, SAR, AIS, SIGINT/EW, communications relay, laser designator payloads. PLEO SATCOM for beyond-line-of-sight control. FLARES VTOL kit for vertical launch and recovery. Open architecture for third-party battle-management systems.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL.

**Units** — SI and aviation standard. Metres, feet, knots, kilometres, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR, SAR, AIS, and SIGINT/EW payloads. Flight control system calibrated for fixed-wing flight and FLARES VTOL transition. PLEO SATCOM calibrated for beyond-line-of-sight control.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and autonomy. The high aspect ratio wing provides efficient cruise and long endurance. The heavy-fuel engine provides sufficient thrust for the 28 kg MTOW and the 7.7 kg payload. The FLARES VTOL kit adds vertical launch and recovery capability without modifying the aircraft or reducing endurance, payload, or range.

**Sensor transforms** — Payload sensors mounted in the modular payload bay. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of engine, FLARES VTOL kit, flight control system, and payloads.

**Integration** — Payload integration in the modular bay. Flight control system verification. PLEO SATCOM integration. FLARES VTOL kit verification. Resilient autonomy verification in GPS-denied environments.

**Field** — Over 1.6 million combat flight hours. Operated from over 45 ship classes and land sites on six continents. Service with 35+ international militaries. US Navy ISR services since 2005. US Marine Corps ISR services since 2004. Brazilian Navy first launch (2022). Colombian Navy maritime surveillance (2025). Japanese and US joint nighttime drone drill (2026). Spanish Navy ViDAR integration (2026). NATO exercises. Extreme environment operations from the tropics to the Arctic.

**Endurance** — 18+ hours with 17 lb payload. Day-to-night ISR and targeting. PLEO SATCOM for over-the-horizon missions.

**Environmental** — Battle-tested in extreme environments from the tropics to the Arctic. Shipboard operations from frigate to carrier decks. Not for icing conditions without additional protection. FLARES VTOL kit operates in temperatures from −20 °C to +45 °C and wind ranges of 0–30 knots with 10-knot gusts.

**Known limitations** — The ScanEagle is a Group 2 UAS with a 17 lb payload capacity; it cannot carry large sensors or heavy weapons. The 18+ hour endurance is impressive but limited compared to larger MALE/HALE platforms. The heavy-fuel engine requires JP-5 or JP-8, which is available on US Navy ships but may not be available in all austere environments. The FLARES VTOL kit adds weight and complexity but preserves full endurance, payload, and range. The aircraft is not stealth; it relies on altitude, low acoustic and thermal signatures, and resilient autonomy for survivability in contested airspace.

---

## Log

**Build history** — ScanEagle developed by Insitu (a Boeing Company). Over 1.6 million combat flight hours. The UAS that invented the agile ISR category. Operated from over 45 ship classes and land sites on six continents. Service with 35+ international militaries. US Navy ISR services since 2005. US Marine Corps since 2004. PLEO SATCOM and laser-designation payload introduced November 2025. Selected by US Navy for continued ISR services under COCO model May 2026.

**Open issues** — Expansion of payload options (SAR, SIGINT, EW). Integration with emerging battle-management systems. PLEO SATCOM integration for beyond-line-of-sight control. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — ScanEagle: 18+ hours endurance, 17 lb payload, heavy-fuel engine, FLARES VTOL kit. PLEO SATCOM: introduced November 2025. Laser designator: STANAG-3733-compliant, introduced November 2025. AI-assisted wide-area maritime search: introduced 2024. ViDAR integration: Spanish Navy, 2026.

**Lessons learned** — The FLARES no-sacrifice VTOL kit is the key enabler of expeditionary operations from confined spaces without launch or recovery equipment. The heavy-fuel engine provides logistics commonality with US Navy ships and 18+ hours of endurance. Resilient autonomy in GPS-contested and denied environments is critical for operations against peer adversaries. The open architecture enables rapid integration with third-party mission and battle-management systems. PLEO SATCOM enables beyond-line-of-sight control from global locations. The aircraft's low acoustic signature and long endurance make it effective for persistent maritime surveillance. Over 1.6 million combat flight hours and service with 35+ international militaries validate the platform's reliability and effectiveness.

**Cost actual** — Not publicly disclosed. Insitu provides Contractor-Owned, Contractor-Operated (COCO) ISR services to the US Navy and US Marine Corps. Unit cost varies by configuration, payload, and quantity. The ScanEagle is positioned as a cost-effective, attritable ISR asset for tactical and maritime operations.

---

## Status

**Condition** — operational. Fielded with 35+ international militaries. US Navy ISR services since 2005. US Marine Corps since 2004. Over 1.6 million combat flight hours.

**Blockers** — None. Active production and global service.

**Next steps** — Integration of PLEO SATCOM and laser-designation payload for ISR-T missions. Expansion of AI-assisted maritime search capabilities. Continued service with US Navy, US Marine Corps, and international customers. Production scaling to meet demand. Integration with emerging battle-management systems.

---

**Note on this Shell:** The scaneagle is a distinct class in the library: a Group 2 fixed-wing UAS designed for **shipboard and expeditionary ISR** with 18+ hours of endurance and a 17 lb modular payload capacity. Unlike the v-bat (ducted-fan, heavy-fuel, 13-hour endurance, Group 3) or the stalker (hybrid VTOL, propane fuel cell, 8+ hours, Group 2), the ScanEagle is a conventional fixed-wing aircraft that has been adapted for vertical launch and recovery through the FLARES no-sacrifice VTOL kit. Its heavy-fuel engine (JP-5/JP-8) is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. The PLEO SATCOM and laser-designation payload upgrades (November 2025) enable beyond-line-of-sight ISR-T missions from global locations. With over 1.6 million combat flight hours, service with 35+ international militaries, and operations from more than 45 ship classes and land sites on six continents, the ScanEagle is the reference for a mature, battle-proven, shipboard-capable, long-endurance ISR platform.
