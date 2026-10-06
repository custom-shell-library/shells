# openarm

**Class:** arm<br>
**Generation:** 2<br>
**Version:** 2.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Enactic<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Open-source 7-DOF robot arm with quasi-direct-drive (QDD) joints and bilateral force feedback, designed for physical AI research, teleoperation, and contact-rich data collection. The arm is human-scale, with an aluminum and stainless-steel structure and a MISUMI-frame base, and is proportioned for a person ~160–165 cm tall. It supports compliant interaction, gravity compensation, and rich teleoperation, making it a strong platform for imitation learning, reinforcement learning, and sim-to-real transfer. The OpenArm project also includes the OpenArm Cell (a standardized evaluation enclosure) and the OpenArm KER (a motorless kinematic replica for teleoperation and data collection). <br>

**Environment** — Indoor laboratory and research benchtop. The arm is intended for controlled environments, not for industrial deployment or outdoor use. The OpenArm Cell adds light curtains, area sensors, and an e-stop for safe operation in shared spaces. <br>

**Mission** — Provide a low-cost, fully open-source, human-scale arm for physical AI research. The arm is designed for: (1) Teleoperation with bilateral force feedback, (2) Contact-rich data collection for imitation learning, (3) Sim-to-real policy deployment, and (4) Standardized benchmarking via the OpenArm Cell. The project also includes OpenArm Online, where researchers can submit trained policies as Docker containers and evaluate them on simulated tasks through a web browser. <br>

**Operator** — Single operator via Linux PC (Ubuntu 22.04/24.04) communicating over SocketCAN. The software stack includes C++ and Python CAN-FD libraries, ROS 2, MoveIt 2 configurations for bimanual operation, and Dora nodes for data collection and teleoperation. <br>

**Reusability** — Fully open-source. Hardware CAD files in STEP, STL, and Fusion 360 formats are licensed under CERN-OHL-S-2.0, while most software repositories use the Apache 2.0 license. The project provides open-source CAD, BOM, firmware, control software, ROS 2, MuJoCo, Isaac Lab, and dataset tools. <br>

---

## Spec

**Physical** — ~5.5 kg per arm (excluding the base and the host PC). Human-scale, proportioned for a person ~160–165 cm tall. Base plate 190 × 250 mm, 8 mm thick, 30 mm hole pitch, 48 × M6 taps. The structure uses aluminum and stainless steel on structural and high-load parts, with 3D-printed casings. The arm is designed to be mounted on a MISUMI-frame base, and the OpenArm Cell uses MISUMI aluminum profiles for the enclosure. <br>

**Kinematic** — 7-axis arm + 1 parallel pinch gripper (8 actuators). A bimanual system uses 14 arm DOF + 2 grippers. The arm uses a human-like joint layout, with the shoulder (J1, J2) using high-torque motors, the upper arm (J3) and elbow (J4) using mid-torque motors, and the wrist (J5, J6, J7) and gripper using low-torque motors. Reach is 606 mm (CAD-cited figure). <br>

**Dynamic** — Payload (including the end-effector): nominal 4.1 kg, held for 1 minute in worst posture (arm fully extended); peak 6.0 kg, for a 3 s move into worst posture + 1 s hold. If a 1.5 kg tool is fitted: remaining payload ≈ 2.6 kg nominal / 4.5 kg peak. <br>

**Power** — Motors: 24 V DC (the 8009P also supports 24–48 V). Currents: the 8009P is rated 20 A / peak 50 A each; the 4340/4310 are rated 2.5 A. The OpenArm Cell reference draw is ≈480 W + the host PC. <br>

**Thermal** — Passive cooling. The motors have integrated drivers with over-temperature protection. <br>

**Environmental** — Indoor, controlled. The OpenArm Cell adds safety features for shared spaces. Not for outdoor or industrial use. <br>

---

## Frame

**Bill of materials** — The complete BOM is available in the OpenArm GitHub repository and docs. The project provides open-source CAD, BOM, firmware, control software, ROS 2, MuJoCo, Isaac Lab, and dataset tools. A basic setup’s bill of materials has an approximate cost of $6,500, while some sources cite a BOM of around $2,500 for the full parts list (excluding assembly and debugging time). The KER (motorless replica) is $2,599, and the KER Encoder Unit is $49. <br>

**Structure** — Aluminum and stainless steel on structural and high-load parts, with 3D-printed casings. The base plate is 190 × 250 mm, 8 mm thick, with 30 mm hole pitch and 48 × M6 taps. The OpenArm Cell uses MISUMI aluminum profiles and includes a motorized Z-axis lift to adjust the height of the work area. <br>

**Actuation** — 8× DAMIAO motors per arm (QDD / low-ratio planetary; DAMIAO protocol). The motor breakdown is:
- 2× DM-J8009P-2EC — J1, J2 (shoulder / high load); rated 20 N·m, peak 40 N·m, 9:1 torque.
- 1× DM-J4340P-2EC — J3 (upper arm / high load); rated 9 N·m, peak 27 N·m.
- 1× DM-J4340-2EC — J4 (elbow / mid load; the 4340 series is not QDD); rated 9 N·m, peak 27 N·m.
- 4× DM-J4310-2EC V1.1 — J5, J6, J7 + gripper (wrist / hand); rated 3 N·m, peak 7 N·m. <br>

**Locomotion** — Fixed base. The arm is designed to be mounted on a benchtop or a MISUMI-frame base. The OpenArm Cell is a stationary evaluation enclosure. <br>

**Manipulation** — A compact 2-finger pinch / parallel gripper. Max jaw opening 88 mm; fully closed = jaws touching. Rotor travel closed → open 60°; motor zero = fully closed. Ball-bearing sliders + linkage bearings (meant for force feedback / bilateral teleop). An in-hand RGB camera is mounted on the 2.0 gripper. Supports Intel RealSense D435 for chest/overhead views and D405 for wrist-mounted close-up views. Custom tools mount by replacing interface part J8_B. <br>

**Power system** — 24 V DC (the 8009P also supports 24–48 V). The 8009P is rated 20 A / peak 50 A each; the 4340/4310 are rated 2.5 A. The OpenArm Cell reference draw is ≈480 W + the host PC. <br>

**Wiring** — CAN-FD (recommended): nominal 1 Mbps, data 5 Mbps, control loop 1 kHz. Classic CAN 2.0 fallback @ 1 Mbps. Motor ID/parameter flashing via DAMIAO debug tool over UART @ 921600 bps. Host path: Linux SocketCAN (Ubuntu 22.04 / 24.04); no onboard computer. <br>

**Custom parts** — The OpenArm project provides open-source CAD files in STEP, STL, and Fusion 360 formats, including 3D-printed casings. The OpenArm Cell uses MISUMI aluminum profiles. The KER uses 16 magnetic encoders and bearing joints instead of motors. <br>

**Fasteners** — Standard M6 taps on the base plate (48 × M6). Other fasteners are standard metric. The BOM includes all required hardware. <br>

**Tools required** — Linux PC (Ubuntu 22.04/24.04) for control. SocketCAN interface. DAMIAO debug tool for motor flashing. Standard metric hex drivers. A calibration jig is recommended (included in the OpenArm Cell). <br>

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| DAMIAO DM-J8009P-2EC (J1, J2) | 2 | DAMIAO | ~$150 each | Actuators/QDD |
| DAMIAO DM-J4340P-2EC (J3) | 1 | DAMIAO | ~$120 | Actuators/QDD |
| DAMIAO DM-J4340-2EC (J4) | 1 | DAMIAO | ~$110 | Actuators/QDD |
| DAMIAO DM-J4310-2EC V1.1 (J5, J6, J7, gripper) | 4 | DAMIAO | ~$80 each | Actuators/QDD |
| Gripper assembly with in-hand camera | 1 | Enactic | ~$200 | Manipulation/Gripper |
| Aluminum/stainless structural parts | 1 set | Enactic / local | ~$500 | Structure |
| 3D-printed casings | 1 set | Local print | ~$50 | Structure |
| MISUMI frame base | 1 | MISUMI | ~$300 | Structure |
| CAN-FD interface (USB-CAN or SocketCAN) | 1 | Various | ~$50 | Comms/CAN |
| Power supply (24V 20A) | 1 | Mean Well | ~$100 | Power/Supply |
| Host PC (Ubuntu 22.04/24.04) | 1 | Various | ~$800 | Compute/PC |
| Cables, connectors, fasteners | 1 set | Various | ~$200 | Wiring/Fasteners |
| OpenArm KER (motorless replica) | 1 | Enactic | $2,599 | Teleoperation/KER |
| OpenArm Cell (evaluation enclosure) | 1 | Enactic | $6,200 | Evaluation/Cell |

---

## Systems

**Manifest** — The OpenArm software stack includes C++ and Python CAN-FD libraries, ROS 2, MoveIt 2 configurations for bimanual operation, and Dora nodes for data collection and teleoperation. It supports MuJoCo and Isaac Lab, as well as Hugging Face’s LeRobot and the mink library for kinematic solving. The platform includes OpenArm Online, where researchers can submit trained policies as Docker containers and evaluate them on simulated tasks through a web browser. <br>

**Firmware** — DAMIAO motor drivers run the QDD control loop. The motors support Damiao MIT mode (kp, kd, q, dq, tau), plus Damiao position and speed modes. The drivers provide over-temperature, over/under-voltage, and over-current protection, and handle bus-off/comms-loss on SocketCAN. <br>

**Middleware** — ROS 2. MoveIt 2 for bimanual operation. Dora nodes for data collection and teleoperation. <br>

**Perception** — In-hand RGB camera on the 2.0 gripper. Supports Intel RealSense D435 for chest/overhead views and D405 for wrist-mounted close-up views. <br>

**Control** — CAN-FD (recommended): nominal 1 Mbps, data 5 Mbps, control loop 1 kHz. Classic CAN 2.0 fallback @ 1 Mbps. Control modes: Damiao MIT mode (kp, kd, q, dq, tau), plus Damiao position and speed modes. <br>

**Planning** — MoveIt 2 configurations for bimanual operation. <br>

**Learning** — Supports imitation learning, reinforcement learning, sim-to-real, and robotic manipulation. Open-source CAD, BOM, firmware, control software, ROS 2, MuJoCo, Isaac Lab, and dataset tools. Hugging Face’s LeRobot and the mink library are supported. <br>

**Teleoperation** — Bilateral force-feedback teleoperation. The OpenArm KER (Kinematic Equivalent Replica) is a motorless leader arm designed for teleoperation. It uses the same joint layout and link dimensions as the OpenArm, providing a 1:1 motion mapping. The KER uses 16 magnetic encoders and bearing joints instead of motors, so the operator can move it with little resistance during long data-collection sessions. <br>

**Safety** — Mechanical limits on every axis. QDD/low-ratio joints are backdrivable (the arm yields on contact). DAMIAO driver protections: over-temperature, over/under-voltage, over-current. Bus-off/comms-loss handling on SocketCAN (interface can be left down after bus-off). The OpenArm Cell adds light curtains/area sensors, an e-stop, and a calibration jig. <br>

**Logging** — Dora nodes for data collection. Dataset tools are part of the open-source stack. <br>

**Networking** — Linux PC (Ubuntu 22.04/24.04) communicating over SocketCAN. <br>

**Config files** — ROS 2 and MoveIt 2 configurations. <br>

**Launch files** — ROS 2 and MoveIt 2 launch files. <br>

**Dependencies** — C++ and Python CAN-FD libraries, ROS 2, MoveIt 2, Dora, MuJoCo, Isaac Lab, LeRobot, mink. <br>

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy or Humble | ros.org | Middleware/ROS2 |
| MoveIt 2 | Latest | ros.org | Planning/MoveIt |
| Dora | Latest | dora-rs | Data collection |
| MuJoCo | Latest | Google DeepMind | Simulation |
| Isaac Lab | Latest | NVIDIA | Simulation/RL |
| LeRobot | Latest | Hugging Face | Learning |
| mink | Latest | github | Kinematics |

---

## Interface

**Emits** — Joint states, motor temperatures, motor currents, gripper state, camera feeds. CAN-FD telemetry at 1 kHz. <br>

**Accepts** — Joint position commands, joint velocity commands, joint torque commands. Damiao MIT mode (kp, kd, q, dq, tau), position mode, and speed mode. <br>

**Serves** — Arming, calibration, parameter access via CAN-FD. <br>

**Executes** — Trajectory execution via MoveIt 2. Teleoperation via KER. <br>

**Extensions** — Custom tools mount by replacing interface part J8_B. <br>

**Frame conventions** — Standard ROS 2 TF tree. Base plate 190 × 250 mm. <br>

**Units** — SI.<br>

---

## Model

**URDF / Xacro** — Provided by the OpenArm project. The hardware CAD files are in STEP, STL, and Fusion 360 formats. <br>

**SDF** — MuJoCo and Isaac Lab models are supported. <br>

**Calibration** — Encoders: 14-bit single-turn magnetic, dual encoder per motor (output + rotor). <br>

**Dynamics** — Motor constants from DAMIAO datasheets. The QDD/low-ratio joints are backdrivable, enabling accurate torque control. <br>

**Sensor transforms** — In-hand camera on the gripper. RealSense D435 for chest/overhead views and D405 for wrist-mounted close-up views. <br>

**Collision geometry** — Provided in the URDF and SDF models.<br>

**Visual geometry** — Provided in the CAD and simulation models.<br>

---

## Trials

**Bench** — Motor direction, encoder counts, CAN-FD communication, control loop frequency. Pass/fail, measured values, date.<br>

**Integration** — ROS 2 bring-up, MoveIt 2 configuration, Dora nodes, teleoperation via KER. Pass/fail, measured values, date.<br>

**Field** — Payload test: 4.1 kg nominal, 6.0 kg peak. Reach test: 606 mm. Gripper test: 88 mm opening. Teleoperation test: bilateral force feedback. Data collection test: imitation learning dataset. Pass/fail, measured values, date.<br>

**Endurance** — Continuous operation until motor temperature limit. Duty cycle and cycle time recorded.<br>

**Environmental** — Indoor, controlled. OpenArm Cell adds safety features for shared spaces.<br>

**Known limitations** — The 4340 series is not QDD. The arm requires a host PC; no onboard computer. The KER full release timeline is still to be announced. The OpenArm Cell is a separate purchase and adds significant cost.<br>

---

## Log

**Build history** — OpenArm 1 released earlier. OpenArm 2.0 released 2026-09-30. OpenArm Cell and KER announced alongside.<br>

**Open issues** — KER release timeline. BOM cost variability.<br>

**Changelog** — OpenArm 2.0: 7-DOF, QDD joints, bilateral force feedback, in-hand camera. OpenArm 1: 6-DOF.<br>

**Lessons learned** — N/A (open-source project).<br>

**Cost actual** — Basic BOM ~$6,500. KER $2,599. OpenArm Cell $6,200. Assembled systems from $5,600 to $14,600 depending on configuration and hands.<br>

---

## Status

**Condition** — operational.<br>

**Blockers** — None. Open-source hardware and software available.<br>

**Next steps** — Configuration selection (arm only, bimanual, with KER, with Cell). Host PC setup with Ubuntu 22.04/24.04 and SocketCAN. ROS 2 and MoveIt 2 integration. Teleoperation and data collection setup. Policy training and OpenArm Online evaluation.

---

**Note on this Shell:** The OpenArm 2.0 is an open-source research platform. Unlike the commercial systems in this library, it can be built from the open-source BOM and modified at the hardware and software level. The QDD joints and bilateral force feedback make it particularly well-suited for physical AI research and contact-rich data collection. The OpenArm Cell provides a standardized evaluation environment, and OpenArm Online enables policy benchmarking. This Shell is a strong candidate for researchers who need a human-scale arm with rich teleoperation and a fully open stack.
