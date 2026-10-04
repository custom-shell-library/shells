# frankapanda

**Class:** arm<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Franka Emika<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Seven-degree-of-freedom torque-controlled collaborative robot arm for manipulation research, force-sensitive assembly, kinesthetic teaching, and learning-from-demonstration. The Panda is the de facto standard research cobot, with joint torque sensors in every axis enabling sensitive force control and direct physical interaction with the environment.<br>
**Environment** — Indoor laboratory and industrial benchtop. IP40 rated (protected against solid objects larger than 1 mm, no water protection). Operating temperature +5 °C to +45 °C. Relative humidity 20–80%, non-condensing.<br>
**Mission** — Precision manipulation, force-controlled assembly, peg-in-hole tasks, surface following, polishing, and research into human-robot collaboration. The open control interface and 1 kHz torque control make it a benchmark platform for imitation learning, reinforcement learning, and sim-to-real transfer.<br>
**Operator** — Single operator via Franka Desk web interface (for programming and system management) or external workstation via Franka Control Interface (FCI) for real-time low-level control. Supports hand-guiding mode for kinesthetic teaching.<br>
**Reusability** — Commercial platform. Not a DIY build. The arm, control unit, and gripper are purchased as a complete system. Third-party end effectors can be mounted via the ISO 9409-1-A50 flange.

---

## Spec

**Physical** — Robot arm weight approximately 18.3 kg. Maximum reach 855 mm. Workspace coverage 94.5%. Mounting flange DIN ISO 9409-1-A50. The slim 19-inch control unit can be placed in server racks.<br>
**Kinematic** — 7 revolute joints, providing 7 degrees of freedom. Redundant serial manipulator, allowing null-space motion and obstacle avoidance while maintaining end-effector pose. Joint ranges: A1 ±166°, A2 ±105°, A3 ±166°, A4 −176° to −7°, A5 ±165°, A6 25° to 265°, A7 ±175°.<br>
**Dynamic** — Payload capacity 3 kg. Pose repeatability ±0.1 mm. Maximum end-effector velocity 2 m/s. Joint torque limits: A1–A4 ±87 Nm, A5–A7 ±12 Nm. Maximum joint velocities: A1–A4 2.175 rad/s (150°/s), A5–A7 2.610 rad/s (301°/s) under FCI control, with A6 limited to 239°/s.<br>
**Power** — Control unit input 100–240 VAC, 50–60 Hz. Power consumption approximately 80 W. Active power factor correction (PFC). Control unit weight approximately 7 kg. IP20 rated.<br>
**Thermal** — Passive cooling. No active thermal management. Joint motors are designed for sustained operation within the specified torque limits.<br>
**Environmental** — IP40 (arm), IP20 (control unit). Not for wet, dusty, or explosive environments.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The arm, control unit, and gripper are purchased as a complete system.

| Component | Notes |
|:---|:---|
| Franka Emika Panda arm | 7 DOF, 18.3 kg, 855 mm reach, IP40 |
| Franka control unit | 19-inch rack mount, 7 kg, IP20, 100–240 VAC |
| Franka parallel-jaw gripper | Continuous grasping force 70 N, maximum 140 N, stroke 80 mm |
| FCI license | Franka Control Interface for 1 kHz real-time control |
| Power cable | IEC 60320 C14 with V-Lock |
| Arm connector cable | Connects arm to control unit |
| External enabling device | Safety input for remote enable |
| Emergency stop device | Safety input for emergency stop |

**Structure** — Human-arm-inspired lightweight serial manipulator. Seven revolute joints in a redundant configuration. Each joint houses a dedicated link-side torque sensor, enabling force sensing without a separate end-effector force/torque sensor.<br>
**Actuation** — Proprietary brushless DC motors with harmonic drive or similar high-ratio gearing. Joint torque sensors at every axis provide direct force measurement. Dedicated position, current, and torque sensors in all seven joints.<br>
**Locomotion** — Fixed base. Mounted on benchtop, pedestal, or mobile platform. The arm is not designed to be moved while powered.<br>
**Manipulation** — Franka parallel-jaw gripper. One degree of freedom (open/close). Adjustable grasp width from 0 to 80 mm. Force-controlled grasping from 20 N to 140 N (continuous 70 N).<br>
**Power system** — Control unit handles all power conversion and distribution. The arm receives power and communication through a single arm connector cable.<br>
**Wiring** — Arm-to-control-unit cable. Ethernet connection for FCI and Desk access. Safety inputs for external enabling and emergency stop.<br>
**Custom parts** — None. Third-party end effectors can be mounted via the ISO 9409-1-A50 flange with appropriate adapter plates.<br>
**Fasteners** — Proprietary. Not user-serviceable.<br>
**Tools required** — None for assembly. Standard tools for end-effector mounting and mounting the arm to a surface.

---

## Systems

**Manifest** — Franka proprietary firmware and open-source software ecosystem.<br>
**Firmware** — Franka proprietary firmware running on the control unit. Regular firmware updates available via Franka Desk. The control unit runs the real-time joint control loop at 1 kHz.<br>
**Middleware** — ROS 2 support via the franka_ros2 package (targeting Franka Research 3 and recent ROS 2 distributions) and the libfranka C++ library. For the legacy Panda, an open-source ROS 2 stack restores support by resolving the long-standing unreliability of the external position control interface, using an asynchronous hardware interface that decouples real-time communication from the ROS 2 control loop.<br>
**Perception** — No onboard perception sensors. The arm relies on joint torque sensors, position sensors, and current sensors in all seven axes. External perception (cameras, depth sensors) must be added by the user for vision-guided manipulation.<br>
**Control** — Franka Control Interface (FCI) provides 1 kHz low-level torque and position control access to the arm and hand. The FCI exploits the available Lagrangian dynamics robot model. Five control interfaces are available: torque, position, velocity, Cartesian, and joint-space. The FCI connects the onboard controller to an external workstation over UDP.<br>
**Planning** — MoveIt 2 is the standard motion planning framework for the Panda. MoveIt Servo enables real-time Cartesian control for teleoperation and reactive motion. The redundant 7-DOF configuration allows null-space optimization for singularity avoidance and joint-limit avoidance.<br>
**Learning** — Widely used for imitation learning, reinforcement learning, and learning from demonstration. The 1 kHz torque control interface and joint torque sensing enable compliant control policies. Supports sim-to-real transfer with MuJoCo, Isaac Sim, and Gazebo. The Panda has an active community and extensive learning-from-demo support.<br>
**Teleoperation** — Cartesian impedance control and haptic teleoperation supported. VR teleoperation stacks exist, including Cartesian impedance control, gripper interface, and force-torque sensing for haptic feedback.<br>
**Safety** — Advanced safety control, force sensing, joint torque and force control, and hand-guiding performance. External enabling device input and emergency stop input. Collision detection via joint torque sensors. Certified for collaborative operation.<br>
**Logging** — Joint states, torques, external torques, estimated external torque, joint collision/contacts, and Cartesian pose available via FCI and libfranka at 1 kHz. Data can be logged for policy training.<br>
**Networking** — Ethernet (TCP/IP) for FCI, Desk programming, and system management. Shop floor connection supported.<br>
**Config files** — Managed via Franka Desk. Robot model (M, C, G, J matrices) available at 1 kHz for control and simulation.<br>
**Launch files** — franka_ros2 provides launch files for bringup, controllers, and MoveIt integration.<br>
**Dependencies** — libfranka (C++ SDK). franka_ros2 (ROS 2 integration). MoveIt 2. Franka Desk (web interface). franky-panda (Python high-level motion library).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| libfranka | 0.15.0+ | Franka | SDK/C++ |
| franka_ros2 | Latest | Franka | Middleware/ROS2 |
| ROS 2 | Humble or Jazzy | ros.org | Middleware/ROS2 |
| MoveIt 2 | Latest | ros.org | Planning/MoveIt |
| franky-panda | Latest | PyPI | SDK/Python |
| panda_simulator | Latest | github | Simulation/Gazebo |
| panda-py | Latest | github | SDK/Python |
| Frankapy | Latest | CMU | SDK/Python |
| Franka-Interface | Latest | CMU | SDK/C++ |

---

## Interface

**Emits** — Joint states (position, velocity, torque), external torque, estimated external torque, joint collision/contacts, Cartesian pose, controller state. All at 1 kHz via FCI.

**Accepts** — Joint position commands, joint velocity commands, joint torque commands, Cartesian pose commands, Cartesian velocity commands, impedance parameters. All at 1 kHz via FCI.

**Serves** — Enabling/disabling, calibration, parameter access via Franka Desk.

**Executes** — Motion planning and execution via MoveIt 2. Trajectory execution via FCI. Hand-guiding mode.

**Extensions** — Third-party end effectors via ISO 9409-1-A50 flange. External perception via user-added sensors.

**Frame conventions** — `base_link` at robot base. `panda_link0` through `panda_link7` for the kinematic chain. `panda_hand` for the gripper. `panda_tcp` for the tool center point.

**Units** — SI. Meters, radians, seconds, Newtons, Newton-meters.

---

## Model

**URDF / Xacro** — Provided by franka_ros2. Includes all joint limits, link masses, inertias, and collision geometry.

**SDF** — Available for Gazebo simulation via panda_simulator.

**Calibration** — Factory calibrated. Joint zero offsets, torque sensor offsets, and kinematic parameters set at factory. Recalibration via Franka Desk or FCI.

**Dynamics** — Lagrangian dynamics model available at 1 kHz. Mass matrix (M), Coriolis matrix (C), gravity vector (G), and Jacobian (J) provided by the control unit. This enables model-based control, computed torque control, and accurate simulation.

**Sensor transforms** — Joint torque sensors at every axis. No external force/torque sensor. End-effector force/torque estimated via Jacobian transformation of joint torques.

**Collision geometry** — Provided in URDF. Simplified geometric primitives for real-time collision checking.

**Visual geometry** — Provided in URDF.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — FCI connection over UDP. franka_ros2 bringup. MoveIt 2 configuration. Joint torque sensor verification. Hand-guiding mode verification.

**Field** — Precision manipulation tasks. Force-controlled assembly (peg-in-hole). Surface following and polishing. Human-robot collaboration scenarios. Learning-from-demonstration experiments.

**Endurance** — Continuous operation within specified torque limits. Joint temperature monitoring.

**Environmental** — Indoor laboratory and industrial benchtop. IP40 (arm), IP20 (control unit).

**Known limitations** — Vendor software support for the original Panda has been discontinued. Current releases of franka_ros2 and libfranka target the newer Franka Research 3 (FR3) arm. Laboratories relying on the Panda are left on outdated, unmaintained software unless using community-maintained ROS 2 stacks. Position control through the official external interface is unreliable, prone to vibrations and protective stops; an open-source ROS 2 stack resolves this by using an asynchronous hardware interface. The gripper does not support real-time control and must be controlled using libfranka bindings directly.

---

## Log

**Build history** — Panda released 2017. Awarded German Future Prize for affordability and ease of use. Franka Research 3 (FR3) succeeded the Panda. Vendor software support for Panda discontinued. Community-maintained ROS 2 stacks available.

**Open issues** — Vendor software support discontinued for original Panda. Position control interface reliability. Gripper real-time control limitations.

**Changelog** — N/A (commercial product).

**Lessons learned** — N/A (commercial product).

**Cost actual** — Approximately €15,500 including arm, hand, and controller with FCI interface, without taxes. New units $40K, used units $25K. Rental available at $11,000/month.

---

## Status

**Condition** — operational.

**Blockers** — None. Commercially available (original Panda discontinued; FR3 is the current production model).

**Next steps** — Configuration selection (FCI license, gripper, mounting). Workstation setup for FCI (low-latency Ethernet configuration recommended). ROS 2 integration via franka_ros2 or community stack. MoveIt 2 configuration for motion planning. End-effector selection based on application.

---
