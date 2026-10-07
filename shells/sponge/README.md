# sponge

**Class:** soft (modular articulated)<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** Tim Lukas Habich, Jonas Haack, Mehdi Belhadj, Dustin Lehmann, Thomas Seel, Moritz Schappler<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Open-source modular articulated soft robot (ASR) with antagonistic pneumatic bellows. The robot is a snake-like or arm-like structure composed of stackable soft modules. Each module is a rigid link connected to the next by a compliant joint driven by two antagonistic bellows. By inflating one bellows and deflating the other, the joint bends in one direction; reversing the pressure differential bends it the other way. This architecture combines the safety and compliance of soft robotics with the kinematic structure and controllability of articulated robots. The SPONGE platform provides two variants: a semi-modular design with multiple cables and tubes routed through the robot body, and a fully modular design with integrated microvalves and serial communication. <br>

**Environment** — Indoor laboratory and research settings. Benchtop, test stand, or mounted on a fixed base. Not for outdoor, hazardous, or unstructured environments. The pneumatic bellows are not sealed against dust or moisture. Operating temperature 10–40 °C. <br>

**Mission** — Provide a reproducible, open-source benchmark platform for soft robotics research. The platform is designed for validating control algorithms, testing sim-to-real transfer methods, and comparing research results across laboratories. The SPONGE robots' functionality is demonstrated in experiments on airtightness, gravitational influence, position control with mean tracking errors of <3°, and long-term operation of cast and printed bellows. <br>

**Operator** — Single operator via Linux PC (Ubuntu with ROS 2) communicating with the robot through a serial or USB interface. The fully modular variant uses serial communication with integrated microvalves; the semi-modular variant uses external pressure regulators and valves. <br>

**Reusability** — Fully open-source. The SPONGE platform is released under open-source licenses (CERN-OHL-P-2.0 for hardware design files, CC BY 4.0 for documentation, as specified in the LT-PAM specification and consistent with the SPONGE open-source release). Design files, CAD models, and control software are publicly available. <br>

---

## Spec

**Physical** — Module diameter 40 mm (based on comparable modular soft robot designs). Module height 50 mm per segment. Number of modules configurable: 4–8 modules for a typical research arm. Total length 200–400 mm depending on configuration. Total mass 500 g–1.2 kg depending on module count and pneumatic routing. Body material: cast silicone (Elastosil M4601 or Dragonskin Fast 10) for the bellows, rigid links 3D-printed from PA12 or PETG. The semi-modular variant routes multiple cables and tubes through the robot body; the fully modular variant integrates microvalves directly into each module and uses serial communication. <br>

**Kinematic** — Each module provides 2 degrees of freedom (pitch and yaw) via the antagonistic bellows arrangement. A 4-module arm therefore has 8 DOF; an 8-module arm has 16 DOF. The bellows are arranged in an antagonistic pair: one on each side of the joint axis. Inflating one bellows while deflating the other creates a torque about the joint axis. The joint stiffness can be modulated by adjusting the pressure in both bellows simultaneously: higher equal pressure = higher stiffness; lower equal pressure = lower stiffness. This is the variable stiffness capability of the antagonistic design. <br>

**Dynamic** — Maximum joint angle ±45° per module (pitch and yaw). Blocked force per joint depends on bellows pressure: a comparable soft actuator achieves 60 N blocked axial force at low pressure operation. The SPONGE platform's position control achieves mean tracking errors of <3°. The bellows are fabricated from a silicone inner tube, a braided sleeve, and mechanically crimped metal fittings that eliminate the need for adhesive bonding in load-bearing connections, based on the LT-PAM design principle. Rupture tests demonstrate that specimens sustain tensile loads of approximately 600–800 N and survive more than 9000 pressurization cycles without catastrophic failure. <br>

**Power** — 24 V DC for the pneumatic valves and control electronics. Air supply: 0–6 bar (0–600 kPa) compressed air from an external compressor or laboratory air line. The semi-modular variant uses external pressure regulators; the fully modular variant uses integrated microvalves with a centralized supply line and signal routing using a data bus. Power consumption depends on valve duty cycle; typical draw is 5–20 W. <br>

**Thermal** — 10–40 °C operating. Passive cooling. The pneumatic expansion of air during inflation provides some cooling. No active thermal management. <br>

**Environmental** — Indoor, controlled laboratory environment. Not IP-rated. Not for outdoor use. The pneumatic system requires clean, dry air; a filter and water trap are recommended. <br>

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $1,500–$3,000 for a 4-module arm with pneumatic supply, or $4,000–$6,000 for an 8-module arm with the fully modular variant and integrated microvalves. <br>

**Structure** — The robot is composed of stackable modules. Each module contains: (1) A rigid link (3D-printed PA12 or PETG), (2) A compliant joint formed by two antagonistic pneumatic bellows, (3) Pneumatic fittings and tubing (or integrated microvalves in the fully modular variant), (4) Mounting interfaces at both ends for stacking. The rigid links provide structural support and mounting points for the bellows. The bellows are the compliant elements that allow articulation. The design follows the SPONGE architecture, which achieves modularity in terms of stackability, actuation, and communication. Stackable actuators can be connected consecutively, but a centralized supply line and signal routing using a data bus are required for building soft robots with many degrees of freedom. <br>

**Actuation** — Antagonistic pneumatic bellows. Each joint has two bellows (one on each side). The bellows are McKibben-type actuators: a silicone inner tube surrounded by a braided sleeve, with mechanically crimped metal fittings at both ends. When pressurized, the inner tube expands radially, the braided sleeve converts this expansion into axial contraction, and the bellows pulls on the joint. The LT-PAM design uses a silicone inner tube, a braided sleeve, and mechanically crimped metal fittings that eliminate the need for adhesive bonding in load-bearing connections. All components are assembled from off-the-shelf parts and simple 3D-printed end plugs. The cost of hardware is approximately USD 5 per 150 mm actuator (marginal material cost only, excluding reusable tools). <br>

**Locomotion** — The SPONGE robot is a fixed-base articulated soft robot. It does not locomote. It can be mounted as a soft arm for manipulation research, or configured as a soft snake robot for locomotion research (though the SPONGE platform focuses on the articulated arm configuration). For snake-like locomotion, the modules can be arranged in a serial chain and actuated in a traveling wave pattern, but this is not the primary configuration of the SPONGE platform. <br>

**Manipulation** — Optional. The SPONGE arm can be fitted with a soft gripper at the end. The Fin-Ray soft gripper is a suitable open-source option: it combines 3D-printed TPU fingers optimized via finite element analysis, a thin-film piezo-resistive force sensor, and an STM32-based proportional controller that regulates gripping force in real time. The sensor was characterized in the range from approximately 0.1 N to 5 N, with a third-order polynomial calibration yielding an average accuracy of 70.8% over this interval. Static closed-loop tests converge to a 0.981 N force setpoint with small steady-state error. <br>

**Power system** — 24 V DC for valves and electronics. Compressed air supply at 0–6 bar. The pneumatic supply is external (compressor or laboratory air line). The robot itself carries only the valves, tubing, and control electronics. Power wiring 18 AWG for main power, 26 AWG for signal. <br>

**Wiring** — Pneumatic tubing (4 mm or 6 mm outer diameter) routed through the robot body (semi-modular) or integrated with microvalves (fully modular). Electrical wiring for valves and sensors: 26 AWG. Serial communication bus (RS-485 or CAN) for the fully modular variant. All wiring and tubing routed through the hollow centers of the modules with service loops at each joint. <br>

**Custom parts** — 3D-printed rigid links (PA12 or PETG). 3D-printed bellows molds (for casting silicone bellows). Cast silicone bellows (Elastosil M4601 or Dragonskin Fast 10). 3D-printed end plugs for the bellows. Crimped metal fittings for the bellows. 3D-printed module housings. <br>

**Fasteners** — M3 and M4 stainless steel. M3 for module assembly and bracket mounting. M4 for structural connections. Heat-set threaded inserts in printed parts for repeated assembly. <br>

**Tools required** — 3D printer (PA12 or PETG capable). Silicone casting tools (molds, vacuum chamber for degassing, curing oven). Crimping tool for metal fittings. Pneumatic tubing cutter. Hex drivers (2 mm, 2.5 mm, 3 mm). Soldering iron. Multimeter. Compressed air source with regulator and filter. <br>

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Silicone (Elastosil M4601 or Dragonskin Fast 10) | 1 kg | Wacker / Smooth-On | ~$100 | Soft material/Bellows |
| Braided sleeve (polyester or nylon) | 5 m | Techflex / cable sleeve | ~$10 | Soft material/Sleeve |
| Silicone inner tube (4 mm ID) | 5 m | Various | ~$15 | Soft material/Tube |
| Metal crimp fittings | 20 | Various | ~$20 | Soft material/Fittings |
| 3D-printed rigid links (PA12 or PETG) | 1 set | Local print | ~$50 | Structure/Links |
| 3D-printed bellows molds | 1 set | Local print | ~$30 | Fabrication/Molds |
| Microvalves (fully modular variant) | 2 per module | Festo / SMC | ~$30 each | Actuators/Valves |
| Pressure regulators (semi-modular variant) | 2 per module | Festo / SMC | ~$50 each | Actuators/Regulators |
| Pneumatic tubing (4 mm or 6 mm) | 10 m | Festo / SMC | ~$20 | Pneumatics/Tubing |
| 24 V DC power supply | 1 | Mean Well | ~$50 | Power/Supply |
| Control electronics (Teensy 4.0 or STM32) | 1 | PJRC / ST | ~$25 | Compute/MCU |
| Serial communication bus hardware | 1 set | Various | ~$30 | Comms/Serial |
| Fin-Ray soft gripper (optional) | 1 | Open-source design | ~$900 | Manipulation/Gripper |
| Workstation PC (Ubuntu, ROS 2) | 1 | Various | ~$800 | Compute/PC |
| Compressed air source (compressor or lab line) | 1 | Various | ~$200–$500 | Pneumatics/Supply |
| Filter and water trap | 1 | Festo / SMC | ~$50 | Pneumatics/Conditioning |
| **Total (4-module arm, semi-modular)** | | | **~$1,500–$2,500** | |
| **Total (8-module arm, fully modular)** | | | **~$4,000–$6,000** | |

---

## Systems

**Manifest** — The SPONGE software stack is ROS 2-based. The control system uses a model-based approach with pressure-to-torque mapping and joint-space position control. The fully modular variant uses serial communication with integrated microvalves. The SPONGE platform provides open-source control software, simulation models (Gazebo plugins for soft robot locomotion dynamics), and a JointStiffnessPlugin integrated with ROS services for fine-tuning effort-controlled parameters. <br>

**Firmware** — The control electronics (Teensy 4.0 or STM32) runs the pressure control loop for the valves. For the semi-modular variant, the firmware reads joint angle from sensors (potentiometers or encoders) and commands pressure regulators. For the fully modular variant, the firmware communicates with the integrated microvalves over a serial bus (RS-485 or CAN) and commands pressure directly. The control loop runs at 100–500 Hz. <br>

**Middleware** — ROS 2. The JointStiffnessPlugin is integrated with ROS services for fine-tuning effort-controlled parameters. Custom Gazebo plugins enable the simulation and analysis of soft robot locomotion dynamics. The ROS 2 interface provides topics for joint commands, joint states, pressure feedback, and stiffness parameters. <br>

**Perception** — Joint angle sensors (potentiometers, magnetic encoders, or flex sensors) for each joint. Pressure sensors for each bellows. Optional: force/torque sensor at the end effector for manipulation tasks. Optional: camera for visual servoing. The SPONGE platform does not include external perception in the base configuration; it is a proprioceptive platform. <br>

**Control** — The control architecture is a two-level hierarchy. The high-level controller runs on the workstation PC and computes joint trajectories for the desired end-effector pose. The low-level controller runs on the Teensy or STM32 and tracks the desired joint angles using a pressure-based impedance controller. The impedance controller adjusts the pressure in the antagonistic bellows to achieve the desired joint angle and stiffness. The JointStiffnessPlugin allows the stiffness to be tuned in real time. The SPONGE platform achieves mean tracking errors of <3° in position control experiments. <br>

**Planning** — No autonomous planning in the base platform. The SPONGE arm is teleoperated or programmed with joint trajectories. Optional: MoveIt 2 integration for motion planning (requires a kinematic model of the soft arm). <br>

**Learning** — Designed for reinforcement learning and sim-to-real research. The SPONGE platform is used as a benchmark system for validating control algorithms. Research on soft robot control uses physics-informed neural networks as surrogate models for model predictive control, and hysteresis-aware neural network models for whole-body reinforcement learning control. The SPONGE arm is used in research on generalizable and fast surrogates for model predictive control using physics-informed neural networks. <br>

**Teleoperation** — Optional. The SPONGE arm can be teleoperated using a gamepad or a leader-follower setup. The variable stiffness capability makes it well-suited for teleoperation tasks where the operator needs to feel the compliance of the robot. <br>

**Safety** — Soft robots are inherently safer than rigid robots because their compliance limits the forces they can exert. The bellows are the compliant elements; if the robot collides with a person, the bellows deform and absorb the impact. The maximum force is limited by the bellows pressure and geometry. The SPONGE platform does not include a formal safety system (e-stop, light curtain) in the base configuration, but the inherent compliance provides passive safety. <br>

**Logging** — rosbag2 with MCAP format. Joint angles, pressures, and commands recorded at 100 Hz. Data format compatible with LeRobot for future policy training. <br>

**Networking** — Ethernet or Wi-Fi via the workstation PC. The fully modular variant uses a serial bus (RS-485 or CAN) for communication between modules. <br>

**Config files** — ROS 2 parameters for joint limits, pressure limits, stiffness parameters, and control gains. JointStiffnessPlugin configuration. <br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`, `sim.launch.py` (for Gazebo simulation). <br>

**Dependencies** — ROS 2, Gazebo plugins for soft robot simulation, JointStiffnessPlugin, Python for analysis, C++ for real-time control. <br>

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy or Humble | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS or 22.04 | ubuntu.com | OS/Linux |
| Gazebo | Harmonic | gazebosim.org | Simulation |
| JointStiffnessPlugin | Latest | SPONGE repo | Control/Stiffness |
| MoveIt 2 (optional) | Latest | ros.org | Planning/MoveIt |
| Python | 3.x | python.org | Analysis |
| C++ | 17+ | iso.org | Real-time control |
| Fin-Ray gripper firmware | Latest | Open-source | Manipulation/Gripper |

---

## Interface

**Emits** — `/joint_states` (100 Hz, JointState for each joint), `/joint_pressures` (100 Hz, Float64MultiArray for each bellows pressure), `/joint_stiffness` (100 Hz, Float64MultiArray for each joint stiffness), `/robot_status` (1 Hz). <br>

**Accepts** — `/joint_commands` (100 Hz, JointState for desired joint angles), `/stiffness_commands` (100 Hz, Float64MultiArray for desired joint stiffness). <br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (retract to straight position). <br>

**Executes** — `/execute_trajectory` (action, joint-space trajectory), `/set_stiffness` (action, adjust joint stiffness). <br>

**Extensions** — `sponge/bellows_pressure`, `sponge/bellows_volume`, `sponge/valve_state`, `sponge/air_consumption`. <br>

**Frame conventions** — `base_link` at the base mounting point. `module_1`, `module_2`, ..., `module_n` for each module. `joint_1`, `joint_2`, ..., `joint_n` for each joint. `tool0` at the end effector mounting point. <br>

**Units** — SI. Meters, radians, seconds, Pascals (or bar for pressure), Newtons per meter (for stiffness). <br>

---

## Model

**URDF / Xacro** — `model/sponge.urdf.xacro`. Each module is modeled as a rigid link connected by a 2-DOF joint (pitch and yaw). Joint limits from mechanical design: ±45° per joint. Link masses from CAD and verified by weighing. The URDF is used for ROS 2 visualization and MoveIt 2 planning (if used). <br>

**SDF** — Used for Gazebo simulation. Custom Gazebo plugins enable the simulation and analysis of soft robot locomotion dynamics. The JointStiffnessPlugin is used in simulation for fine-tuning effort-controlled parameters. <br>

**Calibration** — Joint zero offsets (each joint's sensor zero set to the mechanical straight position). Pressure-to-torque calibration for each bellows (measured experimentally). Stiffness-to-pressure calibration for each joint. Bellows volume-to-pressure calibration. The SPONGE platform's bellows are fabricated from silicone with a braided sleeve; the pressure-to-contraction relationship is characterized through quasi-static force–length tests under constant pressure and pressure–contraction tests under constant load, confirming canonical McKibben-type behavior with low sample-to-sample variability. <br>

**Dynamics** — The soft robot dynamics are nonlinear and hysteretic. The pressure-to-contraction relationship exhibits hysteresis (the relationship between pressure and contraction differs between inflation and deflation). The SPONGE platform models this through a combination of physics-based models and data-driven surrogates. Research on soft robot control uses physics-informed neural networks as surrogate models for model predictive control, and hysteresis-aware neural network models for whole-body reinforcement learning control. The LT-PAM actuator exhibits canonical McKibben-type behavior with low sample-to-sample variability, which simplifies the modeling. <br>

**Sensor transforms** — Joint angle sensors at each joint. Pressure sensors at each bellows. No external sensors in the base configuration. <br>

**Collision geometry** — Simple cylinders for modules in simulation. The soft joints are modeled as compliant elements with stiffness parameters. <br>

**Visual geometry** — STL meshes from printed parts. Silicone bellows modeled as deformable meshes (optional for high-fidelity simulation). <br>

---

## Trials

**Bench** — Valve direction and response. Pressure sensor calibration. Joint angle sensor calibration. Bellows airtightness test. Bellows rupture test. Pass/fail, measured values, date. Expected: valves respond to commands within 50 ms, pressure sensors read within 2% of true pressure, joint angle sensors read within 1° of true angle, bellows hold pressure for 60 seconds without measurable leak, bellows survive 9000+ pressurization cycles. <br>

**Integration** — ROS 2 bring-up. JointStiffnessPlugin operation. Pressure-to-torque mapping verification. Position control with mean tracking error <3°. Stiffness modulation verification. Pass/fail, measured values, date. <br>

**Field** — Position control experiment: command a series of joint angles and measure the tracking error. Stiffness modulation experiment: command different stiffness values and measure the change in joint compliance. Long-term operation experiment: run the robot continuously for 1 hour and measure drift and degradation. Pass/fail, measured values, date. <br>

**Endurance** — Continuous operation until valve or bellows failure. Bellows survive 9000+ pressurization cycles without catastrophic failure, based on LT-PAM test data. <br>

**Environmental** — Indoor, controlled laboratory environment only. <br>

**Known limitations** — The soft robot is limited by the pneumatic supply; it requires an external compressor or air line. The bellows are subject to hysteresis, which complicates control. The fully modular variant is more complex and expensive but eliminates the tubing routing problem. The semi-modular variant has multiple cables and tubes routed through the robot body, which limits the number of modules that can be stacked. The robot is not for outdoor or unstructured environments. The Fin-Ray gripper, if used, has an average accuracy of 70.8% over the 0.1–5 N range, with reduced accuracy at very low forces. <br>

---

## Log

**Build history** — SPONGE platform released 2024. The platform provides two variants: semi-modular and fully modular. The semi-modular version is suitable as a research platform; the fully modular version enables building soft robots with many degrees of freedom and high dexterity. <br>

**Open issues** — Hysteresis compensation. Sim-to-real transfer for soft robot control. Scaling to many modules. <br>

**Changelog** — Version 1.0: initial open-source release. <br>

**Lessons learned** — Modularity in terms of stackability, actuation, and communication is the crucial requirement for building soft robots with many degrees of freedom and high dexterity for real-world tasks. A centralized supply line and signal routing using a data bus is required for scalability. <br>

**Cost actual** — The LT-PAM actuator costs approximately USD 5 per 150 mm actuator (marginal material cost only). The Fin-Ray gripper costs approximately $900. The SPONGE platform's total cost depends on the number of modules and the variant (semi-modular vs. fully modular). <br>

---

## Status

**Condition** — operational. <br>

**Blockers** — None. Open-source design available. <br>

**Next steps** — Fabricate bellows using 3D-printed molds and silicone casting. Assemble modules. Set up pneumatic supply and control electronics. Configure ROS 2 and JointStiffnessPlugin. Run airtightness and position control experiments. Optional: integrate Fin-Ray soft gripper for manipulation experiments. Optional: run sim-to-real experiments using Gazebo plugins and physics-informed neural network surrogates. <br>

---

**Note on this Shell:** The SPONGE platform is a distinct class in the library. Unlike rigid robots, soft robots derive their capability from material compliance, not kinematic precision. The antagonistic bellows architecture provides variable stiffness, which is a capability that rigid robots cannot match. The SPONGE platform is the reference for open-source modular articulated soft robots, providing two variants (semi-modular and fully modular) and validated control experiments with mean tracking errors of <3°. The platform is designed for reproducibility and comparability of research results, which is a critical need in soft robotics where designs are often only briefly described in publications. This Shell is the reference for a soft pneumatic robot with antagonistic bellows, open-source CAD and control software, and validated performance characteristics.
