# ghostbat

**Class:** aerial (collaborative combat aircraft / loyal wingman)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Boeing Defence Australia / Royal Australian Air Force  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Uncrewed Collaborative Combat Aircraft (CCA) designed to operate alongside crewed fighters as a “loyal wingman.” The Ghost Bat extends the sensor range, weapons capacity, and survivability of crewed platforms by acting as an attritable, networked teammate that can fly ahead of, alongside, or independently of manned aircraft. It is designed for air-to-air combat, strike, intelligence, surveillance, and reconnaissance (ISR), and electronic warfare. The aircraft is not a drone in the traditional sense; it is a collaborative combat aircraft, meaning it operates as part of a networked force with human operators providing mission-level command and authorization for weapons release. The Royal Australian Air Force (RAAF) will become the first air arm in the world to field an advanced CCA when the MQ-28 enters service in 2028.

**Environment** — High subsonic to supersonic flight envelope, compatible with fighter aircraft speeds. Operating altitude up to 40,000 feet. Range exceeding 2,000 nautical miles. Designed for operation in contested airspace with low observability characteristics. Not for operations in icing conditions or severe turbulence without additional protection. The aircraft is designed for expeditionary deployment from austere bases.

**Mission** — Collaborative combat, air-to-air engagement, strike, ISR, electronic warfare, and force multiplication. The Ghost Bat has demonstrated autonomous find-fix-target missions, in which it autonomously detected, tracked, and designated aerial targets within an assigned area. In December 2025, an MQ-28 destroyed a jet-powered drone target with an AIM-120 fired at the Woomera test range in South Australia, with an operator aboard an RAAF E-7A Wedgetail controlling the CCA and authorizing the engagement, while an F/A-18F Super Hornet provided targeting data across the networked force.

**Operator** — Single Launch and Recovery Operator and a Mission Execution Operator, both stationed within a Ground Control Station. The aircraft can also be controlled from airborne assets, facilitating seamless integration with existing Air Force platforms. Beyond Line of Sight (BLOS) communication links enable the MQ-28 custodian to operate from a crewed aircraft, ground station, or naval vessel at unlimited standoff distances.

**Reusability** — Commercial defence platform with a spiral upgrade program. The aircraft is designed for ease of operation and manufacturing, with a digital-first development approach that relies on modeling and simulation rather than extensive flight testing. Production is established at Toowoomba, Queensland, which will initially build Block 2 aircraft.

---

## Spec

**Physical** — Length 11.7 m. Height 2.0 m. Wingspan 7.3 m (Block 2 and Block 3; increased from 6 m on Block 1). Maximum takeoff weight 5,443 kg (12,000 lb), increased from 4,535 kg (10,000 lb) on Block 1. Useful payload capacity >2,040 kg (4,500 lb). The airframe is constructed from advanced composite materials for low observability and weight efficiency. The 25% larger wing on Block 2 and Block 3 allows the aircraft to carry an additional 900 kg (2,000 lb) of fuel, stores, and mission payloads compared to baseline versions.

**Kinematic** — Single jet engine driving the aircraft to speeds compatible with fighter aircraft. The Ghost Bat is a tailless, blended wing body design optimized for low observability and aerodynamic efficiency. Control surfaces are actuated by electromechanical actuators. The aircraft is designed for autonomous operation with human-in-the-loop authorization for weapons release. The digital-first development approach means the flight control laws are validated primarily in simulation, with flight testing confirming the modeling results.

**Dynamic** — Range exceeding 2,000 nautical miles. Speeds compatible with fighter aircraft (high subsonic to supersonic). Operating altitude up to 40,000 feet. The Block 2’s 25% larger wing provides greater fuel capacity and extended range. The Block 3 is considering adapting the drone for aerial refueling to further enhance its reach. Three back-to-back sorties during the Valiant Shield exercise demonstrated a turnaround time between flights of just 19 minutes.

**Power** — Single jet engine. Specific engine model and thrust class not publicly disclosed. The aircraft carries sufficient fuel for a range exceeding 2,000 nautical miles. Power distribution includes redundant buses for flight-critical avionics, weapons, and mission systems. The MQ-28 is designed for ease of maintenance and rapid turnaround, as demonstrated by the 19-minute turnaround time between sorties.

**Thermal** — Low visual and heat signature characteristics are confirmed for the MQ-28. The tailless, blended wing body design reduces radar cross-section, and the engine exhaust is routed to minimise infrared signature. Specific thermal management details are not publicly disclosed.

**Environmental** — Designed for operation in contested airspace alongside crewed fighters. The aircraft is not rated for icing conditions without additional protection. Operating temperature range not publicly specified, but the aircraft is designed for expeditionary deployment from austere bases in the Indo-Pacific region.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The aircraft is purchased as a complete system with ground control station, mission systems, and weapons integration.

| Component | Notes |
|:---|:---|
| MQ-28 Ghost Bat airframe | Composite construction, 11.7 m length, 7.3 m wingspan, 5,443 kg MTOW |
| Jet engine | Single engine, speed compatible with fighter aircraft |
| Modular nose section | Mission-configurable, accommodates interchangeable sensors and payloads |
| Internal weapons bays | Two internal weapons stations, each capable of one AMRAAM or two SDBs |
| External weapons stations | Provision for three external weapons stations |
| Skyward IRST sensor | Infrared search-and-track, Leonardo |
| Eaton weapons launch and release systems | Partner for weapons integration |
| BLOS communication links | SATCOM for beyond-line-of-sight control |
| Government Reference Architecture software | Open standards for weapons, payloads, command and control, and mission autonomy |
| Ground Control Station | Launch and Recovery Operator + Mission Execution Operator stations |
| Airborne control interface | Control from crewed aircraft (e.g., E-7A Wedgetail) |

**Structure** — Tailless, blended wing body composite airframe with a low observability profile. The internal weapons bays are longer on Block 2, accommodating up to four Small Diameter Bombs or two missiles the size of the AIM-120 AMRAAM. The modular, missionised nose provides enhanced payload configuration options and supports insertion of third-party capability. The aircraft is designed for ease of operation and manufacturing, with a simple, low-cost design that can be produced at scale.

**Actuation** — Single jet engine. Control surfaces actuated by electromechanical actuators. The aircraft has demonstrated speeds compatible with fighter aircraft, meaning it can keep pace with platforms like the F-35 and F-15EX during collaborative operations.

**Locomotion** — Fixed-wing flight. High subsonic to supersonic cruise, compatible with crewed fighter aircraft. The aircraft can be controlled from a ground station, a crewed aircraft, or a naval vessel via BLOS communication links.

**Manipulation** — None. The aircraft is a weapons and sensor platform. The internal weapons bays and external weapons stations provide the effector capability: AIM-120 AMRAAM air-to-air missiles, GBU-39/B Small Diameter Bombs, and potentially GBU-53/B StormBreaker glide bombs. Boeing is in talks with MBDA about launching a Meteor air-to-air missile from the MQ-28; fit checks have been conducted.

**Power system** — Single jet engine driving an integrated generator that provides electrical power to the avionics, sensors, and weapons. Specific power generation capacity not publicly disclosed. The aircraft carries sufficient fuel for a range exceeding 2,000 nautical miles.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular nose and weapons stations. The Government Reference Architecture software uses open standards to enable operators to tailor weapons, payloads, command and control, and mission autonomy.

**Custom parts** — None. All components are Boeing proprietary or certified third-party. The open architecture enables integration of third-party capability via the missionised nose and Government Reference Architecture software.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting, weapons loading, and field maintenance.

---

## Systems

**Manifest** — Boeing proprietary software stack with Government Reference Architecture compliance and open standards.

**Firmware** — The aircraft runs a digital-first flight control system with autonomous operation capability. In June 2025, an MQ-28 conducted find-fix-target missions in which it autonomously detected, tracked, and designated aerial targets within an assigned area. In December 2025, an MQ-28 operated autonomously during the final attack phase of a networked engagement.

**Middleware** — Boeing proprietary. BLOS communication links enable control from a crewed aircraft, ground station, or naval vessel at unlimited standoff distances. The aircraft can be controlled from an RAAF E-7A Wedgetail airborne early warning and control aircraft, with an operator aboard authorizing the engagement while an F/A-18F Super Hornet provided targeting data across the networked force.

**Perception** — Modular missionised nose with interchangeable sensors and payloads. Confirmed sensor partners include Leonardo Skyward infrared search-and-track (IRST) sensors. The aircraft has demonstrated autonomous detection, tracking, and designation of aerial targets. Specific radar, EO/IR, and electronic warfare sensor details are not publicly disclosed.

**Control** — The flight control system manages autonomous navigation, collaborative operations, and weapons employment with human authorization. The Ghost Bat has demonstrated networked collaborative combat: an operator aboard an E-7A Wedgetail controlled the CCA and authorized the engagement, while an F/A-18F Super Hornet provided targeting data. The aircraft operated autonomously during the final attack phase. This is the defining capability of a collaborative combat aircraft: it is not fully autonomous in weapons release, but it is autonomous in flight, navigation, and target tracking.

**Planning** — Autonomous route planning and collaborative mission execution. The BLOS communication links enable the MQ-28 custodian to operate from a crewed aircraft, ground station, or naval vessel at unlimited standoff distances, enabling distributed operations across a networked force. The Government Reference Architecture software enables operators to tailor weapons, payloads, command and control, and mission autonomy to suit their operational requirements.

**Learning** — None publicly disclosed. The aircraft uses classical control, sensor fusion, and autonomous target tracking. No learning-based control is mentioned for safety-critical weapons release.

**Teleoperation** — Two-person ground control station (Launch and Recovery Operator + Mission Execution Operator). The aircraft can also be controlled from airborne assets, including the E-7A Wedgetail. The BLOS communication links enable control from a crewed aircraft, ground station, or naval vessel at unlimited standoff distances. The operator provides mission-level command and authorizes weapons release; the aircraft handles flight control, navigation, and target tracking autonomously.

**Safety** — Human-in-the-loop for weapons release. The operator aboard the E-7A Wedgetail authorized the engagement of a jet-powered drone target with an AIM-120 fired from the MQ-28. The aircraft is designed with low observability characteristics and survivability upgrades to support more flexible mission concepts and distribute operational risk. The triple-redundant autopilot system (in the Bayraktar TB2, a comparable MALE UCAV) provides fault tolerance and high mission safety; the MQ-28 likely has a similar or more advanced redundancy architecture.

**Logging** — Mission data, sensor data, and weapons employment logs. Specific logging details not publicly disclosed. The networked engagement in December 2025 involved an E-7A Wedgetail, an F/A-18F Super Hornet, and the MQ-28, indicating that mission data is shared across the networked force in real time.

**Networking** — BLOS communication links for beyond-line-of-sight control from a crewed aircraft, ground station, or naval vessel. The aircraft has demonstrated networked collaborative combat with E-7A Wedgetail and F/A-18F Super Hornet platforms. Government Reference Architecture software with open standards enables interoperability with Boeing and non-Boeing platforms for allied forces.

**Config files** — Proprietary. No user-accessible config files. The Government Reference Architecture software uses open standards to enable operators to tailor weapons, payloads, command and control, and mission autonomy.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Boeing ground control station software. E-7A Wedgetail airborne control interface. F/A-18F Super Hornet targeting data interface. Leonardo Skyward IRST. Eaton weapons launch and release systems. MBDA Meteor missile integration (in progress). Government Reference Architecture software.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Boeing flight control | Proprietary | Boeing | Control/Flight |
| Government Reference Architecture | Proprietary | Boeing | Architecture/Open |
| Mission autonomy software | Proprietary | Boeing | Autonomy/Mission |
| Skyward IRST software | Proprietary | Leonardo | Sensors/IRST |
| Weapons integration software | Proprietary | Eaton / MBDA | Weapons/Integration |
| E-7A Wedgetail control interface | Proprietary | Boeing | Command/Control |
| F/A-18F Super Hornet data link | Proprietary | Boeing | Command/Control |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, airspeed, altitude, fuel state, system health. Sensor data: IRST tracks, radar tracks, EO/IR imagery. Weapons status. Networked force data.

**Accepts** — Navigation commands (waypoints, routes, collaborative mission profiles). Weapons authorization (human-in-the-loop). Sensor tasking commands. Payload commands. Command from airborne assets (E-7A Wedgetail, F/A-18F Super Hornet) or ground station.

**Serves** — Collaborative combat services. Sensor data sharing with networked force. Weapons employment services (with human authorization).

**Executes** — Autonomous navigation. Collaborative combat operations alongside crewed fighters. Find-fix-target missions. Air-to-air engagement with AIM-120. Strike with Small Diameter Bombs. ISR. Electronic warfare.

**Extensions** — Modular missionised nose for interchangeable sensors. Three external weapons stations. Internal weapons bays (2× AMRAAM or 4× SDB). Aerial refueling capability (Block 3, under consideration). Meteor missile integration (in progress). Third-party capability via Government Reference Architecture software.

**Frame conventions** — Military grid reference system (MGRS) for position. NED for navigation. FRD for body. Airspeed in knots or Mach. Altitude in feet MSL.

**Units** — SI and military standard. Meters, nautical miles, knots, feet, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for IRST and other payloads. Weapons calibration for internal and external stations.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and simulation. The digital-first development approach means flight testing is essentially a validation of modeling and results.

**Sensor transforms** — IRST and other sensors mounted in the modular nose. Weapons stations on internal bays and external hardpoints.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — Payload integration in the modular nose. Weapons integration (internal bays and external stations). BLOS communication link verification. Networked force integration with E-7A Wedgetail and F/A-18F Super Hornet.

**Field** — Autonomous find-fix-target mission (June 2025): detected, tracked, and designated aerial targets autonomously. Live weapons engagement (December 2025): destroyed a jet-powered drone target with an AIM-120 at Woomera test range, with operator authorization from an E-7A Wedgetail and targeting data from an F/A-18F Super Hornet. Valiant Shield exercise (June–July 2026): nine sorties from Rota, including operations with U.S. Air Force F-35s and F-15EXs; three back-to-back sorties with 19-minute turnaround time. U.S. Navy cooperation: three sorties from Naval Air Station Point Mugu, California.

**Endurance** — Range exceeding 2,000 nautical miles. The Block 3 is considering aerial refueling to further enhance reach.

**Environmental** — Designed for operation in contested airspace alongside crewed fighters. Low observability characteristics confirmed. Not for icing conditions without additional protection.

**Known limitations** — The MQ-28 is not a fully autonomous weapons system; human authorization is required for weapons release. The aircraft is designed for collaborative operations with crewed fighters, not for independent air superiority missions. The Block 3 variant with internal weapons bays and potential aerial refueling is still in development; the Block 2 currently being produced does not use the internal weapons bay (a Block 2 aircraft carried an AIM-120 on an external pylon during weapons testing in late 2025). International sales are still in negotiation; Germany, Japan, and other Indo-Pacific nations have expressed interest, but no export orders have been confirmed. The aircraft relies on a networked force for targeting data; it is not designed to operate in a communications-denied environment without significant onboard autonomy.

---

## Log

**Build history** — MQ-28 Ghost Bat developed by Boeing Defence Australia and the Royal Australian Air Force. First flew in February 2021. Test fleet accumulated approximately 230 hours over 200 sorties. Eight Block 1 aircraft built. Block 2 aircraft with 25% larger wing, increased MTOW, and longer internal weapons bays. Nine Block 2 aircraft ordered by Australia. Block 3 with further improvements expected to enter production in 2029. Production facility established in Toowoomba, Queensland. International interest from Germany (industrial team with Rheinmetall, Rohde & Schwarz, Diehl Defence, Hensoldt), Japan, and other Indo-Pacific nations.

**Open issues** — Block 2 has yet to achieve operational capability. Internal weapons bay not used on Block 2; carried externally during testing. Aerial refueling capability under consideration for Block 3. Meteor missile integration in progress with MBDA; fit checks conducted but no schedule set for demonstration. Export sales not yet confirmed. Integration with non-Boeing command and control systems.

**Changelog** — Block 1: initial pre-production prototypes, 6 m wingspan, 10,000 lb MTOW. Block 2: 7.3 m wingspan, 12,000 lb MTOW, 4,500 lb useful load, longer internal weapons bays, modular missionised nose, BLOS communication links. Block 3: scalable internal weapons bay, wider wingspan, potential aerial refueling, Government Reference Architecture software upgrades.

**Lessons learned** — Digital-first development allows rapid iteration and validation of flight control laws through simulation, reducing the need for extensive and expensive flight testing. Collaborative combat is a team sport: the MQ-28’s most significant demonstrations involved an E-7A Wedgetail, an F/A-18F Super Hornet, and the MQ-28 operating as a networked force. The modular missionised nose and Government Reference Architecture software enable rapid integration of third-party capability, which is critical for international customers with sovereign requirements. The 19-minute turnaround time between sorties demonstrates that a CCA can generate sorties at a rate comparable to crewed fighters.

**Cost actual** — Not publicly disclosed. The MQ-28 is designed for ease of manufacturing and low-cost production relative to crewed fighters. Boeing Australia designed the Ghost Bat as a simple aircraft with ease of operation and manufacturing in mind. Unit cost is expected to be a fraction of a crewed fighter, enabling attritable operations.

---

## Status

**Condition** — operational (Block 2 in production; RAAF service entry planned for 2028).

**Blockers** — None. Production facility established. Block 2 yet to achieve operational capability.

**Next steps** — Block 2 operational capability for RAAF. Block 3 development with scalable internal weapons bay and potential aerial refueling. Meteor missile integration demonstration with MBDA. International sales campaigns in Germany, Japan, and Indo-Pacific nations. Continued networked force integration with E-7A Wedgetail, F/A-18F Super Hornet, F-35, and F-15EX. U.S. Air Force and U.S. Navy interest expressed.

---

**Note on this Shell:** The ghostbat is a distinct class in the library: a Collaborative Combat Aircraft (CCA) / loyal wingman designed to operate alongside crewed fighters as a networked teammate. Unlike the evo-le (long-endurance ISTAR UAS) or the raybird (tactical deep-reconnaissance UAS), the Ghost Bat is a combat aircraft designed for air-to-air engagement and strike, with speeds compatible with fighter aircraft and a range exceeding 2,000 nautical miles. Its defining capability is not autonomy in isolation, but collaboration: it has demonstrated networked engagement with an E-7A Wedgetail providing control and authorization, and an F/A-18F Super Hornet providing targeting data. The modular missionised nose and Government Reference Architecture software enable rapid integration of third-party capability, making it highly configurable for allied nations. The Block 2’s 25% larger wing and longer internal weapons bays increase range and payload capacity, while the Block 3 is expected to add aerial refueling for even greater reach. With RAAF service entry planned for 2028 and international interest from Germany, Japan, and the United States, the Ghost Bat is the reference for a combat-proven, networked, collaborative combat aircraft designed to fly alongside crewed fighters in contested airspace.
