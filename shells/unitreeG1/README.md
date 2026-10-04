# Unitree G1

**Class:** humanoid<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Unitree Robotics<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Humanoid robot platform for research, education, and embodied AI development. Walks, runs, jumps, and manipulates objects. Designed for imitation learning, reinforcement learning, and sim-to-real policy deployment.<br>
**Environment** — Indoor structured and unstructured. Lab, classroom, warehouse, home. Not IP-rated. Not for outdoor rain or extreme terrain. Operating temperature 0–40 °C.<br>
**Mission** — Locomotion research, manipulation research, human-robot interaction, education, and AI policy development. The G1 is positioned as the most accessible full-size humanoid for research, with the largest third-party ecosystem and ROS 2 support.<br>
**Operator** — Single operator via handheld remote controller. Higher-level autonomy via onboard compute and Unitree SDK. Supports imitation and reinforcement learning workflows.<br>
**Reusability** — Commercial platform. Not a DIY build. Configurable with optional hands, waist DOF, and compute modules.

---

## Spec

**Physical** — ~35 kg with battery. 1320 × 450 × 200 mm standing (H×W×D). 690 × 450 × 300 mm folded. Single leg length (thigh + shin) 0.6 m. Arm span ~0.45 m. Carbon fiber–aluminum composite joint structure with industrial-grade crossed roller bearings.<br>

**Kinematic** — 23 DOF base configuration, expandable to 43 DOF with optional dexterous hands and waist joints. Single leg: 6 DOF. Waist: 1 DOF (standard), expandable to 3 DOF (+2 optional). Single arm: 5 DOF. Hands: optional Dex3-1 three-finger force-controlled hand (7 active DOF: 3 thumb, 2 index, 2 middle) or two additional wrist DOF.<br>

**Dynamic** — Max running speed >2 m/s. Max knee joint torque 90 N·m (standard) or 120 N·m (EDU/Plus configurations). Arm max payload ~2 kg (standard) or ~3 kg (EDU). Capable of dynamic movements including standing up from prone, folding into compact positions, and rapid turning. Tested in dynamic reinforcement learning scenarios including single-leg hopping and 360° rotational jumps.<br>

**Power** — 13-cell lithium battery (13S, ~48 V nominal). 9000 mAh capacity with quick-release design. Charger 54 V 5 A. Runtime approximately 2 hours active.<br>

**Thermal** — Local air cooling system. Joint motors use low-inertia high-speed inner-rotor permanent magnet synchronous motors designed for better response speed and heat dissipation. Passive cooling for electronics.<br>

**Environmental** — Indoor and controlled outdoor. No IP rating. Not for rain, dust, or extreme terrain. Operating temperature 0–40 °C.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. Purchased as a complete system with configurable options.

| Component | Notes |
|:---|:---|
| Unitree G1 base unit | 23 DOF, ~35 kg, 1.32 m standing height |
| Joint actuators | Low-inertia high-speed inner-rotor PMSM, dual encoders per joint, industrial crossed roller bearings |
| Dex3-1 hands (optional) | 3-finger force-controlled, 7 active DOF per hand, optional multi-point tactile array |
| Waist DOF upgrade (optional) | +2 DOF (total 3 waist DOF) |
| Wrist DOF upgrade (optional) | +2 DOF per wrist |
| 9000 mAh smart battery | Quick-release, 13S |
| 54 V 5 A charger | Standard |
| Handheld remote controller | Included |
| Gantry | Included with EDU configurations |
| Compute module | 8-core high-performance CPU standard; optional 100 TOPS module (Orin-class) |
| Depth camera | Standard |
| 3D LiDAR | Standard |
| 4-microphone array | Standard |
| 5 W speaker | Standard |
| WiFi 6, Bluetooth 5.2 | Standard |

**Structure** — Humanoid form factor. Full joint hollow electrical routing for power and signal distribution through the joints. Carbon fiber–aluminum composite structure with industrial crossed roller bearings at each joint for high precision and load capacity.<br>

**Actuation** — Unitree self-developed micro servo motors. Low-inertia high-speed inner-rotor PMSM. Max joint torque 120 N·m. Dual encoder per joint for precise position and velocity feedback. Local air cooling for sustained operation.<br>

**Locomotion** — Bipedal walking and running. Max speed >2 m/s. Dynamic movements including standing from prone, compact folding, and rotational jumps. The G1+ variant (2026) features stronger joints and upgraded perception.<br>

**Manipulation** — Optional Dex3-1 three-finger force-controlled hands. Force-position hybrid control for precise object manipulation. Capable of grasping eggs, handling tools, and performing dexterous tasks.<br>

**Power system** — 13S lithium battery, 9000 mAh, quick-release. 54 V 5 A charger. 2-hour runtime.<br>

**Wiring** — Full joint hollow routing. Internal only. Not user-accessible.<br>

**Custom parts** — None. All components are Unitree proprietary or certified accessories.<br>

**Fasteners** — Proprietary. Not user-serviceable.<br>

**Tools required** — None for assembly. Standard tools for payload and accessory mounting.

---

## Systems

**Manifest** — Unitree SDK and ROS 2 ecosystem.<br>

**Firmware** — Unitree proprietary firmware. Regular OTA updates supported. Secondary development supported on EDU models for both upper and lower level control.<br>

**Middleware** — ROS 2 support confirmed. Unitree SDK provides Python and C++ APIs for joint control, sensor access, and locomotion commands. The G1 has the largest third-party ecosystem among research humanoids.<br>

**Perception** — Depth camera (standard). 3D LiDAR (standard). 4-microphone array (standard). 5 W speaker (standard). WiFi 6 and Bluetooth 5.2. Optional upgraded perception on G1+ variant.<br>

**Control** — Unitree proprietary whole-body controller. Joint-level control via SDK. Supports imitation and reinforcement learning workflows. Force-position hybrid control for manipulation. Model-based and learning-based locomotion controllers supported.<br>

**Planning** — Higher-level planning via onboard compute or external ROS 2 stack. Unitree provides development manuals and ecosystem support for building custom planners.<br>

**Learning** — Designed for imitation and reinforcement learning. The G1 supports training policies in simulation (Isaac Gym, MuJoCo) and deploying to hardware. Unitree's UnifoLM (Unitree Robot Unified Large Model) initiative aims to provide a unified foundation model for the platform. Depth-based reinforcement learning locomotion and whole-body control examples are supported.<br>

**Teleoperation** — Handheld remote controller included. Higher-level teleoperation via SDK and ROS 2. Supports external motion capture integration for imitation learning data collection.<br>

**Safety** — Emergency stop via remote controller. Joint torque and velocity limits enforced in firmware. Fall detection and safe shutdown. The manufacturer explicitly warns that the robot is structurally complex with extremely powerful dynamics and that users should maintain adequate safety distance.<br>

**Logging** — Joint states, IMU data, and sensor streams available via SDK. Data format compatible with LeRobot for imitation learning pipelines.<br>

**Networking** — WiFi 6 and Bluetooth 5.2 standard. Ethernet available via optional compute module.<br>

**Config files** — Managed via Unitree SDK and development environment. No user-accessible firmware config files.<br>

**Launch files** — Unitree SDK provides example launch files for ROS 2 integration.<br>

**Dependencies** — Unitree SDK (Python, C++). ROS 2 Jazzy or Humble. Optional: Isaac Lab for sim-to-real training. Unitree development manual and ecosystem support for EDU models.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Unitree SDK | Latest | Unitree | Middleware/SDK |
| ROS 2 | Jazzy or Humble | ros.org | Middleware/ROS2 |
| Unitree ROS 2 packages | Latest | github | Middleware/drivers |
| Isaac Lab (optional) | Latest | NVIDIA | Simulation/RL |
| MuJoCo (optional) | Latest | Google DeepMind | Simulation |
| LeRobot (optional) | Latest | Hugging Face | Learning |

---

## Interface

**Emits** — Joint states, IMU data, depth camera feed, LiDAR scan, microphone array audio. Telemetry: battery state, joint temperatures, error status.

**Accepts** — Remote controller commands. SDK commands for joint positions, velocities, torques, and whole-body locomotion. High-level velocity and pose commands.

**Serves** — Arming, calibration, parameter access via Unitree SDK.

**Executes** — Walking, running, turning, standing, sitting, manipulation via SDK.

**Extensions** — Optional hands, waist DOF, wrist DOF, compute modules.

**Frame conventions** — Unitree proprietary. ROS 2 TF tree available via SDK.

**Units** — SI.

---

## Model

**URDF / Xacro** — Provided by Unitree via SDK. Includes all joint limits, link masses, and collision geometry.

**SDF** — Available for simulation in Gazebo and Isaac Sim.

**Calibration** — Factory calibrated. Joint zero offsets and IMU bias set at factory. Recalibration via SDK.

**Dynamics** — Joint torque limits, velocity limits, and motor constants provided in SDK documentation. System identification models available for sim-to-real transfer.

**Sensor transforms** — Depth camera, LiDAR, and IMU mount positions documented in SDK.

**Collision geometry** — Provided in URDF and SDF.

**Visual geometry** — Provided in URDF and SDF.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — SDK connection, ROS 2 bring-up, joint control verification, sensor data verification.

**Field** — Walking and running on flat and uneven indoor surfaces. Dynamic movements including jumps and rotational turns. Manipulation tasks with Dex3-1 hands. Reinforcement learning policy deployment.

**Endurance** — ~2 hours active runtime. Joint temperature monitoring during sustained locomotion.

**Environmental** — Indoor and controlled outdoor. Not tested for rain, dust, or extreme temperature.

**Known limitations** — Not IP-rated. Not for outdoor rain or extreme terrain. The G1+ variant has stronger joints and upgraded perception, indicating the base model has known joint and perception limitations. Humanoid robots are described as being in an early stage of global exploration, and users are advised to understand the limitations of humanoid robots before purchasing. Industrial continuous operation not yet supported by base configurations.

---

## Log

**Build history** — G1 released May 2024. G1+ variant released September 2026 with stronger joints and upgraded perception. Regular firmware updates and ecosystem expansions.

**Open issues** — Industrial continuous operation not yet supported. Hand configurations vary by SKU. Regional pricing differences.

**Changelog** — G1+ upgrade (2026): stronger joints, upgraded perception. Waist and wrist DOF options added. Dex3-1 hands with tactile array option added.

**Lessons learned** — N/A (commercial product).

**Cost actual** — Base G1: ¥85,000 (~$13,000–$16,000) in China. G1 Basic (23 DOF, dummy hands): $21,500 USD. G1 EDU Standard (U1): $62,714 USD. G1 with Dex3-1 hands: higher. Prices vary by region, configuration, and reseller.

---

## Status

**Condition** — operational.

**Blockers** — None. Commercial availability. Lead time 6–8 weeks for EDU configurations.

**Next steps** — Configuration selection (DOF count, hands, compute module). Operator training via Unitree development manual. ROS 2 integration for custom applications. Sim-to-real policy training pipeline setup.

---
