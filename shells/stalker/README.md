# stalker

**Class:** aerial (Group 2 VTOL fixed-wing UAS)  
**Generation:** 1  
**Version:** 5.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Edge Autonomy (Redwire)  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Small, hybrid VTOL fixed-wing unmanned aircraft system designed for long-endurance ISR (Intelligence, Surveillance, Reconnaissance) in austere and contested environments. The Stalker is not a strategic asset; it is a **tactical, expeditionary ISR platform** that a two-person team can pull from a case, assemble in ten minutes, launch vertically from a rooftop or clearing, and leave airborne for over eight hours — or, in record configuration, nearly forty. Its defining characteristics are **hybrid VTOL** (vertical take-off with rotors, forward flight as a fixed-wing aircraft), **propane fuel cell endurance** (8+ hours standard, 39+ hours record), and **low acoustic signature** that allows it to operate undetected at low altitude where larger drones cannot.

**Environment** — Outdoor, expeditionary, all-weather. Deployed from rooftops, vehicle decks, and confined clearings without runways, catapults, or launch gear. Operating altitude up to 15,000 ft. Endurance 8+ hours standard on fuel cell, 4 hours on battery, 2 hours in VTOL battery mode. Not for operations in icing conditions or severe turbulence without additional protection. Designed for austere locations where infrastructure is minimal and support personnel are few.

**Mission** — Persistent local ISR, route monitoring, force protection, overwatch, and signals intelligence collection. The Stalker’s low acoustic signature and ability to fly low and undetected make it more effective than high-flying platforms for gathering fine-grained intelligence at close range. A Stalker with a quality imager operating undetected a couple of hundred meters away can surpass what can be gathered from a Reaper-type platform at 10,000 feet. This applies even more to signals intelligence equipment detecting and hacking signals like Wi-Fi on the ground.

**Operator** — Two-person team. The aircraft weighs around 50 pounds, assembles and flies in ten minutes, and requires no infrastructure. A single operator can control the aircraft from a ground control station; a second person assists with launch and recovery.

**Reusability** — Commercial defence platform with active production and export. The Stalker VXE has been operationally proven, and the Block 30 variant is in service with the U.S. Marine Corps and other allied forces. Redwire has received follow-on orders from the U.S. Navy and Marine Corps, including $20 million in contracts for Stalker drones.

---

## Spec

**Physical** — Wingspan 4.9 m (16 ft). Length approximately 3 m (10 ft). Maximum take-off weight 22 kg (49 lbs) with battery or fuel cell configuration. Payload capacity up to 2.5 kg (5.5 lbs). The airframe is constructed from lightweight composite materials optimised for low acoustic signature and aerodynamic efficiency. The VTOL configuration adds rotor arms for vertical launch and recovery without a runway.

**Kinematic** — Hybrid VTOL fixed-wing. Vertical take-off and landing using electric rotors, transition to forward flight using a pusher propeller. The aircraft flies as a conventional fixed-wing aircraft during cruise. The VTOL capability eliminates the need for runways, catapults, or launch gear, enabling deployment from rooftops, vehicle decks, and confined clearings. The flight control system manages the transition between hover and forward flight automatically.

**Dynamic** — Endurance 8+ hours standard on propane fuel cell with 2.5 kg payload, or 4 hours on battery. Record endurance 39 hours, 17 minutes, and 7 seconds, achieved with an external wing-mounted fuel tank and a production Stalker VXE modified for the record flight. Cruise speed 30+ knots, maximum speed 50+ knots. Flight ceiling 4,572 m (15,000 ft). Communications range up to 160 km (100 miles). VTOL endurance up to 2 hours on battery. Ferry range 138 miles on battery, 269 miles on fuel cell.

**Power** — Hybrid propulsion system. A ruggedized Solid Oxide Fuel Cell (SOFC) using propane provides 8+ hours of operation, or a rechargeable lithium battery provides 4 hours. The fuel cell can replace 90% of onboard batteries, providing a sixfold increase in mission duration compared to battery-only systems. The record flight used a hybrid propane SOFC and lithium battery with an external wing-mounted fuel tank. Propane is globally available and efficient, enabling extended range and loiter time without the noise of a combustion engine.

**Thermal** — Passive cooling. The fuel cell operates at high temperature internally but the exterior surfaces remain cool enough for safe handling. The electric motors are air-cooled by rotor wash in hover and ram air in forward flight. The low thermal signature is a key survivability feature; the aircraft is difficult to detect by infrared sensors compared to internal combustion engines.

**Environmental** — Designed for expeditionary operations in austere locations. The aircraft is deployed from rooftops and confined clearings, operates in challenging weather conditions, and is fully operational in GPS-denied areas with precision navigation. Not rated for icing conditions without additional protection. The composite airframe is resistant to environmental degradation. The low acoustic signature allows operation at low altitude without detection.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Stalker is purchased as a complete system with ground control station, payload integration, and support equipment.

| Component | Value |
|:---|:---|
| Stalker Block 30 airframe | Composite construction, 4.9 m wingspan, 22 kg MTOW |
| Solid Oxide Fuel Cell (SOFC) | Propane-powered, 8+ hours endurance |
| Rechargeable lithium battery | 4 hours endurance, backup for fuel cell |
| VTOL rotor system | Electric rotors for vertical launch and recovery |
| Pusher propeller | Forward flight propulsion |
| Flight control system | Fully autonomous, GPS-denied navigation capable |
| EO/IR sensor payload | Stabilised day/night imaging and targeting |
| SIGINT payload | Signals intelligence collection |
| Communications datalink | Up to 160 km range, Silvus Dual S & C band |
| Ground control station | Operator interface for mission command and payload control |

**Structure** — Lightweight composite airframe with a high aspect ratio wing for efficient cruise and long endurance. The VTOL rotor arms are attached to the fuselage and stow for transport. The fuselage houses the fuel cell, battery, avionics, and payload bay. The aircraft is designed for rapid assembly in ten minutes by a two-person team, with no runway infrastructure required. The airframe is optimised for low acoustic signature, making it quiet at close range.

**Actuation** — Hybrid VTOL: electric rotors for vertical flight, pusher propeller for forward cruise. Control surfaces (elevator, rudder, ailerons) actuated by lightweight electromechanical actuators. The flight control system manages the transition between hover and forward flight automatically. The VTOL configuration provides the flexibility to launch and recover from confined spaces that would be impossible for conventional fixed-wing aircraft.

**Locomotion** — Hybrid VTOL fixed-wing. Vertical take-off using rotors, transition to forward flight, cruise as a fixed-wing aircraft, transition back to hover for vertical landing. The aircraft is runway-independent, enabling deployment from rooftops, vehicle decks, and confined clearings. Cruise speed 30+ knots, maximum speed 50+ knots.

**Manipulation** — None. The aircraft is a sensor and communications platform. The payload is the effector: EO/IR cameras, SIGINT equipment, or other mission sensors. The modular payload bay allows reconfiguration for different mission profiles.

**Power system** — Hybrid propulsion with a propane Solid Oxide Fuel Cell and a rechargeable lithium battery. The fuel cell provides 8+ hours of endurance, while the battery provides 4 hours and serves as a backup for the fuel cell. The record flight configuration used an external wing-mounted fuel tank to achieve 39+ hours. Propane is globally available and efficient, enabling extended range and loiter time without the noise of a combustion engine.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The communications datalink uses Silvus Dual S & C band as standard, providing up to 160 km range.

**Custom parts** — None. All components are Edge Autonomy/Redwire proprietary or certified third-party. The modular payload bay enables rapid reconfiguration for different mission profiles. The record flight configuration used an external wing-mounted fuel tank, which is not a standard production feature but demonstrates the platform’s ability to accept extended-range modifications.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid assembly and recovery by a two-person team, with modular components for field maintenance.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The aircraft assembles in ten minutes by a two-person team with no special tools.

---

## Systems

**Manifest** — Edge Autonomy/Redwire proprietary software stack with fully autonomous flight control and GPS-denied navigation.

**Firmware** — The aircraft runs a proprietary flight control system with fully autonomous operation, including automatic VTOL launch, transition to forward flight, cruise, and recovery. The aircraft is fully operational in GPS-denied areas with precision navigation and a state-of-the-art flight control system. The fuel cell and battery are managed by an energy management system that optimises endurance and power delivery.

**Middleware** — Proprietary. The aircraft communicates via a Silvus Dual S & C band datalink with up to 160 km range. The ground control station provides mission planning, payload control, and data exploitation. The open architecture supports integration of third-party payloads and mission software.

**Perception** — Modular payload bay with 2.5 kg capacity. Payload options include EO/IR sensors for day/night imaging and targeting, SIGINT equipment for signals intelligence collection, and other mission sensors. The low acoustic signature allows the aircraft to operate at low altitude, making the sensors more effective than high-altitude platforms. Specific sensor details are not publicly disclosed, but the platform is designed for modular payload integration.

**Control** — Fully autonomous flight control. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft handles VTOL launch, transition to forward flight, navigation, station-keeping, and recovery autonomously. The GPS-denied navigation capability enables operations in contested electronic warfare environments where GNSS jamming and spoofing are prevalent.

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The aircraft can be retasked in flight. The VTOL capability allows launch and recovery from confined locations, enabling operations from rooftops, vehicle decks, and austere clearings without runway infrastructure.

**Learning** — None publicly disclosed. The aircraft uses classical control, autonomous navigation, and energy management. No learning-based control is mentioned for safety-critical functions.

**Teleoperation** — Two-person launch and recovery team, single operator for flight control via ground control station. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and VTOL transitions autonomously. The ground control station provides mission planning, payload control, and data exploitation.

**Safety** — The aircraft is fully autonomous, with GPS-denied navigation and precision landing capability. The VTOL configuration eliminates the risk of runway excursions or launch failures. The low acoustic signature reduces the risk of detection. The fuel cell and battery provide redundant power sources. The aircraft is designed for operation in austere and contested environments, with resilience to GNSS jamming and spoofing.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The low acoustic signature and low-altitude operation enable fine-grained intelligence collection that would be difficult with high-altitude platforms. Specific logging details are not publicly disclosed.

**Networking** — Silvus Dual S & C band datalink with up to 160 km range. The aircraft can operate as a communications relay or network node, extending communications coverage in austere environments. The open architecture supports integration with third-party command and control systems.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the ground control station.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Edge Autonomy/Redwire ground control station software. Flight control system. Payload-specific software (EO/IR, SIGINT). Silvus datalink software.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Edge Autonomy flight control | Proprietary | Edge Autonomy | Control/Flight |
| GPS-denied navigation | Proprietary | Edge Autonomy | Navigation/GNSS-Denied |
| Energy management | Proprietary | Edge Autonomy | Power/Energy |
| Ground control station | Proprietary | Edge Autonomy | GCS |
| Payload integration software | Proprietary | Various | Payload/Integration |
| Silvus datalink | Proprietary | Silvus | Comms/Datalink |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, fuel cell status, battery state, system health. Sensor data: EO/IR imagery, SIGINT data. Network data: datalink status, relay node status.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. VTOL launch and recovery commands.

**Serves** — Persistent ISR services. Force protection. Route monitoring. Signals intelligence collection. Communications relay.

**Executes** — Autonomous VTOL launch, transition to forward flight, persistent ISR over a local area, signals intelligence collection, autonomous recovery. Return-to-base in comms-denied environment.

**Extensions** — Modular payload bay (2.5 kg capacity). EO/IR, SIGINT, and other mission sensors. External wing-mounted fuel tank for extended endurance (record configuration). Communications relay payload.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL.

**Units** — SI and aviation standard. Metres, feet, knots, kilometres, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR and SIGINT payloads. Flight control system calibrated for VTOL transition and forward flight. Fuel cell and battery energy management calibrated for optimal endurance.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and energy management. The hybrid VTOL configuration presents unique challenges during transition from hover to forward flight; the flight control system manages this transition autonomously. The high aspect ratio wing provides efficient cruise and long endurance. The fuel cell provides sixfold increase in mission duration compared to battery-only systems.

**Sensor transforms** — Payload sensors mounted in the modular payload bay. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of fuel cell, battery, motors, flight control system, and payloads.

**Integration** — Payload integration in the modular bay. Flight control system verification. GPS-denied navigation verification. Fuel cell and battery integration. Datalink and ground control station integration.

**Field** — World record endurance flight: 39 hours, 17 minutes, and 7 seconds, establishing a new record in the Group 2 (5 to <25 kg) category. The record flight was conducted with a production Stalker VXE modified with an external wing-mounted fuel tank and powered by a hybrid propane SOFC and lithium battery. U.S. Marine Corps fielding in Japan. $20 million follow-on orders from U.S. Navy and Marine Corps. Operation in austere locations without runway infrastructure. Low-altitude ISR missions with EO/IR and SIGINT payloads.

**Endurance** — 8+ hours standard on fuel cell with 2.5 kg payload. 4 hours on battery. 2 hours VTOL endurance on battery. 39+ hours record endurance with external fuel tank. Ferry range 269 miles on fuel cell, 138 miles on battery.

**Environmental** — Expeditionary operations in austere locations. Deployed from rooftops, vehicle decks, and confined clearings. Not for icing conditions without additional protection. Low acoustic signature for undetected low-altitude operation.

**Known limitations** — The Stalker is a Group 2 UAS with a 2.5 kg payload capacity; it cannot carry large sensors or heavy weapons. The 8+ hour endurance is impressive but limited compared to larger MALE/HALE platforms. The fuel cell requires propane, which must be supplied in the field; the battery provides a 4-hour backup. The 39-hour record flight used a non-standard external fuel tank configuration. The low acoustic signature and low-altitude operation make the aircraft more effective for close-range ISR, but it is still vulnerable to air-to-air threats and ground fire at low altitude. The aircraft is not stealth; it relies on low acoustic and thermal signatures, altitude, and endurance for survivability.

---

## Log

**Build history** — Stalker developed by Lockheed Martin, now produced by Edge Autonomy (Redwire). Stalker VXE30 record flight 2022: 39 hours, 17 minutes, 7 seconds in the Group 2 category. Stalker Block 30 is the current production variant with hybrid VTOL and propane fuel cell. U.S. Marine Corps fielded Stalker in Japan (2025). Redwire received $20 million in follow-on orders from the U.S. Navy and Marine Corps (2026). The Stalker is designed to fill the gap between short-endurance quadcopters and larger tactical UAVs, providing expeditionary ISR with minimal infrastructure.

**Open issues** — Expansion of payload options (SIGINT, EW, communications relay). Fuel cell logistics in austere environments. Production scaling to meet demand. Export control and ITAR restrictions. Integration with emerging command and control systems.

**Changelog** — Stalker VXE: record 39-hour flight (2022). Stalker Block 30: hybrid VTOL, propane fuel cell, 8+ hours endurance, modular payload bay. Block 30 follow-on orders from U.S. Navy and Marine Corps (2026).

**Lessons learned** — The hybrid VTOL configuration eliminates the need for runways, catapults, or launch gear, enabling deployment from rooftops, vehicle decks, and confined clearings. The propane fuel cell provides a sixfold increase in mission duration compared to battery-only systems, enabling 8+ hours of endurance. The low acoustic signature allows the aircraft to operate undetected at low altitude, making its sensors more effective than high-altitude platforms. The VTOL capability and small logistical footprint make the Stalker suitable for expeditionary operations in austere locations. The aircraft fills the gap between short-endurance quadcopters and larger tactical UAVs, providing persistent local ISR at the tactical edge.

**Cost actual** — Redwire received $20 million in follow-on orders from the U.S. Navy and Marine Corps for Stalker drones. Unit cost is not publicly disclosed but is expected to be a fraction of larger MALE/HALE platforms. The Stalker is positioned as a cost-effective, attritable ISR asset for tactical operations.

---

## Status

**Condition** — operational. Fielded with the U.S. Marine Corps and other allied forces. Production active with follow-on orders from the U.S. Navy and Marine Corps.

**Blockers** — None. Active production and procurement.

**Next steps** — Integration of new payloads (SIGINT, EW, communications relay). Continued fielding with U.S. Marine Corps and allied forces. Expansion of export sales to allied and partner forces. Production scaling to meet demand. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The stalker is a distinct class in the library: a Group 2 hybrid VTOL fixed-wing UAS designed for **local, persistent ISR** in austere and contested environments. Unlike the k1000ule (solar-powered, 75-hour endurance, Group 2) or the v-bat (ducted-fan, heavy-fuel, 13-hour endurance, Group 3), the Stalker combines hybrid VTOL with propane fuel cell endurance to achieve 8+ hours of flight with a 2.5 kg payload, or 39+ hours in record configuration. Its low acoustic signature allows it to operate undetected at low altitude, making its sensors more effective than high-altitude platforms for close-range intelligence collection. The VTOL capability and two-person, ten-minute assembly make it suitable for expeditionary operations from rooftops, vehicle decks, and confined clearings. With U.S. Marine Corps fielding, U.S. Navy follow-on orders, and a world record for endurance in its class, the Stalker is the reference for a small, long-endurance, VTOL ISR platform for local persistent surveillance.
