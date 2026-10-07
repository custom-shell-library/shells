# k1000ule

**Class:** aerial (Group 2 solar-powered ultra-long-endurance UAS)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Kraus Hamdani Aerospace (KHA)  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Small, solar-powered, ultra-long-endurance unmanned aircraft designed for persistent local ISR (Intelligence, Surveillance, Reconnaissance) and communications relay. The K1000ULE is not a strategic asset; it is a **pseudo-satellite** that a small unit can deploy from an SUV, leave airborne for days, and use to maintain continuous situational awareness over a local area of operations. It is the longest-endurance fully electric unmanned aircraft in its size and weight category (Group 2, 21–55 lb). Its defining feature is not speed or payload, but **persistence**: 75+ hours of continuous flight, achieved through solar recharge and AI-controlled thermal soaring that mimics a bird's flight patterns, allowing it to operate with its engine off up to 80% of the time.

**Environment** — Outdoor, all-weather, day and night operations. Service ceiling 20,000 ft, allowing it to operate above weather and civilian traffic. Deployed from an SUV or small vehicle in austere environments. The aircraft is designed for endurance and flexibility rather than speed or firepower. Not for operations in icing conditions or severe turbulence without additional protection. Deployed in the Indo-Pacific, Middle East, and Africa.

**Mission** — Local ISR, communications relay, electronic warfare, and persistent surveillance. The K1000ULE carries a 5.5 lb (2.5 kg) payload that can include sensors, communications equipment, and electronic warfare systems. It functions as an airborne network node, connecting legacy systems with modern systems through the ATNE++ communications system, and can operate in contested environments. On the civilian side, it has been used in the oil industry for long-range monitoring.

**Operator** — Small unit deployment, typically two personnel. The aircraft is extremely portable and can be deployed from an SUV. The operator provides mission-level command; the aircraft handles flight control and energy management autonomously, using AI to detect and exploit thermal currents. The autopilot runs ArduPilot, which is open-source and has been updated with Ukraine combat data.

**Reusability** — Commercial defence platform with active procurement. The US Air Force awarded a $270 million contract for K1000ULE drones under a new tender. Operationally used by the US Army, Navy, and SOCOM, and has been deployed in the Indo-Pacific, Middle East, and Africa. The platform is proven, not a science experiment.

---

## Spec

**Physical** — Length 9.8 ft (3 m). Wingspan 16–20 ft (4.9–6.1 m), depending on variant. Maximum take-off weight 42.5 lb (19.3 kg). The airframe is constructed from lightweight composite materials with solar panels embedded in the wing surface, which recharge the onboard lithium-ion batteries. The aircraft is designed for extreme portability and can be deployed from a small vehicle.

**Kinematic** — Twin propeller engines, electric. Fixed-wing configuration optimized for endurance rather than speed. The aircraft uses AI to detect and benefit from thermal currents, mimicking a bird's soaring pattern; this allows it to operate with its engine off up to 80% of the time. The autopilot system runs ArduPilot, an open-source autopilot updated with Ukraine combat data. The aircraft can be configured for fixed-wing flight (up to 24 hours) or eVTOL mode (up to 12 hours).

**Dynamic** — Endurance: 75+ hours continuous flight (2023 record), with standard endurance up to 24 hours depending on configuration and conditions. Top speed 46 mph (74 km/h). Service ceiling 20,000 ft. The 75-hour record was set in 2023, exceeding any unrefuelled drone flight in its class. The aircraft's endurance is enabled by solar panels, batteries, and energy-efficient AI-controlled flight patterns inspired by birds.

**Power** — Solar-powered, fully electric. Solar panels embedded in the wing recharge lithium-ion batteries during daylight hours. The AI-controlled thermal soaring allows the aircraft to operate with its engine off up to 80% of the time, dramatically extending endurance. No fuel logistics required.

**Thermal** — Passive thermal management. The solar panels and batteries are thermally coupled to the wing structure, which acts as a heat sink during daylight hours. The AI-controlled soaring reduces motor operation, which in turn reduces thermal load. No active refrigeration is required for the operating envelope.

**Environmental** — Designed for operation in austere environments. The aircraft is deployed from an SUV and operates above weather and civilian traffic at 20,000 ft. Not rated for icing conditions without additional protection. The composite airframe is resistant to UV degradation and environmental exposure. Deployed in diverse climates including the Indo-Pacific, Middle East, and Africa.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The K1000ULE is purchased as a complete system with ground control station and modular payload integration.

| Component | Notes |
|:---|:---|
| K1000ULE airframe | Composite construction, 3 m length, 16–20 ft wingspan, 42.5 lb MTOW |
| Solar panels | Embedded in wing surface, recharge lithium-ion batteries |
| Lithium-ion batteries | Store solar energy for night operation and peak power demands |
| Twin propeller engines | Electric, powered by solar-charged batteries |
| AI thermal soaring autopilot | ArduPilot-based, updated with Ukraine combat data |
| ATNE++ communications system | Airborne network node, connects legacy and modern systems |
| Modular payload bay | 5.5 lb (2.5 kg) capacity for sensors, comms, EW |
| Ground control station | Operator interface for mission command and payload control |

**Structure** — Lightweight composite airframe with high aspect ratio wing. The wing is the primary structural element, housing the solar panels and supporting the twin propeller engines. The fuselage is minimal, housing the batteries, avionics, and payload bay. The aircraft is designed for disassembly and transport in a small vehicle, enabling deployment from austere locations. The solar panels embedded in the wing replenish the long-endurance battery and power the AI directional program.

**Actuation** — Twin electric propeller engines. Control surfaces actuated by lightweight electromechanical actuators. The AI-controlled autopilot manages all phases of flight, including thermal soaring, energy management, and station-keeping. The engine-off soaring capability is the key enabler of the 75-hour endurance.

**Locomotion** — Fixed-wing flight with eVTOL capability. The aircraft can take off and land vertically (eVTOL mode, 12-hour endurance) or operate as a conventional fixed-wing aircraft (24-hour endurance). The AI-controlled thermal soaring allows the aircraft to gain altitude without motor power, mimicking a bird's flight pattern.

**Manipulation** — None. The aircraft is a sensor and communications platform. The payload is the effector: sensors, communications relay equipment, or electronic warfare systems.

**Power system** — Solar-powered, fully electric. Solar panels in the wing recharge lithium-ion batteries. The AI thermal soaring reduces motor operation, extending battery life. No fuel logistics required, which is a significant advantage in austere environments where fuel resupply is difficult or impossible.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The ATNE++ communications system provides the network interface for connecting legacy and modern systems.

**Custom parts** — None. All components are KHA proprietary or certified third-party. The modular payload bay enables integration of different sensors and communications equipment.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for field deployment by a small crew, with modular components for rapid assembly and disassembly.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The system is designed for rapid deployment from an SUV.

---

## Systems

**Manifest** — KHA proprietary software stack with ArduPilot-based autopilot and ATNE++ communications system.

**Firmware** — The autopilot runs ArduPilot, an open-source autopilot that has been updated with Ukraine combat data. The AI-controlled thermal soaring algorithm detects and exploits thermal currents, allowing the aircraft to operate with its engine off up to 80% of the time. The autopilot manages all phases of flight, including takeoff, climb, cruise, thermal soaring, energy management, and landing.

**Middleware** — KHA proprietary. The ATNE++ system functions as an airborne network node, connecting legacy systems with modern systems. The aircraft can operate in contested environments, with networking capabilities that are more technically important than the airframe itself, reflecting trends in combat design philosophy.

**Perception** — Modular payload bay with 5.5 lb (2.5 kg) capacity. Payload options include sensors, communications equipment, and electronic warfare systems. The aircraft can carry electro-optical and infrared sensors for ISR, as well as communications relay equipment. Specific sensor details are not publicly disclosed, but the platform is designed for modular payload integration.

**Control** — The autopilot manages all flight control functions autonomously. The AI-controlled thermal soaring is the key differentiator: the aircraft detects thermal currents and exploits them to gain altitude without motor power, extending endurance dramatically. The operator provides mission-level command; the aircraft handles flight control, energy management, and thermal soaring autonomously.

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The AI thermal soaring is autonomous, not operator-commanded. The aircraft can be retasked in flight.

**Learning** — The AI thermal soaring is a form of learning-based control, though it is not described as reinforcement learning or imitation learning. The AI detects and benefits from thermal currents, mimicking a bird's soaring pattern. This is a classical control approach informed by biological flight, not a learning-based policy.

**Teleoperation** — Ground control station with operator interface. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft handles flight control and energy management autonomously. The ATNE++ communications system provides the network link for command and control.

**Safety** — The autopilot is autonomous, with energy management ensuring the aircraft maintains sufficient battery charge for continued operation. The AI thermal soaring is inherently safe: if no thermal is available, the aircraft uses motor power. The aircraft operates above weather and civilian traffic at 20,000 ft, reducing collision risk. The system is designed for operation in contested environments, with networking capabilities that are resistant to jamming and interference.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The aircraft can operate as an airborne network node, relaying data to ground stations and other platforms. Specific logging details are not publicly disclosed.

**Networking** — ATNE++ system provides airborne network node capability, connecting legacy systems with modern systems. The aircraft can operate in contested environments, with networking capabilities that are more technically important than the airframe itself. The system can relay communications between ground units, extending range and overcoming terrain obstacles.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set at the ground control station.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — KHA ground control station software. ArduPilot autopilot. ATNE++ communications system. Payload-specific software.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ArduPilot | Updated with Ukraine data | ardupilot.org | Middleware/Autopilot |
| KHA thermal soaring AI | Proprietary | KHA | Autonomy/ThermalSoaring |
| ATNE++ communications | Proprietary | KHA | Comms/Network |
| Ground control station | Proprietary | KHA | GCS |
| Payload integration software | Proprietary | Various | Payload/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, solar output, thermal soaring status, system health. Sensor data: EO/IR imagery, SIGINT data, communications relay signals. Network data: ATNE++ node status, connected systems.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Communications relay configuration. Payload commands.

**Serves** — Persistent ISR services. Communications relay services. Airborne network node services. Electronic warfare services (if equipped).

**Executes** — Autonomous navigation. Thermal soaring. Persistent ISR over a local area. Communications relay. Network extension. Electronic warfare.

**Extensions** — Modular payload bay (5.5 lb capacity). Sensors, communications equipment, electronic warfare systems. ATNE++ network node.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in mph or knots. Altitude in feet MSL.

**Units** — SI and aviation standard. Metres, feet, miles per hour, kilometres per hour, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary commercial platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Solar panel and battery performance characterized through flight testing. Thermal soaring AI calibrated for different geographic regions and seasons. Autopilot calibrated for fixed-wing and eVTOL modes.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and energy management. The AI thermal soaring algorithm models the aircraft's interaction with thermal currents, allowing it to gain altitude without motor power. The high aspect ratio wing and lightweight airframe present unique challenges at low speeds, where thermal soaring is most effective.

**Sensor transforms** — Payload sensors mounted in the modular payload bay. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of solar panels, batteries, motors, and autopilot.

**Integration** — Payload integration in the modular bay. Autopilot verification. Thermal soaring AI verification. ATNE++ communications system verification.

**Field** — 2023 record flight: 75 hours continuous flight, exceeding any unrefuelled drone flight in its class. Deployed in the Indo-Pacific, Middle East, and Africa. Used by the US Army, Navy, and SOCOM. Civilian use in the oil industry for long-range monitoring. Operationally proven, not a science experiment.

**Endurance** — 75+ hours continuous flight (2023 record). Standard endurance up to 24 hours depending on configuration and conditions. eVTOL mode up to 12 hours. Service ceiling 20,000 ft. Top speed 46 mph.

**Environmental** — All-weather operations. Deployed in diverse climates. Not for icing conditions without additional protection.

**Known limitations** — The K1000ULE is a Group 2 UAS with a 5.5 lb payload capacity; it cannot carry large sensors or heavy communications equipment. It is not a tactical strike platform; it is an ISR and communications relay platform. The 20,000 ft service ceiling is lower than strategic HALE platforms, but sufficient to operate above weather and civilian traffic. The aircraft requires favourable thermal conditions for maximum endurance; in regions without strong thermal currents, endurance is reduced. The aircraft is not stealth; it is a slow, propeller-driven platform that is vulnerable to air-to-air threats in contested airspace. The AI thermal soaring is a sophisticated capability that requires extensive flight testing and calibration for different geographic regions and seasons.

---

## Log

**Build history** — K1000ULE developed by Kraus Hamdani Aerospace (KHA), California-based. Year introduced: early 2020s. Set a record for unrefuelled drone flight of 75 hours in 2023. US Air Force awarded $270 million contract for K1000ULE drones under a new tender. Operationally used by the US Army, Navy, and SOCOM. Deployed in the Indo-Pacific, Middle East, and Africa. Civilian use in the oil industry for long-range monitoring.

**Open issues** — Expansion of payload options. Integration with emerging communications systems. Operation in regions without strong thermal currents. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — K1000ULE: initial production configuration. 2023: 75-hour endurance record. 2026: $270 million USAF contract.

**Lessons learned** — The AI thermal soaring capability is the key enabler of the 75-hour endurance, allowing the aircraft to operate with its engine off up to 80% of the time. The solar panels and batteries provide energy for night operation and peak power demands. The ATNE++ communications system is more technically important than the airframe itself, reflecting the shift in combat design philosophy toward networking and information sharing. The aircraft's portability (SUV-deployable) makes it suitable for small unit operations in austere environments. The platform is proven in combat and civilian use, not a science experiment.

**Cost actual** — Per-unit cost roughly in the tens of thousands of dollars, compared to the MQ-9 Reaper's price tag of $30 million. The K1000ULE is so cheap that it is considered attritable, meaning it can be lost without significant financial impact.

---

## Status

**Condition** — operational. Fielded with US Army, Navy, and SOCOM. $270 million USAF contract awarded.

**Blockers** — None. Active production and procurement.

**Next steps** — Expansion of payload options. Integration with emerging communications systems. Continued deployment for persistent ISR and communications relay. Production scaling to meet demand. Development of successor systems with enhanced thermal soaring AI.

---

**Note on this Shell:** The k1000ule is a distinct class in the library: a small, solar-powered, ultra-long-endurance Group 2 UAS designed for **local** persistent ISR and communications relay. Unlike the Orion (tethered, 100 m altitude, 50-hour endurance) or the Evo-LE (VTOL fixed-wing, 8-hour endurance), the K1000ULE is a free-flying, solar-powered aircraft that can loiter for days over a local area, using AI thermal soaring to extend endurance far beyond what battery capacity alone would allow. It is not a strategic asset like the SeaGuardian or Zephyr; it is a tactical asset that a small unit can deploy from an SUV, leave airborne for days, and use to maintain continuous situational awareness over a local area of operations. Its 5.5 lb payload capacity is sufficient for EO/IR sensors, communications relay equipment, or electronic warfare systems. The ATNE++ communications system makes it a network node, not just a sensor platform. With a per-unit cost in the tens of thousands of dollars, it is attritable and affordable. This Shell is the reference for a solar-powered, AI-soaring, ultra-long-endurance small UAS for local persistent ISR and communications relay.
