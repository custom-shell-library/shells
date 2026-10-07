# triton

**Class:** aquatic (manipulator)<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Seven-degree-of-freedom all-electric underwater manipulator for inspection-class ROVs and shallow-to-medium-depth intervention. Performs subsea manipulation tasks that would otherwise require hydraulic arms: turning valves, inserting hot stabs, cutting cables, recovering objects, and operating tool panels. The manipulator is pressure-compensated, fully electric, and rated for continuous immersion to 4,000 m. It eliminates the hydraulic skid, valve pack, and pump required by conventional hydraulic manipulators, reducing vehicle payload and increasing maneuverability.<br>

**Environment** — Freshwater and saltwater. ROV-mounted, subsea. Operating depth 0–4,000 m. Water temperature −2 to +35 °C. Not for surface use, high-current environments beyond ROV station-keeping capability, or explosive atmospheres.<br>

**Mission** — Provide dexterous, force-controlled manipulation for subsea intervention. The manipulator is designed for supervised autonomy: the operator provides high-level goals (e.g., “turn this valve”), and the arm executes with automated motion planning, force control, and fault detection. The manipulator serves as a testbed for autonomous manipulation in subsea environments, following the architecture demonstrated by the AquaSimian limb and the Nauticus Olympic Arm.<br>

**Operator** — Single ROV pilot and manipulator operator. The manipulator is controlled via a master-slave teleoperation interface or a supervised autonomy framework. The operator commands end-effector velocity or position; the arm handles inverse kinematics, joint limits, and force limiting. The operator receives live camera feeds and force-torque telemetry.<br>

**Reusability** — Repeatable build from off-the-shelf and custom components. Based on the architectures of the Nauticus Olympic Arm, the Reach Robotics Alpha 5, the JPL AquaSimian, and the CSIP ARM 5E. Production candidate for research and light intervention ROVs.

---

## Spec

**Physical** — Weight in air 100 kg (Nauticus Olympic Arm: 100 kg in air, 75 kg in water). Weight in water 75 kg (net buoyancy achieved through syntactic foam and oil-filled voids). Reach 1,850 mm (Olympic Arm: 1,850 mm). Compact folded dimensions: approximately 230 × 150 × 40 mm (Reach Alpha 5: 230 × 150 × 40 mm when curled). The arm is constructed from hard-anodised aluminium and stainless steel (Olympic Arm: anodized aluminum and stainless steel; Alpha 5: AL6061 hard anodised Type III).<br>

**Kinematic** — 7 degrees of freedom (Olympic Arm: 7 DOF; AquaSimian: 7 DOF). Joint configuration: azimuth (rotary, 270°), shoulder pitch (linear, 135°), elbow pitch (linear, 135°), elbow roll (rotary, 328°), wrist yaw (rotary, 180°), wrist rotate (rotary, infinite), and gripper open/close. The redundant 7-DOF configuration allows the arm to maintain end-effector pose while avoiding obstacles and joint limits. The joint ranges are based on the Olympic Arm specification table.<br>

**Dynamic** — Maximum lift 300 kg (Olympic Arm: 300 kg). Peak grip force 4,092 N (Olympic Arm: 4,092 N; Alpha 5: 600 N closing force). Peak wrist torque 170 N·m (Olympic Arm: 170 N·m). Peak wrist speed 50 rpm (Olympic Arm: 50 rpm). Maximum lift at full extension: 2 kg (Alpha 5: 2 kg at full reach). Axial load rating: 100 kg (Alpha 5: 100 kg axial load rating).<br>

**Power** — Input voltage 110–480 V AC or 70–90 V DC (Olympic Arm: 110–480 V AC, 70–90 V DC). Minimum peak power 2,000 W (Olympic Arm: 2,000 W). The arm is powered from the ROV’s power bus. Each joint actuator contains a brushless DC motor, a harmonic gear, an angular feedback potentiometer, and a drive circuit, all integrated into an oil-filled, pressure-compensated housing (Huahai-4E: oil-filled, pressure-compensated joint with PM brushless motor, drive circuit, harmonic gear, and angular feedback potentiometer).<br>

**Thermal** — Passive cooling through the oil-filled housings and seawater. The oil in each actuator housing conducts heat from the motor and drive circuit to the housing wall, which is cooled by ambient seawater. Operating temperature −2 to +35 °C. Storage temperature −10 to +80 °C (Alpha 5: operating 5–35 °C, storage −10 to 80 °C).<br>

**Environmental** — Rated depth 4,000 m (Olympic Arm: 4,000 m). Seals rated to 7,500 m (CSIP ARM 5E: 7,500 m rated seals). Pressure compensation: oil-filled voids compensated to 0.4 bar above ambient (CSIP ARM 5E: pressure compensated to 0.4 Bar above ambient). In the event of a seal breach, oil leaks out but water cannot leak in (CSIP ARM 5E: “oil may leak out but water cannot leak in”). Corrosion resistance: hard-anodised aluminium, 316 stainless steel, and nickel aluminium bronze (CSIP ARM 5E: HE30 hard anodized aluminum, 316 stainless steel, and nickel aluminum bronze).

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $45,000–$80,000 for a research-grade build, or $120,000–$200,000 for a fully qualified commercial-grade unit.<br>

**Structure** — The arm consists of seven modular joint housings connected by rigid links. Each joint housing is a cylindrical pressure vessel machined from hard-anodised aluminium. The housing contains the brushless DC motor, harmonic gear, drive circuit, and angular feedback potentiometer, all immersed in oil. The oil is pressure-compensated by a flexible membrane or piston that transmits ambient seawater pressure to the oil while preventing water ingress. The joint housings are connected by stainless steel links with integrated cable routing. The end effector interface is an ISO 9409-1-A50 flange or a custom quick-change tool interface. The overall architecture follows the Olympic Arm and AquaSimian designs.<br>

**Actuation** — 7 brushless DC motors, one per joint. Each motor is integrated with a harmonic gear (zero backlash, high torque density) and an angular feedback potentiometer (Huahai-4E: PM brushless motor, harmonic gear, angular feedback potentiometer). The motors are designed to operate in oil, with oil-tolerant insulation and bearings (CSIP ARM 5E: brushless motors that operate in oil). The actuators are pressure-compensated to 0.4 bar above ambient, which prevents seawater ingress even at full ocean depth (CSIP ARM 5E: pressure compensated to 0.4 Bar above ambient, with 7,500 m rated seals).<br>

**Locomotion** — Fixed base. The manipulator is mounted on an ROV. The ROV provides locomotion; the manipulator provides manipulation.<br>

**Manipulation** — Seven degrees of freedom plus a gripper. End effector options: four-finger gripper (Olympic Arm: four-finger gripper), 4-inch parallel jaws (Olympic Arm: 4-inch parallel jaws), three-function robotic gripper (AquaSimian: custom 3-function robotic gripper), and interchangeable jaws (Alpha 5: interchangeable jaws). The gripper is mounted to a 6-DOF force-torque sensor (AquaSimian: 6 degree of freedom force torque sensor), which measures interaction forces and torques at the end effector. The force-torque sensor enables force control, impedance control, and autonomous fault detection.<br>

**Power system** — Input voltage 70–90 V DC or 110–480 V AC (Olympic Arm: 110–480 V AC, 70–90 V DC). Power is distributed from the ROV’s power bus to each joint actuator through a shared bus. Each joint has a local drive circuit that converts the bus voltage to the motor voltage and controls the motor current. The power system includes over-current protection, over-temperature protection, and leak detection (AquaSimian: capabilities to detect and autonomously respond to any leaks or motor faults by disconnecting motor power when the system is in an off-nominal state).<br>

**Wiring** — All wiring is routed through the joint housings and links. The communication bus is RS-485 or CAN (Alpha 5: Serial 232/485; CSIP ARM 5E: digital positioning with position feedback). The power and communication cables are oil-filled and pressure-compensated. Cable penetrators are rated to 7,500 m. The wiring harness is designed for continuous flexing at each joint.<br>

**Custom parts** — Machined joint housings (hard-anodised aluminium). Machined links (hard-anodised aluminium or 316 stainless steel). Pressure compensation membranes or pistons. Oil-filled actuator assemblies. Quick-change tool interface. Syntactic foam buoyancy modules. Custom PCBs for the drive circuits and communication bus.<br>

**Fasteners** — 316 stainless steel or titanium. All fasteners must be corrosion-resistant and rated for the operating depth. Thread locker (marine-grade) on all fasteners. Seals: double O-ring seals with backup rings on all rotating and static interfaces.<br>

**Tools required** — CNC machining (for joint housings and links). Pressure test chamber (for depth qualification). Oil filling and pressure compensation equipment. Marine-grade crimping tools. Torque wrench. Multimeter. Oscilloscope. ROV integration tools.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Brushless DC motor with oil-compatible insulation | 7 | Maxon / Faulhaber | ~$800 each | Actuators/BLDC |
| Harmonic gear (zero backlash, high ratio) | 7 | Harmonic Drive / Leaderdrive | ~$1,200 each | Actuators/Gearbox |
| Angular feedback potentiometer or encoder | 7 | Various | ~$200 each | Sensors/Encoder |
| Custom drive circuit PCB (oil-filled, pressure-compensated) | 7 | Custom | ~$300 each | Actuators/driver |
| 6-DOF force-torque sensor (subsea-rated) | 1 | ATI / Schunk | ~$8,000 | Sensors/ForceTorque |
| Four-finger gripper or parallel jaws | 1 | Custom / Olympic Arm | ~$5,000 | Manipulation/Gripper |
| Machined joint housings (hard-anodised aluminium) | 7 | Custom machine shop | ~$1,500 each | Structure/Housing |
| Machined links (aluminium or stainless) | 6 | Custom machine shop | ~$800 each | Structure/Link |
| Pressure compensation membranes | 7 | Custom | ~$100 each | PressureComp/Membrane |
| Oil (dielectric, low-viscosity) | 5 L | Various | ~$200 | PressureComp/Oil |
| Syntactic foam buoyancy modules | 1 set | Trelleborg / Engineered Syntactic Systems | ~$3,000 | Buoyancy/Foam |
| Subsea connectors and cable penetrators | 1 set | Teledyne / SEACON | ~$2,000 | Comms/Connectors |
| 316 stainless steel fasteners and seals | assorted | McMaster | ~$1,000 | Fasteners/Seals |
| ROV integration kit (mounting, cabling, interface) | 1 | Custom | ~$2,000 | Integration |
| Surface control console (joystick, display, PC) | 1 | Various | ~$5,000 | Operator/Console |
| **Total (research build)** | | | **~$45,000–$80,000** | |
| **Total (qualified commercial build)** | | | **~$120,000–$200,000** | |

---

## Systems

**Manifest** — The control system is a layered architecture. The surface control console runs the operator interface and high-level planning. The subsea control electronics run the joint servo loops and force control. The communication link is fiber optic or RS-485. The architecture follows the Huahai-4E layered control system and the AquaSimian supervised autonomy framework.<br>

**Firmware** — Each joint has a local drive circuit that runs the motor current loop at 10–20 kHz. The subsea control computer runs the joint position/velocity/force loops at 1 kHz. The surface control console runs the inverse kinematics and trajectory generation at 100–200 Hz. The AquaSimian limb features high power density actuators and a 6-DOF force-torque sensor, with capabilities to detect and autonomously respond to leaks or motor faults by disconnecting motor power when the system is in an off-nominal state.<br>

**Middleware** — The subsea control system is based on a network of embedded computers (Huahai-4E: three embedded PC/104 computers for servo control, task plan, and target sensor, communicating through UDP multicast in VxWorks). The surface control console is fiber-linked to the subsea control system. For ROS 2 integration, the subsea control system can be bridged to ROS 2 via a high-bandwidth link (fiber optic or Ethernet over the ROV tether), allowing the manipulator to participate in a larger autonomy stack.<br>

**Perception** — 6-DOF force-torque sensor at the end effector (AquaSimian: 6 degree of freedom force torque sensor). Joint position feedback from angular potentiometers or encoders. Optional: underwater camera on the wrist or end effector (Olympic Arm: SD tool camera with integrated LEDs, Imenco OE14-376 Light Ring Color Camera). Optional: ultrasonic probe array for autonomous grasp strategy (Huahai-4E: unique ultra-sonic probe array and underwater camera, autonomous grasp strategy based multi-sensor).<br>

**Control** — The control architecture has three levels: (1) Surface operator interface: the operator commands end-effector velocity, position, or force via a joystick or master arm. (2) Subsea high-level control: inverse kinematics, trajectory generation, and force control run on the subsea control computer. (3) Joint servo control: each joint runs a local current, velocity, and position loop. The force-torque sensor enables impedance control and force limiting. The AquaSimian limb performs tasks through a supervised autonomy framework that makes efficient use of operator input, 3D scene reconstructions, automated motion planning, and parameterized behaviors. The limb must robustly interact with its environment to perform tasks such as turning a subsea valve or inserting a hot stab.<br>

**Planning** — Automated motion planning for common intervention tasks (valve turning, hot stab insertion, tool operation). The operator selects a task from a menu, and the arm plans and executes the motion with force monitoring. The AquaSimian limb uses 3D scene reconstructions and parameterized behaviors for supervised autonomy. The CSIP ARM 5E features a learning function which stores the maneuvers performed by the arm and combines with a memory function for repeated actions.<br>

**Learning** — None in the base platform. The arm is designed for supervised autonomy, not learning. Optional: the logged task data (joint trajectories, forces, and outcomes) can be used to train task-specific policies offline.<br>

**Teleoperation** — Master-slave teleoperation with force feedback. The operator uses a joystick (CSIP ARM 5E: joystick for left/right slew and up/down movement, twist function for jaw rotate, thumbwheel for jaw open/close) or a master arm. The surface control console provides 3D visualization and telemetry (Alpha 5: intuitive user interface with 3D visualisation and telemetry). Force feedback from the force-torque sensor is displayed as a visual overlay or fed back to the master arm if equipped.<br>

**Safety** — Leak detection: each actuator housing has a leak sensor that detects water ingress. If a leak is detected, the arm disconnects motor power and notifies the operator through LED lighting on the Light Lids that seal the actuator assembly housings (AquaSimian: LED lighting on the Light Lids, disconnect motor power when in an off-nominal state). Over-current and over-temperature protection in each drive circuit. Joint limits enforced in the servo loop. Force limits enforced by the force-torque sensor and impedance controller. Emergency stop at the surface console. The pressure-compensated, oil-filled design provides intrinsic safety: even if a seal fails, water cannot enter the housing, and the arm fails gracefully.<br>

**Logging** — All joint positions, velocities, currents, forces, and torques logged at 1 kHz. Task outcomes and operator commands logged. Data used for post-mission analysis, fault diagnosis, and task optimization. The CSIP ARM 5E learning function stores maneuvers for repeated actions.<br>

**Networking** — Fiber optic link between the surface console and the subsea control system. RS-485 or CAN bus between the subsea control computer and the joint drive circuits. Ethernet or fiber over the ROV tether for ROS 2 integration.<br>

**Config files** — Joint limits and PID gains. Inverse kinematics parameters (link lengths, joint offsets). Force control parameters (impedance gains, force limits). Task definitions (valve turning, hot stab insertion, tool operation).<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `task_execution.launch.py`, `logging.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy (for surface integration). Subsea control software (VxWorks or Linux with real-time patches). Drive circuit firmware. Surface control console software (Qt or web-based GUI).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS (surface) | ubuntu.com | OS/Linux |
| VxWorks or Linux RT (subsea) | Various | Wind River / Linux | OS/RTOS |
| MoveIt 2 (optional) | Latest | ros.org | Planning/MoveIt |
| OpenCV (optional) | Latest | opencv.org | Perception |
| Force-torque control library | Custom | — | Control/Force |

---

## Interface

**Emits** — Joint positions, velocities, currents. End-effector pose. Force-torque sensor readings (6-axis). Leak detection status. Motor temperature. Camera feed (if fitted). Ultrasonic probe data (if fitted).<br>

**Accepts** — Joint position commands, joint velocity commands, joint torque commands. End-effector pose commands. End-effector velocity commands. Force/impedance commands. Task commands (valve turn, hot stab insert, etc.). Gripper open/close.<br>

**Serves** — Enable, disable, calibrate, home. Task execution services.<br>

**Executes** — Joint-space trajectories. Cartesian trajectories. Task-specific behaviors (valve turning, hot stab insertion, cable cutting, object recovery).<br>

**Extensions** — Tool changer interface. Additional sensors (camera, ultrasonic probe, conductivity sensor).<br>

**Frame conventions** — Base frame at the ROV mounting interface. Joint frames at each joint axis. End-effector frame at the tool center point. Force-torque sensor frame at the sensor origin.<br>

**Units** — SI. Meters, radians, seconds, Newtons, Newton-meters. Depth in meters. Pressure in bar.

---

## Model

**URDF / Xacro** — `model/triton.urdf.xacro`. Includes 7 revolute joints with position and velocity limits. Joint limits from the specification table. Links: base, azimuth, shoulder, elbow, elbow_roll, wrist_yaw, wrist_rotate, tool0. The URDF is used for surface visualization and motion planning.<br>

**SDF** — Used for Gazebo simulation with underwater physics (buoyancy, drag, added mass). The arm dynamics are simulated using the UUV Simulator or DAVE plugins.<br>

**Calibration** — Joint zero offsets (each joint’s potentiometer zero set to the mechanical zero corresponding to the arm’s home position). Force-torque sensor zero (tare with no load). Link lengths measured from CAD. Buoyancy and center of buoyancy measured experimentally. Drag coefficients identified through tank testing.<br>

**Dynamics** — Motor constants from datasheet. Harmonic gear ratios. Link masses from CAD. Buoyancy and center of buoyancy from syntactic foam and oil-filled voids. Drag coefficients identified through tank testing. The pressure-compensated, oil-filled actuators have different dynamics than air-filled actuators because the oil adds inertia and viscous damping. These effects are identified through system identification in a test tank.<br>

**Sensor transforms** — Force-torque sensor at the end effector, between the wrist and the gripper. Joint position sensors at each joint. Camera on the wrist or end effector. Ultrasonic probe array on the end effector (Huahai-4E).<br>

**Collision geometry** — Simple cylinders for links in simulation. Gripper collision geometry. Force-torque sensor collision geometry.<br>

**Visual geometry** — STL meshes from machined and printed parts.

---

## Trials

**Bench** — Motor direction, encoder counts, potentiometer readings, force-torque sensor calibration, leak sensor test. Pass/fail, measured values, date. Expected: all 7 motors respond to commands, potentiometers report position with sufficient resolution, force-torque sensor reads zero at rest and linear response under load, leak sensors trigger when submerged in a test tank.<br>

**Integration** — Communication bus test. Surface console to subsea control link. Inverse kinematics verification. Force control loop tuning. Pass/fail, measured values, date.<br>

**Field** — Pressure test in a hyperbaric chamber to 4,000 m equivalent (40 MPa). Tank test: turn a subsea valve, insert a hot stab, pick up and place objects. ROV integration test: mount on an ROV and perform a simulated intervention task. Pass/fail, measured values, date. The Huahai-4E was tested in a watertight test at 40 MPa and performed autonomous grasp experiments in a tank. The results of watertight test in 40 MPa, joint’s efficiency test and autonomous grasp experiments in tank are presented in the literature.<br>

**Endurance** — Continuous operation in a test tank for 100 hours. Joint temperature monitoring. Oil leak inspection. Seal wear inspection.<br>

**Environmental** — Tested in freshwater and saltwater. Pressure tested to 4,000 m equivalent. Corrosion tested per ASTM B117 salt spray.<br>

**Known limitations** — The arm is heavy in air (100 kg) and requires an ROV with sufficient payload capacity. The oil-filled, pressure-compensated design adds complexity and maintenance requirements (oil changes, seal inspections). The harmonic gears introduce some compliance and friction, which affects force control accuracy. The arm is not designed for high-speed motion; it is a precision manipulation tool, not a fast pick-and-place manipulator. The 7-DOF redundancy increases control complexity. The arm requires a trained operator and a surface control console.

---

## Log

**Build history** — Dated entries, what changed, why. The design is based on the Olympic Arm (Nauticus Robotics), the Reach Alpha 5 (Reach Robotics), the AquaSimian limb (JPL), the CSIP ARM 5E, and the Huahai-4E (HUST).<br>

**Open issues** — Links, priority, status. Oil compensation membrane reliability. Seal life at 4,000 m. Force control bandwidth with harmonic gears. Buoyancy optimization for different ROVs.<br>

**Changelog** — Version bumps, what triggered each.<br>

**Lessons learned** — The pressure-compensated, oil-filled design is the key enabler for deep-water electric manipulation. The force-torque sensor is essential for robust interaction with the environment. Supervised autonomy reduces operator workload and improves task success rate. The modular joint design simplifies repair and replacement (CSIP ARM 5E: modularity means spares can be used to repair the arm or a specific modular section can be flown out and fitted on site rather than returning the arm to a central repair base).<br>

**Cost actual** — Final spend vs. BOM estimate.

---

## Status

**Condition** — draft.<br>

**Blockers** — None. Ready to begin detailed design and sourcing.<br>

**Next steps** — Finalise BOM, source actuators and force-torque sensor, machine joint housings, assemble first joint, pressure test, assemble full arm, tank test. Milestone 1: single joint pressure test to 40 MPa. Milestone 2: full arm pressure test. Milestone 3: tank test with valve turning and hot stab insertion. Milestone 4: ROV integration and field trial. Milestone 5: supervised autonomy task library. Milestone 6: optional ultrasonic probe array and autonomous grasp strategy.

---

**Note on this Shell:** The triton manipulator is a distinct class in the library. Unlike the diver and mariner platforms (which are mobile vehicles), triton is a fixed-base manipulator designed for ROV integration. The pressure-compensated, oil-filled electric actuator architecture is the defining engineering feature: it enables deep-water electric manipulation without hydraulics, reducing weight, complexity, and environmental risk. The reference platforms (Olympic Arm, Alpha 5, AquaSimian, CSIP ARM 5E, Huahai-4E) demonstrate that all-electric manipulators can match hydraulic arms in strength and dexterity while being cleaner, lighter, and more controllable. This Shell is the reference for a 7-DOF underwater electric manipulator with force-torque sensing, supervised autonomy, and 4,000 m depth rating.
