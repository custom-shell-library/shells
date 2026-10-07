# nova

**Class:** space (free-flying manipulator)<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Free-flying space robot for on-orbit servicing, inspection, and assembly. Carries a 7-degree-of-freedom dexterous manipulator on a propulsive free-flyer bus with reaction wheels for attitude control and cold-gas or electric propulsion for translation. Performs satellite inspection, anomaly resolution, ORU (orbital replacement unit) exchange, and cooperative assembly tasks. The manipulator and the base are dynamically coupled: moving the arm imparts reaction torques and forces on the base, and the base's motion changes the arm's workspace and dynamics. This coupling is the defining engineering challenge of the platform class, and it is why space robots cannot simply reuse terrestrial manipulator controllers.<br>

**Environment** — Low Earth orbit (LEO) and geosynchronous Earth orbit (GEO). Vacuum, microgravity (10⁻⁶ g in LEO, effectively zero in GEO), thermal cycling (−150 °C to +150 °C on external surfaces), ionising radiation, atomic oxygen (LEO only), and plasma. Not for atmospheric flight or surface operation.<br>

**Mission** — Provide a research-scale, reproducible free-flying manipulator platform for on-orbit servicing research, proximity operations, and coupled dynamics experiments. The platform is designed to be ground-testable in a flat-floor or air-bearing facility, and to be flight-qualifiable for a small satellite mission. It exists to advance the state of autonomous and supervised on-orbit manipulation, following the heritage of ETS-VII, the DARPA RSGS program, and the DYMAFLEX free-flying manipulator experiment.<br>

**Operator** — Single operator via a ground station or an on-orbit crew interface. The operator commands end-effector pose or velocity, or selects scripted tasks (inspection scan, ORU exchange, docking). The robot executes the task with closed-loop control using onboard force-torque sensing, vision, and reaction-wheel/propulsion coordination. Supervised autonomy is the primary mode; full autonomy is a research goal.<br>

**Reusability** — Repeatable build for a research programme. The bus is based on the Astrobee free-flyer architecture (modular, open-source, 32 cm cube, fan propulsion for ISS internal use, thruster propulsion for external use). The manipulator is based on the ETS-VII and RSGS arm heritage (7 joints, tool drive, 2–3 m reach). Ground-testable in a flat-floor facility with a gantry offload or an air-bearing table.

---

## Spec

**Physical** — Bus: approximately 500 × 500 × 500 mm cube (research scale) or 1,000 × 1,000 × 1,000 mm for a larger variant. Bus mass 50–100 kg (research scale) or 500–1,000 kg (flight scale). Manipulator mass 15–30 kg per arm (ETS-VII arm: 2 m, 6 DOF; RSGS arm: 3 m, 7 joints plus tool drive). Total system mass 100–200 kg (research scale) or 1,500–4,400 kg (flight scale, based on the 4,400 kg MRV). Structural materials: aluminium honeycomb, carbon fibre reinforced polymer (CFRP) for the bus panels and arm links, titanium for high-stress joints. The manipulator links are CFRP tubes with titanium end fittings, following the RSGS arm design which is robust enough to be fully testable in Earth gravity — a rare characteristic for spaceflight robotic arms.<br>

**Kinematic** — 7 degrees of freedom per manipulator arm (RSGS: seven high-strength, high-performance joints plus a tool drive). Joint configuration: azimuth (rotary), shoulder pitch, shoulder roll, elbow pitch, forearm roll, wrist pitch, wrist yaw, plus a tool drive. The 7-DOF redundant configuration allows the arm to maintain end-effector pose while avoiding joint limits, singularities, and collisions, and enables reactionless motion (moving the arm without disturbing the base attitude) using the reaction null-space. The arm reach is 2 m (ETS-VII) or 3 m (RSGS). The bus itself has 6 degrees of freedom: 3 translational (X, Y, Z) and 3 rotational (roll, pitch, yaw), actuated by thrusters and reaction wheels.<br>

**Dynamic** — Arm: maximum tip speed 50 mm/s (ETS-VII: 50 mm/s), 250 mm/s for a high-performance arm (DYMAFLEX: 25 cm/s maximum tip speed). End-tip positioning accuracy 1.3 mm (ETS-VII: 1.3 mm positioning accuracy at end tip). End-tip force 40 N and torque 10 N·m (ETS-VII: more than 40 N force, 10 N·m torque at end tip). Bus: maximum translational thrust 0.8–3.0 N per axis depending on thruster configuration (Astrobee: 0.849 N max thrust on x-axis, 0.406 N on y-axis, with 12 adjustable flow-rate nozzles; ATMOS: 3.0 N max thrust on x and y axes). Maximum rotational rate 5 deg/s (ETS-VII: 5 deg/s velocity at end tip). The coupled dynamics between the arm and the free-flying base are the dominant engineering concern: the arm's motion induces base translation and rotation, and the base's motion changes the arm's effective inertia and workspace.<br>

**Power** — Bus power: 100–500 W average, 1,000–2,000 W peak during high-torque manipulation. Solar arrays (deployable, 2 wings) with battery storage for eclipse. Bus voltage 28 V DC (standard spacecraft bus) or 100 V DC for high-power variants. Arm power: 200–500 W peak per arm. The RSGS payload draws power, data, and control services from avionics boxes. All power conditioning via radiation-hardened DC-DC converters. Battery: lithium-ion, 100–500 Wh depending on mission duration and eclipse fraction.<br>

**Thermal** — External surfaces: −150 °C to +150 °C. Internal electronics: −20 °C to +50 °C (controlled by heaters and thermal blankets). The arm joints are thermally isolated from the bus and use heaters to maintain lubricant viscosity and encoder accuracy. Radiators reject waste heat. Multi-layer insulation (MLI) blankets cover the bus and arm. Thermal-vacuum testing is mandatory before flight (RSGS underwent extreme thermal-vacuum exposures at NRL facilities).<br>

**Environmental** — Vacuum: 10⁻⁶ Torr or lower. Microgravity: 10⁻⁶ g in LEO, effectively zero in GEO. Radiation: 10–100 krad total ionising dose (TID) depending on orbit and mission duration. Atomic oxygen (LEO only): erodes exposed polymers; requires AO-resistant coatings (e.g., SiO₂) on MLI and CFRP. Plasma: charging and discharging; requires conductive coatings and grounding. Debris: micrometeoroid and orbital debris (MMOD) shielding for critical components.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $250,000–$500,000 for a ground-testable research build, or $5–15 million for a flight-qualified unit. Space hardware is expensive because of qualification testing, radiation hardening, and low production volume.<br>

**Structure** — Bus: aluminium honeycomb panels with CFRP face sheets, assembled into a cube or rectangular box. The bus houses the avionics, batteries, reaction wheels, thruster tanks, and the arm mounting interface. The Astrobee bus is a 32 cm cube with an exterior shell of Ultem and aluminium, three smartphone computers, three payload bays, and berths for two free flyers. The manipulator: CFRP tubular links with titanium end fittings and aluminium joint housings. Each joint contains a brushless DC motor, a harmonic drive or cycloidal reducer, an absolute encoder, a torque sensor, and a thermal control heater. The joint housings are sealed against vacuum and use space-rated lubricants (e.g., Braycote or Fomblin). The tool drive at the end of the arm accepts interchangeable tools (grippers, cameras, lights, torque tools) via a robotic tool changer (RSGS: each arm accommodates multiple interchangeable satellite-servicing tools; NRL outfitted the arms with control electronics, cameras, lights, and a robotic tool changer).<br>

**Actuation** — Arm: 7× brushless DC motors with harmonic drives. The RSGS arms use seven high-strength, high-performance joints. The ETS-VII arm uses DC brushless motors. Joint torque is sized for the manipulation task: 10 N·m at the end tip (ETS-VII) requires approximately 50–100 N·m at the shoulder joint depending on arm configuration. Bus: 12× cold-gas or electric thrusters (Astrobee: 12 adjustable flow-rate nozzles, 0.849 N max thrust on x-axis; ATMOS: 3.0 N max thrust on x and y axes) and 3–4 reaction wheels for attitude control. The thrusters provide translation and reaction-wheel desaturation; the reaction wheels provide fine attitude control without propellant consumption. The RSGS arms are robust enough to be fully testable in Earth gravity, which is unique among spaceflight robotic arms. The DYMAFLEX manipulator is a high-performance, low-mass 4-DOF arm designed to operate at a maximum tip speed of 25 cm/s on a free-floating base.<br>

**Locomotion** — Free-flying. The bus translates and rotates in 6 DOF using thrusters and reaction wheels. The arm does not locomote; it manipulates. The bus can operate in two modes: (1) **Free-flying mode** — the bus actively controls its position and attitude using thrusters and reaction wheels, allowing it to approach, inspect, and manipulate a target. (2) **Free-floating mode** — the bus is not actively controlled (thrusters off), and the combined bus-arm system conserves momentum; the arm's motion induces base motion, and the controller must account for this coupling. The ETS-VII demonstrated both modes, and the DYMAFLEX experiment specifically investigated the coupled dynamics between the manipulator and a free-floating base.<br>

**Manipulation** — 7-DOF manipulator with a tool drive at the end. Tools: parallel-jaw gripper, three-finger dexterous hand, torque tool (for bolts), camera and light tool, and specialised servicing tools (e.g., refuelling nozzle, ORU grapple). The RSGS arm accommodates multiple interchangeable satellite-servicing tools, including a suite of modular tools, sensors, and advanced lighting for delicate mechanical interventions. The arm can install Mission Extension Pods (MEPs) — propulsion “jet packs” that extend the life of existing GEO satellites by six or more years. The ETS-VII arm has a three-finger multi-sensor hand with active and passive degrees of freedom for precise manipulation. The arm can also be used for reactionless manipulation: by moving the arm along the reaction null-space, the base attitude is undisturbed, which is essential for precise pointing during servicing.<br>

**Power system** — Solar arrays: 2 deployable wings (RSGS/SIS: 2 deployable solar arrays, batteries). Bus voltage 28 V DC or 100 V DC. Battery: lithium-ion, 100–500 Wh. Power distribution: radiation-hardened DC-DC converters, latching current limiters, and fuses. Arm power: 200–500 W peak per arm, distributed through the avionics boxes that provide power, data, and control services to the arms (RSGS: avionics boxes provide power, data, and control services to the arms).<br>

**Wiring** — Internal harness: radiation-hardened cables, shielded twisted pairs for data, and power cables sized for peak arm current. The harness routes through the bus and the arm joints with service loops at each joint. Connectors: MIL-DTL-38999 or equivalent space-rated connectors. The arm harness includes motor power, encoder signals, torque sensor signals, heater power, and thermistor signals. All wiring is tested for vacuum compatibility (no outgassing) and radiation tolerance.

**Custom parts** — Bus structure (aluminium honeycomb panels). Arm links (CFRP tubes with titanium end fittings). Joint housings (aluminium or titanium). Tool changer interface. Reaction wheel assemblies. Thruster assemblies. Avionics boxes. Thermal blankets (MLI). Radiators. Solar array substrates. All custom parts require qualification testing (vibration, thermal-vacuum, EMC, radiation).

**Fasteners** — Titanium and stainless steel fasteners, space-rated. All fasteners are secured with thread locking compound (space-rated, low-outgassing) or safety wire. No fasteners are allowed to loosen in launch vibration or thermal cycling.

**Tools required** — Cleanroom (ISO Class 7 or better). Vacuum chamber for thermal-vacuum testing. Vibration table for launch qualification. EMC test facility. Radiation test facility. Flat-floor or air-bearing facility for ground testing (e.g., the OOS-SIM facility at DLR: 10 m × 7.5 m × 5 m, with 2 industrial robots (KR120, 1,049 kg each), 1 light-weight robot (LWR IV+, 15 kg), and 1 haptic input device (LWR IV)). Torque wrenches, cleanroom tools, ESD-safe tools.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Space-rated brushless DC motor with harmonic drive | 7 | Maxon / Harmonic Drive | ~$15,000 each | Actuators/BLDC |
| Absolute encoder (space-rated) | 7 | Renishaw / Heidenhain | ~$5,000 each | Sensors/Encoder |
| Joint torque sensor (space-rated) | 7 | ATI / Schunk | ~$8,000 each | Sensors/Torque |
| Reaction wheel assembly (space-rated) | 3–4 | Blue Canyon / Honeywell | ~$50,000 each | Actuators/ReactionWheel |
| Cold-gas thruster assembly | 12 | VACCO / Moog | ~$5,000 each | Actuators/Thruster |
| Cold-gas tank (high-pressure) | 1–2 | Various | ~$20,000 | Propulsion/Tank |
| Solar array (deployable, 2 wings) | 1 set | Various | ~$100,000 | Power/Solar |
| Lithium-ion battery (space-rated) | 1 | Various | ~$50,000 | Power/Battery |
| Avionics box (power, data, control) | 2 | Custom | ~$80,000 each | Compute/Avionics |
| Onboard computer (radiation-hardened) | 1–2 | BAE / Cobham | ~$100,000 | Compute/RadHard |
| Force-torque sensor (6-axis, space-rated) | 1 | ATI / Schunk | ~$25,000 | Sensors/ForceTorque |
| Tool changer (robotic) | 1 | Custom / NRL | ~$30,000 | Manipulation/ToolChanger |
| Gripper tool (parallel jaw) | 1 | Custom | ~$15,000 | Manipulation/Gripper |
| Torque tool (for bolts) | 1 | Custom | ~$10,000 | Manipulation/Tool |
| Camera and light tool | 1 | Custom | ~$20,000 | Sensors/Camera |
| CFRP arm links (2 m, 7 joints) | 1 set | Custom | ~$50,000 | Structure/Arm |
| Aluminium honeycomb bus panels | 1 set | Custom | ~$40,000 | Structure/Bus |
| Thermal blankets (MLI) | 1 set | Sheldahl / Dunmore | ~$15,000 | Thermal/MLI |
| Radiators | 1 set | Custom | ~$20,000 | Thermal/Radiator |
| Cleanroom tools and fasteners | assorted | Various | ~$10,000 | Assembly |
| **Total (research build)** | | | **~$250,000–$500,000** | |
| **Total (flight build)** | | | **~$5–15 million** | |

---

## Systems

**Manifest** — See detailed manifest below.

**Firmware** — The onboard computer runs the flight software, which is responsible for: (1) arm joint control (position, velocity, torque), (2) reaction wheel and thruster control for bus attitude and translation, (3) coupled dynamics compensation, (4) force-torque control for manipulation, (5) vision processing for target tracking and pose estimation, (6) fault detection, isolation, and recovery (FDIR), and (7) communication with the ground station. The RSGS flight software includes scripted control modes (the robotic arm moves through a pre-planned trajectory using only proprioceptive sensors), partial autonomy (the arm carries out a task using environmental sensors such as end-effector cameras or the force-torque sensor), and teleoperation (the robotic arm executes onboard servo control and compliance control as needed, but all other control loops are closed via the human operator's eyes and hands). The software is written in C or C++ and runs on a radiation-hardened processor (e.g., BAE RAD750 or Cobham GR740). The control loop runs at 100–1,000 Hz for the arm joints and 10–100 Hz for the bus.

**Middleware** — No ROS in the flight software. Space robots use custom, radiation-hardened, deterministic software. For ground testing and research, ROS 2 can be used on the ground station and in the ground-test version of the robot. The DLR OOS-SIM facility uses a hard real-time control system with a two-finger gripper on the LWR and a haptic input device. For the research build, ROS 2 with a real-time patch can be used on the ground-test bus, with a clear separation between the flight software (deterministic, radiation-hardened) and the research software (ROS 2, modular, testable).

**Perception** — End-effector camera and lights (RSGS: cameras and lighting; ETS-VII: cameras and force sensors). 6-axis force-torque sensor at the wrist (ETS-VII: force sensor; RSGS: force-torque sensor). Star trackers and sun sensors for bus attitude determination. IMU for bus rate and acceleration. Optional: LiDAR or flash LiDAR for proximity operations and 3D reconstruction of the target satellite. Optional: docking camera for final approach. The ETS-VII used virtual graphics prediction and bilateral control for teleoperation, with a 1.3 mm end-tip positioning accuracy.

**Control** — Three-level control architecture: (1) **Task level** (ground station or onboard autonomy): the operator or autonomy software selects a task (inspection, ORU exchange, docking) and the task is decomposed into arm and bus motions. (2) **Coordinated control level** (onboard, 10–100 Hz): the arm and bus motions are coordinated to achieve the task while respecting momentum, thermal, and power constraints. The controller compensates for the coupled dynamics between the arm and the free-flying base. Reaction null-space control is used for reactionless manipulation; when reactionless motion is not possible, the reaction wheels absorb the angular momentum and the thrusters desaturate the wheels. (3) **Joint servo level** (onboard, 100–1,000 Hz): each joint runs a position, velocity, or torque loop. The force-torque sensor at the wrist enables impedance control and force control. The ETS-VII demonstrated precise telerobotic control with 1.3 mm positioning accuracy at the end tip, 50 mm/s velocity, 5 deg/s angular velocity, and more than 40 N force and 10 N·m torque at the end tip. The DYMAFLEX experiment investigated the coupled dynamics between the manipulator and the free-floating base, and the associated controller-based mitigation strategies.

**Planning** — Onboard motion planning for the arm: trajectory generation with joint limits, singularity avoidance, collision avoidance, and reaction null-space constraints. Bus motion planning: approach trajectories, station-keeping, and collision avoidance with the target satellite. The RSGS uses scripted control modes with pre-planned trajectories, partial autonomy with environmental sensors, and teleoperation. The OOS-SIM facility uses a hard real-time control system with a two-finger gripper and a haptic input device for teleoperation.

**Learning** — None in the flight software. Space robots are conservative; learning-based control is not yet flight-qualified for safety-critical manipulation. Research on learning-based space manipulation is active, but the flight platform uses model-based control with verified flight software. For the research build, reinforcement learning and imitation learning can be used in the ground-test environment, but the policies must be verified and validated before any flight deployment.

**Teleoperation** — Ground station or on-orbit crew interface. The operator commands end-effector pose or velocity, or selects scripted tasks. The RSGS control modes include: (1) **Scripted** — the robotic arm moves through a pre-planned trajectory using only proprioceptive sensors. (2) **Partial autonomy** — the robotic arm carries out a task using environmental sensors such as end-effector cameras or the force-torque sensor. (3) **Teleoperation** — the robotic arm executes onboard servo control and compliance control as needed, but all other control loops are closed via the human operator's eyes and hands. The ETS-VII was teleoperated from a ground control station in Japan, with a time delay of approximately 5–7 seconds for a GEO relay; the robot used virtual graphics prediction and bilateral control to compensate for the delay. The OOS-SIM facility uses a haptic input device (LWR IV) for teleoperation with force feedback.

**Safety** — FDIR (fault detection, isolation, and recovery) is mandatory. The flight software monitors joint torque, motor current, temperature, encoder health, and communication link status. If a fault is detected, the arm enters a safe state (hold position, retract, or release the tool). The bus monitors attitude, reaction wheel speed, thruster health, and power status. Collision avoidance with the target satellite is enforced by the motion planner and by proximity sensors. The RSGS arms are robust enough to be fully testable in Earth gravity, which allows ground verification of the safety-critical functions. The flight software is verified and validated to NASA or ESA software standards (e.g., NASA-STD-8739.8, ECSS-Q-ST-80C).

**Logging** — All telemetry is logged: joint positions, velocities, torques, motor currents, temperatures, force-torque sensor data, camera images, bus attitude, reaction wheel speeds, thruster status, power status, and FDIR events. Data is stored onboard and downlinked to the ground station. The log is used for post-mission analysis, anomaly investigation, and software improvement.

**Networking** — Ground station link: S-band or Ka-band radio, with a data rate of 1–100 Mbps depending on the link budget. Onboard: MIL-STD-1553, SpaceWire, or Ethernet for the internal data bus. The arm and bus communicate over a deterministic, radiation-tolerant bus (e.g., CAN or SpaceWire). Time synchronisation via a spacecraft clock and a GPS receiver (if in LEO).

**Config files** — Flight software parameters: joint limits, torque limits, velocity limits, controller gains, FDIR thresholds, thermal limits, power limits. Mission configuration: target satellite model, task sequence, tool selection. All config files are verified and validated before upload.

**Launch files** — None. The flight software is a single, deterministic executable. Ground-test software may use ROS 2 launch files for modular testing.

**Dependencies** — Flight software: custom, radiation-hardened, deterministic. Ground-test software: ROS 2, Python, C++, real-time Linux (PREEMPT_RT), Gazebo or Isaac Sim for simulation, and a ground-test version of the flight software with instrumented interfaces.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Flight software | Custom | NASA / ESA / DARPA | Control/Flight |
| FDIR software | Custom | NASA / ESA | Safety/FDIR |
| ROS 2 (ground test) | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu (ground test) | 24.04 LTS | ubuntu.com | OS/Linux |
| Gazebo (ground test) | Harmonic | gazebosim.org | Simulation |
| Isaac Sim (ground test) | Latest | NVIDIA | Simulation |
| C++ | 17+ | iso.org | Flight/Ground |
| Python (ground test) | 3.x | python.org | Ground/Analysis |

---

## Interface

**Emits** — Joint positions, velocities, torques. End-effector pose and wrench (from force-torque sensor). Bus attitude, rate, position, velocity. Reaction wheel speeds. Thruster status. Power status. Camera images. FDIR status. All telemetry is downlinked to the ground station at the link data rate.

**Accepts** — Joint position, velocity, and torque commands. End-effector pose and velocity commands. Bus attitude, position, and velocity commands. Task commands (inspection scan, ORU exchange, docking). Tool selection commands. FDIR commands (safe mode, reset).

**Serves** — Task execution services. Tool change services. Calibration services.

**Executes** — Joint-space trajectories. Cartesian trajectories. Task-specific behaviours (inspection, ORU exchange, docking, refuelling). Reactionless manipulation. Bus manoeuvres (approach, station-keeping, retreat).

**Extensions** — Tool changer interface (interchangeable tools). Additional sensors (cameras, LiDAR, docking camera). Additional payloads (mission extension pods, refuelling modules).

**Frame conventions** — Bus frame: origin at the bus centre of mass, X forward, Y starboard, Z down. Arm base frame: at the arm mounting interface. Joint frames: at each joint axis. End-effector frame: at the tool centre point. Target frame: at the target satellite's centre of mass or grapple fixture. All frames are defined in the flight software and verified in ground testing.

**Units** — SI. Meters, radians, seconds, Newtons, Newton-meters, kilograms, watts, volts, amperes, degrees Celsius, pascals (vacuum), and grays (radiation dose).

---

## Model

**URDF / Xacro** — Not used in flight software. The arm and bus kinematics are defined in the flight software as a serial kinematic chain with 7 revolute joints and a free-flying base with 6 DOF. For ground testing, a URDF can be generated for RViz and MoveIt 2 visualisation and planning.

**SDF** — Not used in flight software. For ground testing, Gazebo or Isaac Sim can simulate the coupled dynamics of the free-flying base and the arm, with microgravity and vacuum conditions. The DLR OOS-SIM facility simulates the orbital rendezvous and servicing scenario with two industrial robots (KR120) and a light-weight robot (LWR IV+), and a haptic input device (LWR IV) for teleoperation.

**Calibration** — Joint zero offsets (each joint's absolute encoder zero set to the mechanical zero). Kinematic calibration of the arm link lengths. Force-torque sensor zero and calibration. Camera intrinsics and extrinsics. Reaction wheel torque calibration. Thruster thrust and alignment calibration. Star tracker and IMU alignment calibration. All calibrations are performed on the ground before launch and verified on orbit (RSGS: on-orbit checkout and calibration equipment; ETS-VII: performance evaluation of satellite-mounted robot system).

**Dynamics** — The dynamics of a free-flying space robot are fundamentally different from a fixed-base manipulator. The combined bus-arm system conserves linear and angular momentum (in free-floating mode), so the arm's motion induces base motion. The equations of motion include the base inertia, the arm inertia, the coupling terms (Jacobian and inertia coupling), and the momentum conservation constraint. The controller must either compensate for the coupling (using the reaction null-space or a momentum-based controller) or actively control the base (using reaction wheels and thrusters) to maintain the desired base attitude. The DYMAFLEX experiment was designed specifically to investigate this coupled dynamics on a parabolic flight, moving the system from TRL 4 to TRL 6. The ETS-VII demonstrated precise telerobotic control with 1.3 mm end-tip accuracy in the presence of this coupling. The RSGS arms are robust enough to be fully testable in Earth gravity, which allows ground verification of the dynamics and controller.

**Sensor transforms** — Force-torque sensor at the wrist, between the last joint and the tool. Cameras on the end effector and on the bus. Star trackers on the bus. IMU at the bus centre of mass. Reaction wheels at their mounting locations. All transforms are defined in the flight software and verified by calibration.

**Collision geometry** — For ground testing and simulation, the arm links are modelled as cylinders and the bus as a box. For flight, collision avoidance is enforced by the motion planner using a simplified geometric model of the arm, the bus, and the target satellite.

**Visual geometry** — For ground testing and simulation, the arm links and bus are modelled with high-fidelity meshes. For flight, the visual model is not used; the motion planner uses the geometric model.

---

## Trials

**Bench** — Joint motor direction, encoder counts, torque sensor calibration, force-torque sensor calibration, reaction wheel spin test, thruster leak test, power system test, communication link test. Pass/fail, measured values, date. Expected: all 7 joints respond to commands, encoders report position with arc-second resolution, torque sensors read zero at rest and linear response under load, reaction wheels spin up and down smoothly, thrusters fire with repeatable thrust, power system delivers stable voltage, communication link closes.

**Integration** — Arm-bus integration. Coupled dynamics test on an air-bearing table or flat-floor facility. Reaction null-space verification. Reaction wheel and thruster coordination test. Force-torque control test. Camera and vision test. Pass/fail, measured values, date. The ETS-VII demonstrated precise telerobotic control with 1.3 mm positioning accuracy, 50 mm/s velocity, 5 deg/s angular velocity, and more than 40 N force and 10 N·m torque at the end tip. The DYMAFLEX experiment demonstrated the coupled dynamics on a parabolic flight.

**Field** — Ground-test facility: flat-floor or air-bearing table with a mock target satellite. Inspection scan task. ORU exchange task. Docking task. Tool change task. Reactionless manipulation task. Pass/fail, measured values, date. The DLR OOS-SIM facility (10 m × 7.5 m × 5 m, 2× KR120 robots, LWR IV+ robot, LWR IV haptic input device) is a reference ground-test facility for this class of robot.

**Endurance** — Continuous operation in the ground-test facility for 100 hours. Thermal cycling test (−150 °C to +150 °C) in a thermal-vacuum chamber. Vibration test (launch qualification levels). EMC test. Radiation test (TID and single-event effects). Pass/fail, measured values, date. The RSGS payload underwent launch vibration stress simulations, electromagnetic compatibility testing, and extreme thermal-vacuum exposures at NRL facilities.

**Environmental** — Thermal-vacuum: −150 °C to +150 °C external, −20 °C to +50 °C internal. Vacuum: 10⁻⁶ Torr or lower. Radiation: 10–100 krad TID. Atomic oxygen: AO-resistant coatings on MLI and CFRP. Plasma: conductive coatings and grounding. MMOD: shielding for critical components.

**Known limitations** — The coupled dynamics between the arm and the free-flying base are the dominant engineering challenge. Reaction wheels have limited angular momentum capacity and require periodic desaturation by thrusters, which consumes propellant. Thrusters consume propellant and cannot be refuelled without a servicing mission. The arm's reach and payload capacity are limited by the mass and power budget of the bus. Thermal control in vacuum is difficult; the arm joints must be heated to maintain lubricant viscosity and encoder accuracy. Radiation hardening and qualification testing drive cost and schedule. The flight software must be verified and validated to NASA or ESA standards, which is a multi-year, multi-million-dollar effort. Ground testing of a free-flying robot requires a flat-floor or air-bearing facility, which is expensive and not widely available. The ETS-VII was launched in 1997 and the RSGS payload launched in 2026; the field is mature but low-volume.

---

## Log

**Build history** — Dated entries, what changed, why. The design is based on the ETS-VII (launched 1997, first free-flying space robot, 2 m, 6-DOF manipulator, 1.3 mm end-tip accuracy), the DARPA RSGS program (two 7-joint arms, 3 m reach, launched 2026 on the MRV), the DYMAFLEX experiment (4-DOF manipulator, free-floating base, parabolic flight), the Astrobee free-flyer (32 cm cube, ~9.1 kg, fan propulsion, ISS internal use), and the DLR OOS-SIM facility (ground-test facility for orbital servicing).

**Open issues** — Links, priority, status. Reaction null-space control for coupled dynamics. Reaction wheel desaturation without propellant. Thermal control of arm joints in vacuum. Radiation hardening of arm electronics. Ground testing of free-flying dynamics. Flight qualification of force-torque sensors.

**Changelog** — Version bumps, what triggered each.

**Lessons learned** — The coupled dynamics between the arm and the free-flying base are the defining engineering challenge. Reaction null-space control and momentum-based control are the key techniques. The RSGS arms are robust enough to be fully testable in Earth gravity, which is a rare and valuable characteristic. The ETS-VII demonstrated that precise telerobotic control is possible with time delay using virtual graphics prediction and bilateral control. The DYMAFLEX experiment demonstrated the importance of parabolic flight testing for TRL advancement.

**Cost actual** — Final spend vs. BOM estimate. Space hardware is expensive because of qualification testing, radiation hardening, and low production volume. The SIS/RSGS contract was valued at US$228 million. A research-scale ground-testable unit is expected to cost $250,000–$500,000; a flight-qualified unit is expected to cost $5–15 million.

---

## Status

**Condition** — draft.

**Blockers** — None for the ground-testable research build. Flight build requires a mission, a launch opportunity, and a flight qualification programme.

**Next steps** — Finalise BOM, source space-rated actuators and sensors, design the bus and arm, build the ground-test unit. Milestone 1: bench test all 7 joints and sensors. Milestone 2: arm-bus integration on an air-bearing table. Milestone 3: coupled dynamics test on a flat-floor or air-bearing facility. Milestone 4: reaction null-space control verification. Milestone 5: inspection, ORU exchange, and docking tasks on a mock target. Milestone 6: thermal-vacuum, vibration, EMC, and radiation qualification for flight. Milestone 7: flight build and launch. Milestone 8: on-orbit checkout and calibration. Milestone 9: on-orbit servicing demonstrations.

---

**Note on this Shell:** nova is a distinct platform class in the library. Unlike terrestrial robots, the space free-flying manipulator operates in microgravity, vacuum, and thermal cycling, and its base is not fixed — the arm and the bus are dynamically coupled. This coupling is the defining engineering challenge, and it is why space robots cannot simply reuse terrestrial manipulator controllers. The reference platforms (ETS-VII, DARPA RSGS, DYMAFLEX, Astrobee, DLR OOS-SIM) demonstrate the state of the art: 1.3 mm end-tip accuracy on ETS-VII, two 7-joint 3 m arms on RSGS, coupled dynamics investigation on DYMAFLEX, modular free-flyer architecture on Astrobee, and ground-test facility design on OOS-SIM. The RSGS payload launched on the MRV in July 2026 and will begin servicing GEO satellites in 2027, marking the transition of on-orbit servicing from demonstration to commercial operation. This Shell is the reference for a free-flying space manipulator with a 7-DOF arm, reaction wheels and thrusters for bus control, force-torque sensing for manipulation, and flight-qualified software.
