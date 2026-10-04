# spot

**Class:** legged<br>
**Generation:** 1<br>
**Version:** 5.2.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Boston Dynamics<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Commercial quadruped robot platform for industrial inspection, autonomous patrol, hazardous-site data collection, and mobile manipulation. Uses articulated legs to climb stairs, cross uneven terrain, and position sensors around industrial equipment. The Spot Arm adds mobile manipulation and equipment interaction capabilities.<br>
**Environment** — Indoor and outdoor. IP54 rated (rain and dust protected, not submersible). Operating temperature −20 °C to +45 °C. Storage temperature −40 °C to +70 °C. Maximum slope ±30°. Maximum step height 300 mm.<br>
**Mission** — Autonomous inspection, mapped patrols, obstacle avoidance, repeatable data capture, and remote operation in hazardous or unfamiliar areas. Deployed across energy, manufacturing, construction, public safety, and research organisations.<br>
**Operator** — Single operator via tablet (Samsung tablet or controller), web interface, or API. Supports autonomous Autowalk missions, semi-autonomous walks, and remote operation.<br>
**Reusability** — Commercial platform. Not a DIY build. Configurable with payloads, arm, and software subscriptions.

---

## Spec

**Physical** — Net weight 33.8 kg with battery. Length 1100 mm. Width 500 mm. Default walking height 610 mm. Max walking height 700 mm. Min walking height 520 mm. Sitting height 191 mm. The Spot Arm adds 8 kg, bringing total to approximately 41.8 kg with arm. Payload mounting uses M5 T-slot rails. Maximum recommended payload width 190 mm.<br>

**Kinematic** — 12 degrees of freedom (3 per leg). Quadruped configuration with articulated legs. Capable of walking, trotting, climbing stairs, and traversing uneven ground. Max nominal speed 5.8 km/h (1.6 m/s). The Spot Arm adds 6 DOF plus gripper, with 984 mm reach and 1800 mm maximum reach height.<br>

**Dynamic** — Payload capacity 14 kg (30.9 lbs) on body mounting rails. Max power per payload port 150 W. Spot Arm: 11 kg max lift, 5 kg continuous lift at 0.5 m extension, 25 kg max drag on carpet. Gripper aperture 175 mm, clamp force 130 N peak. Step height 300 mm. Maximum slope ±30°.<br>

**Power** — Battery capacity 564 Wh. Max battery voltage 58.8 V. Typical runtime approximately 90 minutes (varies with payload and environmental conditions). Standby time 180 minutes. Battery mass 5.2 kg. Spot Power Supply output 400 W. Max charge current 7 A. Charge time via Spot Dock at 25 °C: approximately 50 minutes for 80% charge, 2 hours for 100%. Charge time via Spot Power Supply: approximately 1 hour. Batteries can be swapped without tools but are not hot-swappable in the traditional sense; a direct charger connection to the robot enables continuous operation during battery swap.<br>

**Thermal** — Passive cooling. Operating temperature −20 °C to +45 °C.<br>

**Environmental** — IP54 (rain and dust protected). Storage temperature −40 °C to +70 °C. Not for submergence or operation in heavy rain beyond IP54 limits.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build.

| Component | Notes |
|:---|:---|
| Boston Dynamics Spot base unit | 33.8 kg with battery, IP54, 12 DOF |
| Spot Battery | 564 Wh, 5.2 kg, swappable |
| Spot Power Supply | 400 W output, 7 A max charge |
| Spot Dock (optional) | Autonomous charging station |
| Spot Arm (optional) | 6 DOF + gripper, 8 kg, 984 mm reach |
| Spot Cam+ (optional) | 30x optical zoom PTZ + radiometric thermal |
| Spot Cam+IR (optional) | Adds spherical camera and thermal |
| Spot EAP (Enhanced Autonomy Payload) | Velodyne VLP-16 LiDAR + Spot CORE I/O GXP |
| Spot CORE I/O | Onboard compute with 5G/LTE modem, CBRS support, two Ethernet ports |
| Spot GXP | Payload breakout: 5V/12V/24V regulated power, RJ45 Ethernet |
| Tablet controller | Samsung tablet with Spot app |
| Spot Enterprise software | Orbit fleet management, Autowalk, data capture |
| Spot Care | One year service and support, damage protection |

**Structure** — Articulated quadruped with 12 degrees of freedom. Each leg has three joints. Body houses the battery, compute, sensors, and payload ports. Two payload ports on the back provide power and communication through DB25 connections. Mounting rails provide mechanical attachment.<br>

**Actuation** — Proprietary electric motors with high-torque density. Each leg joint is independently actuated. No hydraulic components. All-electric platform.<br>

**Locomotion** — Legged quadruped. Walks, trots, climbs stairs, traverses uneven terrain, and recovers from falls autonomously. Max speed 1.6 m/s.<br>

**Manipulation** — Optional Spot Arm: 6 DOF plus gripper, 984 mm reach, 11 kg max lift, 5 kg continuous lift at 0.5 m extension. Gripper with 175 mm aperture and 130 N peak clamp force. Capable of opening doors, manipulating objects, and semi-autonomous operation.<br>

**Power system** — 564 Wh lithium-ion battery, 58.8 V max. Swappable without tools. Charging via Spot Power Supply (1 hour to full) or Spot Dock (50 min to 80% at 25 °C). Hot-swap capability available when robot is connected to charger during battery swap.<br>

**Wiring** — Internal only. Payload ports provide unregulated DC 35–58.8 V at 150 W per port. Gigabit Ethernet passthrough to robot. Time synchronization and safety system integration available via payload ports.<br>

**Custom parts** — None. All components are Boston Dynamics proprietary or certified third-party. Payloads mount via M5 T-slot rails and DB25 ports.<br>

**Fasteners** — Proprietary. Not user-serviceable.<br>

**Tools required** — None for assembly. Tablet controller included. Standard tools for payload mounting.

---

## Systems

**Manifest** — Boston Dynamics proprietary firmware and SDK ecosystem with ROS 2 support.<br>

**Firmware** — Boston Dynamics proprietary firmware. Software version 5.2 current as of September 2026. Regular OTA updates. Firmware managed via Spot app and Orbit platform.<br>

**Middleware** — Spot SDK (Python, C++, gRPC API). `spot_ros2` ROS 2 driver package bridges the Spot SDK to ROS 2 Humble on Ubuntu 22.04, supported on both ARM64 and AMD64 platforms. The `spot_driver` package exposes topics, services, and actions for control and state information including images. Data conversion system provides bidirectional translation between Spot SDK protobuf messages and ROS 2 message types. Docker image available for ready-to-run ROS 2 Humble with Spot driver installed. Experimental support for RMW Zenoh middleware.<br>

**Perception** — Five pairs of stereo cameras providing 360° field of view: front-left, front-right, left, right, and rear. Camera functions: black-and-white or color fisheye, range (depth), and infrared. Terrain sensing range 4 m. Optional Spot Cam+ adds 30x optical zoom PTZ camera and radiometric thermal camera. Spot Cam+IR adds spherical camera (360° × 170° view). Spot EAP adds Velodyne VLP-16 LiDAR with 100 m range and 360° horizontal FOV, 30° vertical FOV. LiDAR increases sensing range from 2–4 m to approximately 120 m.<br>

**Control** — Proprietary whole-body controller. Joint-level API available for reinforcement learning and custom behavior development. Autowalk missions enable autonomous navigation using mapped routes. Obstacle avoidance and repeatable data capture supported.<br>

**Planning** — Autowalk: create maps, waypoints, and edges for autonomous navigation. Orbit software schedules missions, manages fleets, and associates readings with facility assets. Mission planning via tablet and web interface. AI-powered visual inspection learning (AIVI-Learning) integrated with Google Gemini Robotics for higher-level reasoning and complex visual analysis.<br>

**Learning** — Joint-level API enables reinforcement learning for unique behaviors and locomotion modes. Sim-to-real transfer supported with Webots and other simulation environments. Visuomotor policy learning demonstrated with flow-matching policies on Spot. Open-vocabulary object retrieval demonstrated with VLM and LLM reasoning over 3D scene graphs.<br>

**Teleoperation** — Tablet controller with point-and-walk interface. Web interface for remote operation. API for programmatic control. Semi-autonomous walks and tasks through remote operation. Autonomous capability for mapped patrols.<br>

**Safety** — Safety system integration via payload ports. Fall recovery autonomous. Emergency stop via controller. Motor lockout for maintenance. Obstacle avoidance integrated into autonomy stack. IP54 protection for rain and dust.<br>

**Logging** — Data capture during autonomous missions. Orbit associates readings with facility assets. Sensor data available via SDK and ROS 2 topics. Images, point clouds, and thermal data logged for inspection reports.<br>

**Networking** — 2.4 GHz / 5 GHz WiFi and Ethernet. Built-in 5G/LTE modem on Spot CORE I/O. CBRS support for private LTE networks. Two Ethernet ports on CORE I/O. Gigabit Ethernet passthrough via payload ports.<br>

**Config files** — Managed via Spot app and Orbit platform. No user-accessible firmware config files.<br>

**Launch files** — `spot_ros2` provides launch files for bringup, driver, and visualization.<br>

**Dependencies** — Spot SDK (Python, C++, gRPC). `spot_ros2` (ROS 2 Humble). Orbit software (fleet management). Spot app (tablet control). Web interface. Docker (optional). Google Gemini Robotics integration (optional).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Spot SDK | 5.0.1+ | Boston Dynamics | SDK |
| spot_ros2 | Latest | github | Middleware/ROS2 |
| ROS 2 | Humble | ros.org | Middleware/ROS2 |
| Ubuntu | 22.04 | ubuntu.com | OS/Linux |
| Orbit | 5.2+ | Boston Dynamics | Fleet management |
| Spot app | 5.2+ | Boston Dynamics | Ground control |
| Web interface | 5.2+ | Boston Dynamics | Remote operation |
| Google Gemini Robotics | ER 1.6 (optional) | Google | AI integration |
| Webots | Latest | cyberbotics.com | Simulation |

---

## Interface

**Emits** — Joint states, IMU data, camera feeds (5 stereo pairs), depth images, telemetry (battery, joint temperatures, error status). Via ROS 2: standard topics for images, joint states, odometry, TF tree. Via SDK: protobuf messages for all state and sensor data.<br>

**Accepts** — Tablet controller commands. Web interface commands. API commands via SDK. High-level velocity and pose commands. Autowalk mission definitions. Payload commands via SDK.<br>

**Serves** — Arming, calibration, parameter access via Spot app and Orbit.<br>

**Executes** — Walking, trotting, stair climbing, Autowalk missions, point-and-walk navigation, arm manipulation, door opening, object pickup and carrying.<br>

**Extensions** — Two payload ports (DB25) with 150 W per port, Ethernet, time sync, safety integration. Spot Arm via dedicated port. Spot Cam+ / Cam+IR via payload port. Spot EAP with Velodyne LiDAR. Third-party payloads via PSDK.<br>

**Frame conventions** — ROS 2 TF tree available via `spot_ros2`. `body` frame at robot center. Leg frames for each joint. `arm_link` frames for Spot Arm. Camera frames for each stereo pair.<br>

**Units** — SI.

---

## Model

**URDF / Xacro** — Available via `spot_ros2`. Includes all joint limits, link masses, and collision geometry. Visual meshes provided.<br>

**SDF** — Available for Webots and Gazebo simulation. Webots virtual environment demonstrated for locomotion algorithm validation.<br>

**Calibration** — Factory calibrated. Calibration recommended twice per year. Camera intrinsics and extrinsics set at factory. IMU bias and joint zero offsets set at factory. Recalibration via Boston Dynamics service.<br>

**Dynamics** — Proprietary. Joint torque limits, velocity limits, and motor constants available via SDK. Joint-level API provides access for reinforcement learning and custom controller development.<br>

**Sensor transforms** — Camera mount positions and orientations documented in SDK. IMU at body center. LiDAR mount position (when using EAP) documented in payload specifications.<br>

**Collision geometry** — Provided in URDF. Simplified geometric primitives for real-time collision checking.<br>

**Visual geometry** — Provided in URDF. High-fidelity meshes for visualization.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery. Boot time approximately 5 minutes.<br>

**Integration** — Spot SDK connection. `spot_ros2` bringup on Ubuntu 22.04 with ROS 2 Humble. Payload port verification (power, Ethernet, time sync). Spot Arm integration. Camera feed verification. LiDAR data verification (EAP). Thermal camera verification (Cam+).<br>

**Field** — Walking and trotting on flat and uneven surfaces. Stair climbing. Autowalk mission execution. Obstacle avoidance. Spot Arm manipulation tasks (door opening, object pickup). Thermal inspection at industrial sites. LiDAR mapping. Remote operation in hazardous environments.<br>

**Endurance** — 90 minutes typical runtime. 180 minutes standby. Continuous operation with battery swap and charger connection. Payload reduces runtime; approximately 60 minutes when powering payloads.<br>

**Environmental** — IP54 verified. Operating temperature −20 °C to +45 °C. Tested in rain and dust. Not submersible.<br>

**Known limitations** — Not submersible (IP54 only). Battery not hot-swappable in the traditional sense; swap requires charger connection or shutdown. Proprietary battery format. Payload width maximum 190 mm. mmWave radar not applicable (different platform). Runtime reduced with payloads. Calibration recommended twice per year.

---

## Log

**Build history** — Spot commercially available June 2020. Software version 5.2 released September 2026 with AI-powered visual inspection (AIVI-Learning) and Google Gemini Robotics integration. Regular updates via OTA. Expanded reseller and technology partnerships (Createc for nuclear sector, August 2026). Deployed at Mariana Minerals Copper One facility (July 2026).<br>

**Open issues** — Battery hot-swap limitations for extended missions. Proprietary battery format. Payload width constraint. Calibration frequency requirement.<br>

**Changelog** — Version 5.2 (September 2026): AI visual inspection learning, Gemini Robotics integration. Earlier versions: Autowalk enhancements, Orbit fleet management, arm manipulation improvements.<br>

**Lessons learned** — N/A (commercial product).<br>

**Cost actual** — Base Spot Explorer: approximately $75,000. Spot + Arm: $95,000–$140,000. Enterprise deployment (3-year): $165,000–$195,000. Public Safety Kit: $250,000 MSRP. Data center deployments: $175,000–$300,000 depending on configuration. Contact sales for current pricing. Authorized distributors available.

---

## Status

**Condition** — operational.<br>

**Blockers** — None. Commercial availability. Contact sales for configuration and pricing.<br>

**Next steps** — Configuration selection (arm, cameras, LiDAR, compute). Orbit software subscription. Operator training (available by request). ROS 2 integration via `spot_ros2`. Payload selection based on mission profile (inspection, manipulation, mapping). Deployment planning with Orbit fleet management.

---
