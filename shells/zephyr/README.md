# zephyr

**Class:** aerial (HAPS — High Altitude Platform Station)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** AALTO (Airbus subsidiary)  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Solar-powered stratospheric unmanned aircraft designed to operate as a High Altitude Platform Station (HAPS) in the “Stratospace” — the layer between conventional airspace and satellites. The Zephyr is not a drone, aircraft, or space asset in the traditional sense; it is a stratocraft that combines the persistence of a geostationary satellite with the flexibility and accuracy of a drone. It provides deep sensing, network extension, and persistent surveillance from 60,000–75,000 ft, above weather and regular air traffic, for months at a time without refuelling.

**Environment** — Stratospheric operations between 60,000 ft and 75,000 ft. Solar-powered, fully electric. Designed to remain above conventional air traffic and most weather systems. Operating altitude provides a stratospheric gateway for acquiring data and connecting assets. Not for operations in the troposphere beyond transit to and from the stratosphere. The aircraft has gained civil and military approvals in five countries across four continents.

**Mission** — Persistent ISR (Intelligence, Surveillance, Reconnaissance), deep sensing, long-range targeting, indications and warning, network extension and communications relay, battle damage assessment, and Assured Positioning, Navigation & Timing (APNT). Commercial capabilities include high service availability, land and sea monitoring, environmental monitoring, disaster management, and direct-to-device mobile connectivity. The Zephyr can station-keep or be readily retasked, travelling up to 1,000 nautical miles per day.

**Operator** — Controlled from Ground Control Stations anywhere in the world using Beyond Line of Sight (BLOS) capabilities. After take-off and ascent into the stratosphere within eight hours, Zephyr navigates to the desired location, which may be hundreds or thousands of kilometres away. The operator provides mission-level command; the aircraft handles flight control, navigation, and station-keeping autonomously.

**Reusability** — Commercial HAPS platform in pre-commercial operational readiness. Over 10 Zephyr 8B models produced, with the improved Zephyr 8C production model planned. AALTO employs approximately 220 people and operates from Farnborough, UK, with a dedicated AALTOPORT in Kenya supporting launch, recovery, and operations. AALTO is intensifying flight testing and working with the UK Civil Aviation Authority towards certification and global commercialisation.

---

## Spec

**Physical** — Wingspan approximately 25 m (82 ft). Weight under 75 kg (165 lbs). Payload capacity up to 8 kg, distributed across two wing bays with dimensions of approximately 800 mm × 330 mm × 110 mm per bay. The ultra-lightweight airframe is constructed from advanced lightweighting materials, including carbon fibre composites and solar cell integrations. The aircraft is engineered to withstand extreme stratospheric conditions including temperatures down to −80 °C and low atmospheric pressure.

**Kinematic** — Fixed-wing, solar-powered, fully electric. High aspect ratio wing for efficient high-altitude cruise. The aircraft is hand-launched or cart-launched and recovered by a belly landing on a prepared surface. Control surfaces are actuated by lightweight electromechanical actuators. The flight control system manages ascent into the stratosphere (within eight hours of take-off), station-keeping, retasking, and descent. The aircraft has demonstrated precise manoeuvrability and agility, enabling operations in complex international airspace without risk of unintended drift into adversary-controlled airspace.

**Dynamic** — Endurance record 67 days, six hours and 52 minutes (2025), exceeding the previous 64-day record. During the 2018 test flight, Zephyr achieved 26 days endurance (25 days, 23 hours and 57 minutes), the longest flight duration of an aircraft ever made without refuelling. The aircraft persisted in the stratosphere day and night, achieving a dawn altitude of 60,000 ft and a highest altitude of 71,140 ft. Operational altitude between 60,000 ft and 75,000 ft. Travelling up to 1,000 nautical miles per day. Cruise speed at altitude is approximately 20–30 m/s (45–67 mph), optimised for station-keeping rather than transit. AALTO is ultimately targeting missions lasting as long as 150 days.

**Power** — Solar-powered, fully electric. The upper wing surface is covered with high-efficiency solar cells that charge lithium-sulphur batteries during daylight hours. The batteries power the electric motors and avionics through the night, enabling continuous day and night operation. The energy balance depends on latitude, season, and altitude; the aircraft operates in the stratosphere where solar irradiance is higher and cloud cover is absent. The 2025 record flight of 67 days demonstrated the energy balance and battery longevity required for multi-month missions.

**Thermal** — Passive thermal management. The stratospheric environment presents unique thermal challenges: solar heating during the day, radiative cooling at night, and ambient temperatures down to −80 °C. The aircraft uses lightweight insulation and thermal control coatings to manage the temperature of the batteries, avionics, and payload. The solar cells and batteries are thermally coupled to the wing structure, which acts as a radiator during the night. No active refrigeration is used; thermal management is entirely passive to minimise mass and power consumption.

**Environmental** — Designed for stratospheric operations. The aircraft is not pressurised and carries no environmental control for a crew (it is unmanned). The airframe is resistant to UV degradation and ozone exposure. The aircraft operates above most weather systems, but must transit through the troposphere during ascent and descent, which exposes it to wind shear, turbulence, and icing conditions. The launch and recovery operations are weather-dependent.

---

## Frame

**Bill of materials** — Commercial HAPS platform. Not a DIY build. The Zephyr is purchased as a complete system with ground control station, launch and recovery equipment, and payload integration services.

| Component | Notes |
|:---|:---|
| Zephyr airframe | ~25 m wingspan, <75 kg, ultra-lightweight composite construction |
| Solar cells | High-efficiency cells covering upper wing surface |
| Lithium-sulphur batteries | Lightweight, high energy density, cycled daily |
| Electric motors (2×) | Brushless DC motors driving pusher propellers |
| Flight control system | Autonomous flight control with station-keeping and retasking |
| BLOS communication | Beyond Line of Sight control from Ground Control Stations worldwide |
| Payload bays (2×) | 800 × 330 × 110 mm each, up to 8 kg total |
| Ground Control Station | Mission planning, telemetry, payload control |
| Launch and recovery equipment | Cart launch, belly landing on prepared surface |
| AALTOPORT | Dedicated facility for launch, recovery, and operations (Kenya) |

**Structure** — Ultra-lightweight composite airframe with high aspect ratio wing. The wing is the primary structural element, housing the solar cells, batteries, and payload bays. The fuselage is minimal, housing the avionics, flight control system, and communication equipment. The two electric motors and propellers are mounted on the wing, providing differential thrust for yaw control and propulsion. The airframe is designed for disassembly and transport in standard shipping containers, enabling deployment to remote operating locations.

**Actuation** — Two brushless DC electric motors driving pusher propellers. Control surfaces (elevator, rudder, ailerons) actuated by lightweight electromechanical actuators. The flight control system manages all phases of flight autonomously, including launch, ascent, station-keeping, retasking, descent, and recovery. No hydraulics; all-electric actuation.

**Locomotion** — Fixed-wing, solar-powered, fully electric flight. The aircraft is hand-launched or cart-launched and climbs to the stratosphere within eight hours. It then operates as a stratospheric platform, station-keeping or transiting at up to 1,000 nautical miles per day. Recovery is by belly landing on a prepared surface.

**Manipulation** — None. The aircraft is a sensor and communications platform. The payload bays accommodate interchangeable payloads for ISR, communications relay, and electronic warfare.

**Power system** — Solar cells on the upper wing surface charge lithium-sulphur batteries during daylight. The batteries power the electric motors and avionics through the night. Power distribution includes redundant buses for flight-critical avionics and payloads. The energy balance is designed for continuous 24-hour operation at stratospheric latitudes, with margin for seasonal and latitudinal variations.

**Wiring** — Internal only. Not user-accessible. Payload integration via the two wing bays. The aircraft has been designed for payload agnosticism, meaning it can accommodate different payloads without redesigning the airframe.

**Custom parts** — None. All components are AALTO/Airbus proprietary or certified third-party. Payloads are integrated into the wing bays using standard mechanical and electrical interfaces.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for minimal maintenance between flights; the primary maintenance activity is battery inspection and replacement after extended missions.

**Tools required** — None for assembly (factory-built). Standard tools for payload integration and field maintenance. The aircraft is transported in shipping containers and assembled on-site by a small crew.

---

## Systems

**Manifest** — AALTO proprietary software stack with payload agnosticism and open interfaces for payload integration.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous navigation, station-keeping, and retasking capability. The flight control system manages the ascent to the stratosphere, the transition to station-keeping mode, and the descent and recovery. The system has demonstrated operational flexibility and aircraft agility, particularly testing lower altitude flying and early stage transition to the stratosphere.

**Middleware** — Proprietary. The aircraft is controlled via BLOS communication links from Ground Control Stations anywhere in the world. The BLOS capability enables control from a ground station thousands of kilometres away. Payload data is downlinked via the same communication links or via separate payload data links.

**Perception** — Payload agnostic. The Zephyr has demonstrated or planned the following payloads: Electronic Support (ES), Electro Optical & Infrared (EO/IR), Synthetic Aperture Radar (SAR), Signals Intelligence (SIGINT), Electronic Intelligence (ELINT), Assured Position, Navigation & Timing (APNT), and various communications and network payloads including 5G, Link 16, MESH, and optical communications. The payload bays are designed to accommodate different payloads with minimal integration effort. The aircraft is also suitable for “local persistence” (ISR) with the ability to stay focused on a specific area of interest hundreds of miles wide, providing satellite-like communications and Earth observation services with greater image granularity over long periods without interruption.

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command: station-keeping location, retasking orders, and payload tasking. The aircraft has demonstrated precise manoeuvrability and agility, enabling operations in complex international airspace. The flight control system also manages the energy balance, ensuring that the solar cells and batteries maintain sufficient charge for continuous 24-hour operation.

**Planning** — Mission planning is performed at the Ground Control Station. The operator defines the station-keeping location, mission duration, and payload tasking. The aircraft autonomously navigates to the desired location after ascent, which may be hundreds or thousands of kilometres away. The aircraft can be retasked in flight to a new location. The 2025 record flight demonstrated the international regulatory coordination required to operate a HAPS across multiple jurisdictions, including crossing the Intertropical Convergence Zone twice and passing through seven flight information regions.

**Learning** — None publicly disclosed. The aircraft uses classical control, autonomous navigation, and energy management. No learning-based control is mentioned.

**Teleoperation** — Ground Control Station with BLOS communication. The operator commands the aircraft from anywhere in the world. The aircraft has demonstrated operational flexibility and aircraft agility, including lower altitude flying and early stage transition to the stratosphere. The Ground Control Station provides telemetry, payload data, and mission planning functions.

**Safety** — The flight control system is autonomous, with redundant avionics for flight-critical functions. The aircraft has gained civil and military approvals in five countries across four continents, demonstrating compliance with airspace regulations. The BLOS control enables operation from a ground station anywhere in the world, reducing the risk of loss of control. The aircraft is designed to be “affordable, attritable” relative to other larger HAPS options, meaning it is cost-effective to operate and replace if lost.

**Logging** — Mission data, sensor data, and flight telemetry are logged onboard and downlinked to the Ground Control Station. The 2025 record flight data includes flight duration, altitude, route, and energy management performance.

**Networking** — BLOS communication links for command and control. Payload data links for ISR and communications relay. The Zephyr can serve as a network extension node, providing 5G, Link 16, MESH, and optical communications relay from the stratosphere. Direct-to-device mobile connectivity is a potential mission, which could restore communications following natural disasters or extend coverage across remote and geographically dispersed regions.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set at the Ground Control Station.

**Launch files** — N/A (proprietary HAPS software).

**Dependencies** — AALTO Ground Control Station software. Payload-specific software (EO/IR, SAR, SIGINT, ELINT, communications). AALTOPORT launch and recovery infrastructure.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| AALTO flight control | Proprietary | AALTO | Control/Flight |
| Energy management software | Proprietary | AALTO | Power/Energy |
| BLOS communication software | Proprietary | AALTO | Comms/BLOS |
| Payload integration software | Proprietary | Various | Payload/Integration |
| Ground Control Station | Proprietary | AALTO | GCS |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, solar cell output, system health. Payload data: EO/IR imagery, SAR imagery, SIGINT/ELINT data, communications relay signals, APNT signals.

**Accepts** — Navigation commands (station-keeping location, retasking, route changes). Payload tasking commands. Mission duration and energy management parameters.

**Serves** — Persistent ISR services. Network extension and communications relay services. Deep sensing and long-range targeting services. APNT services.

**Executes** — Autonomous navigation. Station-keeping. Retasking. Persistent ISR over a local or regional footprint. Communications relay. Direct-to-device mobile connectivity. Environmental monitoring. Disaster management support.

**Extensions** — Two wing payload bays for interchangeable payloads. Payload agnostic design enables integration of new sensors and communication systems.

**Frame conventions** — Latitude, longitude, altitude (feet or metres). NED for navigation. FRD for body. Airspeed in knots or m/s.

**Units** — SI and aviation standard. Metres, feet, nautical miles, knots, kilograms, watts, volts.

---

## Model

**URDF / Xacro** — Not applicable (proprietary HAPS platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Solar cell and battery performance characterised through flight testing. Flight control system calibrated for stratospheric conditions.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and energy management. The high aspect ratio wing and lightweight airframe present unique aeroelastic challenges at stratospheric altitudes, where the air density is low and the Reynolds number is very low. The flight control system accounts for these effects.

**Sensor transforms** — Payloads mounted in the two wing bays. EO/IR, SAR, and communications payloads positioned for optimal field of view and coverage.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of solar cells, batteries, motors, and flight control system.

**Integration** — Payload integration in the wing bays. Flight control system verification. BLOS communication link verification. Energy management system verification.

**Field** — 2018 test flight: 26 days endurance, dawn altitude of 60,000 ft, highest altitude of 71,140 ft, longest flight duration of an aircraft ever made without refuelling. 2020 flight campaign: aircraft agility, control, and operations; demonstrated take-off, climb, cruise, upgraded flight control, and descent phases followed by successful landings. 2025 record flight: 67 days, six hours and 52 minutes; launched from Kenya, travelled into Australian airspace, crossed the Intertropical Convergence Zone twice, passed through seven flight information regions. Spain flight campaign (2026): demonstrating readiness of the complete Zephyr system.

**Endurance** — Record 67 days, six hours and 52 minutes (2025). Previous record 64 days. 2018 record 26 days. Target mission duration up to 150 days. Operational altitude 60,000–75,000 ft.

**Environmental** — Stratospheric operations: temperatures down to −80 °C, low atmospheric pressure, high solar irradiance, ozone exposure. Tropospheric transit during ascent and descent: wind shear, turbulence, icing conditions. Launch and recovery operations are weather-dependent.

**Known limitations** — The Zephyr is a stratospheric platform, not a tactical drone; it operates at 60,000–75,000 ft, which means it cannot provide the same resolution or persistence as a low-altitude platform for localised tactical operations. It is payload-limited: 8 kg total capacity across two wing bays, which constrains the size and power of sensors and communication systems. It is solar-powered, which means its endurance and altitude performance depend on latitude, season, and solar irradiance. It requires a dedicated launch and recovery site (AALTOPORT) with prepared surface and favourable weather. It is not stealth; it is a slow, high-altitude aircraft that is vulnerable to air-to-air missiles and high-altitude air defence systems in contested airspace. The 67-day record flight required significant international regulatory coordination; routine operations in multiple jurisdictions will require sustained regulatory engagement.

---

## Log

**Build history** — Zephyr developed by Airbus, commercialised by AALTO (Airbus subsidiary, created 2023). Over 10 Zephyr 8B models produced. Zephyr 8C production model planned. AALTO employs approximately 220 people. AALTOPORT established in Kenya. UK Civil Aviation Authority certification journey underway. Spain flight campaign (2026). 2018 record flight: 26 days. 2025 record flight: 67 days, six hours, 52 minutes.

**Open issues** — Certification with UK Civil Aviation Authority. Expansion of operational footprint in Kenya. Regulatory coordination for multi-jurisdiction flights. Payload integration for new sensors and communication systems (SIGINT, ELINT, APNT, 5G, Link 16). Battery longevity and energy management for 150-day missions. Vulnerability to air defence in contested airspace.

**Changelog** — Zephyr 8B: current production model, over 10 produced. Zephyr 8C: improved production model planned. 2018: 26-day record. 2025: 67-day record. 2026: Spain flight campaign.

**Lessons learned** — The combination of solar cells, lithium-sulphur batteries, and lightweight composite construction enables multi-month stratospheric endurance. The “Stratospace” is a new operational domain between conventional airspace and satellites, offering persistence comparable to satellites with the flexibility of drones. Payload agnosticism is essential for multi-mission capability; the Zephyr can carry EO/IR, SAR, SIGINT, ELINT, APNT, and communications payloads without airframe redesign. International regulatory coordination is a critical enabler for HAPS operations; the 2025 record flight required cooperation across seven flight information regions. The Zephyr’s affordability and attritability relative to other HAPS options make it suitable for sustained operations.

**Cost actual** — Not publicly disclosed. The Zephyr is positioned as “affordable, attritable” relative to other larger HAPS options. Unit cost and operational cost are not publicly available.

---

## Status

**Condition** — operational. Pre-commercial operational readiness. Over 10 Zephyr 8B models produced. AALTO working towards certification and global commercialisation.

**Blockers** — UK Civil Aviation Authority certification. Expansion of operational footprint. Payload integration for new sensors.

**Next steps** — Continue flight testing in Spain. Expand Kenyan operating base. Continue UK CAA certification journey. Integrate new payloads (SIGINT, ELINT, APNT, 5G, Link 16). Demonstrate 150-day mission endurance. Expand commercial services (environmental monitoring, direct-to-device mobile connectivity, disaster management support). Military applications: deep sensing, long-range targeting, indications and warning, network extension.

---

**Note on this Shell:** The zephyr is a distinct class in the library: a solar-powered stratospheric HAPS designed for multi-month persistence in the “Stratospace” between conventional airspace and satellites. Unlike the evo-le (8-hour VTOL ISTAR), the raybird (24–28-hour tactical reconnaissance), the seaguardian (40-hour maritime MALE), or the akinci (24-hour MALE UCAV), the Zephyr operates for months, not hours. It combines the persistence of a geostationary satellite with the flexibility of a drone, offering satellite-like communications and Earth observation services with greater image granularity over long periods without interruption. The 2025 record flight of 67 days, six hours and 52 minutes exceeds any other aircraft endurance without refuelling. Its 8 kg payload capacity across two wing bays limits sensor size, but its stratospheric altitude provides a wide field of regard and a stable platform for persistent ISR, communications relay, and deep sensing. The Zephyr is not a tactical platform; it is a strategic persistence asset that operates in a domain that is only now being operationalised. This Shell is the reference for a solar-powered stratospheric HAPS with multi-month endurance, payload agnosticism, and BLOS control from anywhere in the world.
