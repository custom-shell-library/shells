# emu

**Class:** humanoid<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Small bipedal humanoid for research into walking, dynamic balance, whole-body manipulation, and sim-to-real transfer. Walks, stands, steps over obstacles, recovers from pushes, and reaches for objects. This is the hardest platform class in the library: bipedal locomotion is inherently unstable, and every component must be lightweight, strong, and torque-dense.<br>

**Environment** — Indoor hard floors and low-pile carpet. Flat to mildly uneven terrain. Not for outdoor use, stairs (without a trained policy), wet surfaces, or high winds. Operating temperature 10–40 °C.<br>

**Mission** — Provide a fully open-source, reproducible bipedal humanoid platform for locomotion and manipulation research. Stand, walk, turn, step, squat, recover from disturbances. Optional arm manipulation. Serves as a testbed for reinforcement learning and imitation learning policies trained in simulation and transferred to hardware.<br>

**Operator** — Single operator via wireless gamepad or ROS 2 teleop. Higher-level commands (velocity, body height, foot placement) sent as twists or custom messages. Supervised autonomy possible with a trained locomotion policy.<br>

**Reusability** — Fully open-source design. All structural components 3D-printable. All actuators built from off-the-shelf drone motors and 3D-printed cycloidal reducers. Repeatable build.

---

## Spec

**Physical** — 8–10 kg total mass depending on battery and configuration. 1000 mm standing height. 300 × 200 mm footprint. 3D-printed PA12-CF body and limb links with aluminum structural reinforcement at high-load joints. Ground clearance adjustable 0–150 mm via leg joints. Center of mass at hip height, slightly forward for stability during forward walking.<br>

**Kinematic** — 20 DOF base configuration. Two 6-DOF legs: hip roll, hip pitch, hip yaw, knee pitch, ankle pitch, ankle roll. Two 4-DOF arms: shoulder pitch, shoulder roll, elbow pitch, wrist yaw. Expandable to 26+ DOF with wrist pitch, wrist roll, and dexterous hands. Leg segment lengths: thigh 250 mm, shin 250 mm, foot length 180 mm. Arm segment lengths: upper arm 180 mm, forearm 180 mm.<br>

**Dynamic** — Peak knee joint torque 60 Nm. Peak hip joint torque 40 Nm. Peak ankle joint torque 25 Nm. Peak shoulder torque 15 Nm. Peak elbow torque 8 Nm. Walking speed 0.5 m/s nominal, 1.0 m/s maximum. Body mass 8 kg, payload 2 kg additional. Capable of standing on one leg, stepping over 100 mm obstacles, and recovering from lateral pushes of 50 N at torso height.<br>

**Power** — 6S LiPo (22.2V nominal, 5000 mAh, 111 Wh). Runtime 45–90 minutes depending on activity. XT60 connector. 24V direct to motor driver boards. 5V 5A buck converter for Raspberry Pi 5. 5V 3A buck for sensors. 3.3V for IMU.<br>

**Thermal** — 10–40 °C operating. Passive cooling. Motors have aluminum stator carriers that act as heat sinks. Sustained high-torque operation will raise motor temperature; drivers report temperature and current monitoring is implemented for derating.<br>

**Environmental** — Indoor only. Not IP-rated. Not for rain, dust, or outdoor use in wind.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $3,200–$4,000.<br>

**Structure** — 3D-printed PA12-CF (carbon fiber reinforced nylon) for the torso, hip housings, thigh links, shin links, foot links, and arm links. The design follows the open-source humanoid architecture pioneered by the Berkeley Humanoid Lite project, which demonstrates that a fully functional humanoid can be built from 3D-printed parts and off-the-shelf components. Aluminum 6061 reinforcement plates are used at the hip and knee joints where cyclic loading is highest. The torso is a single printed shell housing the battery, compute, and driver electronics. Total printed mass approximately 1.2 kg. The full mechanical design files, including all printed parts, are available for replication and modification.<br>

**Actuation** — 20 custom quasi-direct drive (QDD) actuators, one per joint. Each actuator is built from three components: a brushless drone motor, a 3D-printed cycloidal reducer, and an FOC driver board with magnetic encoder. This architecture is based on the open-source actuators developed for the Berkeley Humanoid Lite, which are designed for affordability and ease of replication using common 3D printers and off-the-shelf electronics. The actuator design uses a low-reduction cycloidal gearing combined with an off-the-shelf brushless motor to achieve high torque density, backdrivability, and proprioceptive torque sensing without additional sensors. Each actuator weighs approximately 250–450 g depending on reduction ratio and joint application.<br>

**Locomotion** — Bipedal walking. Leg joints are configured for hip roll, hip pitch, hip yaw, knee pitch, ankle pitch, and ankle roll. The ankle roll joint enables balance control during single-leg stance. Walking gait generated by a trajectory optimizer or a trained reinforcement learning policy. Capable of standing, walking forward and backward, turning in place, squatting, and stepping.<br>

**Manipulation** — Optional arm manipulation. The 4-DOF arms support reaching and simple grasping. Expandable to 6-DOF or 7-DOF arms with additional wrist joints and dexterous hands. Arm actuators use the same QDD design as the legs but with lower reduction ratios suited to lighter loads.<br>

**Power system** — 6S LiPo 5000 mAh, XT60. 24V direct to all actuator driver boards. 5V 5A buck converter for Raspberry Pi 5. 5V 3A buck for sensors. All power wiring 14 AWG for main bus, 18 AWG for per-actuator power, 26 AWG for CAN or serial signal. Power distribution board routes battery to all drivers and buck converters.<br>

**Wiring** — CAN bus daisy-chain across all 20 actuator driver boards. Motor power distributed via power distribution board. CAN bus terminated with 120 ohm resistors at both ends. Signal wires shielded where possible to reduce noise from motor switching. All wiring routed through the hollow centers of the printed limb links, with service loops at each joint to accommodate full range of motion.<br>

**Custom parts** — 3D-printed torso shell (PA12-CF). 3D-printed hip housings (PA12-CF). 3D-printed thigh links (PA12-CF). 3D-printed shin links (PA12-CF). 3D-printed foot links (PA12-CF + TPU sole). 3D-printed upper arm links (PA12-CF). 3D-printed forearm links (PA12-CF). 3D-printed cycloidal reducers for each actuator (PA12-CF). 3D-printed actuator housings (PA12-CF). Aluminum reinforcement plates at hip and knee (6061-T6, CNC or waterjet).<br>

**Fasteners** — M3 and M4 stainless steel. M3 for actuator and bracket mounting. M4 for structural connections. M3 shoulder screws for joint pivots. Heat-set threaded inserts in all printed parts for repeated assembly and disassembly.<br>

**Tools required** — 3D printer (PA12-CF capable, or outsource to a print service). Hex drivers (2 mm, 2.5 mm, 3 mm). Soldering iron. Wire crimper. Multimeter. CAN bus analyzer (recommended). Torque wrench for structural fasteners.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| T-Motor F80 Pro brushless motor (or equivalent) | 20 | T-Motor / HobbyKing | ~$40 each | Actuators/BLDC |
| Custom FOC driver board (SimpleFOC or VESC-based) | 20 | Custom PCB / ODrive | ~$25 each | Actuators/driver |
| AS5047P magnetic encoder | 20 | AMS | ~$8 each | Sensors/Encoder |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| Intel RealSense D435i (optional) | 1 | Intel | ~$350 | Sensors/Camera |
| 6S LiPo 5000 mAh, 22.2V | 1 | Tattu / CNHL | ~$80 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 5V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT60 connector pair | 1 | Various | ~$3 | Power/connector |
| CAN transceiver | 1 | Various | ~$5 | Comms/CAN |
| 120 ohm termination resistors | 2 | Various | ~$1 | Comms/CAN |
| 14 AWG silicone wire | 1 m | Various | ~$5 | Wiring |
| 18 AWG silicone wire | 3 m | Various | ~$8 | Wiring |
| 26 AWG shielded wire | 5 m | Various | ~$10 | Wiring |
| M3, M4 stainless screws, heat-set inserts | assorted | McMaster | ~$40 | Fasteners |
| PA12-CF filament (or print service) | ~1.2 kg | Bambu / Shapeways | ~$120 | Custom parts |
| TPU filament for foot soles | ~100 g | Prusament | ~$8 | Custom parts |
| Aluminum 6061-T6 plates (hip, knee reinforcement) | 2 sets | SendCutSend | ~$50 | Structure |
| Custom PCB fabrication (driver boards) | 20 | JLCPCB / PCBWay | ~$100 | Actuators/driver |
| PS4 or Xbox wireless controller | 1 | Various | ~$50 | Operator interface |
| USB gamepad receiver or Bluetooth dongle | 1 | Various | ~$10 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Teensy 4.0 runs the real-time motor control loop at 1 kHz. It communicates with the 20 custom FOC driver boards over CAN bus. Each driver board runs SimpleFOC or VESC firmware with field-oriented control at 20–40 kHz for smooth torque production. The Teensy reads joint positions and velocities from the magnetic encoders on each actuator, runs a joint-space PD or impedance controller, and sends torque commands back. It reads the BNO085 IMU over I2C or SPI. It receives high-level commands from the Raspberry Pi 5 over micro-ROS serial. Raspberry Pi 5 runs Ubuntu 24.04 LTS and ROS 2 Jazzy.<br>

**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial at 921600 baud. Cyclone DDS on the LAN for remote visualization and teleoperation. The architecture follows the pattern established by the Berkeley Humanoid Lite and other open-source humanoid projects.<br>

**Perception** — BNO085 9-DOF IMU with onboard sensor fusion running CEVA's SH-2 firmware on an ARM Cortex-M0+. Provides fused orientation (rotation vector), linear acceleration, and angular velocity at up to 400 Hz. Optional Intel RealSense D435i depth camera for visual perception, terrain sensing, and manipulation tasks. Optional foot contact sensors for gait phase detection.<br>

**Control** — The Teensy runs a 1 kHz joint-space PD or impedance controller with gravity compensation. The high-level locomotion controller runs on the Raspberry Pi 5 at 200–500 Hz, generating joint trajectories for walking, standing, and stepping. Two control approaches are supported: a model-based trajectory optimizer (centroidal dynamics + whole-body control) and a learned policy (reinforcement learning trained in Isaac Lab or MuJoCo, transferred to hardware). Sim-to-real transfer requires accurate actuator modeling, system identification, and simulated latency, all of which the QDD actuators support through their torque transparency and encoder feedback.<br>

**Planning** — No autonomous navigation in the initial build. Optional: footstep planning for obstacle traversal. Optional: whole-body manipulation planning for reaching and grasping tasks.<br>

**Learning** — Designed for reinforcement learning and imitation learning. The platform supports training locomotion policies in simulation (Isaac Lab, MuJoCo) and deploying them to hardware. The QDD actuators with torque control and encoder feedback enable the proprioceptive sensing required for sim-to-real transfer. Berkeley Humanoid Lite, a reference platform for this design, provides open-source training pipelines and deployment tools, with dedicated LeRobot plugins for data collection and policy training.<br>

**Teleoperation** — Wireless gamepad (PS4 or Xbox) connected to the Raspberry Pi 5 via Bluetooth or USB. A ROS 2 node maps gamepad inputs to velocity commands and body pose adjustments. Optional VR teleoperation for whole-body control, as demonstrated by the Berkeley Humanoid Lite and other open-source humanoids.<br>

**Safety** — Software e-stop. Joint torque limits enforced in the Teensy control loop (max current per actuator). Watchdog: if no command received within 500 ms, the robot enters a damping mode and holds position. Fall detection via IMU: if body pitch or roll exceeds 60°, motors are disabled. The manufacturer explicitly warns that humanoid robots are structurally complex with powerful dynamics, and users should maintain adequate safety distance.<br>

**Logging** — rosbag2 with MCAP format. Joint states, IMU data, foot contacts, and commands recorded at 200 Hz. Optional camera at 30 Hz. Data format compatible with LeRobot for imitation learning pipelines.<br>

**Networking** — Wi-Fi 6 via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access.<br>

**Config files** — URDF (`emu.urdf.xacro`), joint limits and PID gains (`joint_params.yaml`), gait parameters (`gait_params.yaml`), micro-ROS agent config, gamepad mapping.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy, `micro_ros_arduino`, `bno08x_driver`, `joy`, `robot_state_publisher`, `rviz2`, `rosbag2`, `SimpleFOC` or `VESC` firmware for driver boards.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| micro-ROS | Jazzy-compatible | microros.org | Middleware/microROS |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| joy | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |
| SimpleFOC | Latest | simplefoc.com | Firmware/FOC |
| VESC | Latest | vesc-project.com | Firmware/FOC |
| Isaac Lab (optional) | Latest | NVIDIA | Simulation/RL |
| MuJoCo (optional) | Latest | Google DeepMind | Simulation |

---

## Interface

**Emits** — `/joint_states` (200 Hz, JointState for all 20 joints), `/imu/data` (200 Hz, Imu), `/foot_contacts` (100 Hz, custom message), `/odom` (100 Hz, Odometry from leg kinematics), `/robot_status` (1 Hz), `/tf`, optional `/camera/depth/points` (30 Hz).<br>

**Accepts** — `/cmd_vel` (20 Hz, Twist for body velocity), `/body_pose` (20 Hz, custom message for torso height and orientation), `/teleop_input` (20 Hz from gamepad).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (stand up), `/sit` (crouch), `/reset_odometry`.<br>

**Executes** — `/walk` (action, walk for distance), `/turn` (action, turn in place), `/step` (action, step over obstacle), `/stand` (action, hold standing pose), `/squat` (action, crouch to specified height).<br>

**Extensions** — `emu/gait_phase`, `emu/foot_positions`, `emu/motor_temps`, `emu/battery_state`, `emu/balance_margin`.<br>

**Frame conventions** — `base_link` at pelvis center. `base_footprint` at ground projection. Leg frames: `FL_hip_roll`, `FL_hip_pitch`, `FL_hip_yaw`, `FL_knee`, `FL_ankle_pitch`, `FL_ankle_roll`, `FL_foot` (front left), and equivalent for FR, RL, RR. Arm frames: `L_shoulder_pitch`, `L_shoulder_roll`, `L_elbow`, `L_wrist` (left arm), and equivalent for right.<br>

**Units** — SI. Meters, meters/second, radians, seconds, Newtons, Newton-meters.

---

## Model

**URDF / Xacro** — `model/emu.urdf.xacro`. Includes 20 revolute joints with position and velocity limits. Joint limits from mechanical design: hip roll ±45°, hip pitch ±120°, hip yaw ±90°, knee pitch 0 to −150°, ankle pitch ±45°, ankle roll ±30°, shoulder pitch ±120°, shoulder roll ±90°, elbow pitch 0 to −150°, wrist yaw ±90°.<br>

**SDF** — Used for Gazebo Harmonic simulation.<br>

**Calibration** — Joint zero offsets (each motor's encoder zero set to mechanical zero). IMU orientation and bias. Leg segment lengths measured from CAD. Body mass and inertia from CAD and verified by weighing. Foot contact sensor threshold calibration.<br>

**Dynamics** — Actuator constants from motor datasheet and cycloidal reducer ratio. Each actuator's torque constant and back-EMF constant identified through system identification. Leg link masses from printed parts. Body mass from electronics, battery, and chassis. Friction and damping identified through system identification experiments. The QDD actuator architecture enables accurate torque control without additional torque sensors, as the motor current maps directly to joint torque through the known torque constant and reduction ratio.<br>

**Sensor transforms** — IMU mounted at torso center, 50 mm above pelvis. Optional camera at head height (1200 mm), 100 mm forward, 10° down tilt. Foot contact sensors at each foot sole.<br>

**Collision geometry** — Simple boxes and cylinders for links in simulation. Foot collision spheres.<br>

**Visual geometry** — STL meshes from printed and machined parts.

---

## Trials

**Bench** — Motor direction, encoder counts, IMU readings, CAN bus communication with all 20 drivers. Pass/fail, measured values, date. Expected: all 20 actuators respond to torque commands, encoders report position with 14-bit resolution (AS5047P, 16384 counts per revolution), IMU reports orientation within 2° accuracy.<br>

**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 200 Hz. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>

**Field** — Stand and hold pose for 5 minutes. Walk forward 10 m without falling. Turn in place 180°. Step over 50 mm and 100 mm obstacles. Recover from 30 N lateral push. Squat to 50% height and stand. Pass/fail, measured values, date.<br>

**Endurance** — Continuous walking until battery cutoff at 3.3V per cell. Motor temperature at end (expected <80 °C with derating if exceeded).<br>

**Environmental** — Tested on flat indoor surfaces and low-pile carpet only.<br>

**Known limitations** — No outdoor capability. No autonomous navigation without additional sensors. Stairs require a trained policy not included in the base build. Arm manipulation is limited to reaching and simple grasping; dexterous manipulation requires additional hand hardware and a trained policy. Walking speed is limited by the joint torque and balance control authority. Bipedal locomotion is inherently less stable than quadrupedal or wheeled platforms.

---

## Log

**Build history** — Dated entries, what changed, why.<br>

**Open issues** — Links, priority, status.<br>

**Changelog** — Version bumps, what triggered each.<br>

**Lessons learned** — What would be done differently.<br>

**Cost actual** — Final spend vs. BOM estimate.

---

## Status

**Condition** — draft.<br>

**Blockers** — None. Ready to order parts.<br>

**Next steps** — Finalise BOM, order components, print parts, assemble actuators, begin assembly. Milestone 1: bench test all 20 actuators on the CAN bus. Milestone 2: stand and hold pose with balance controller. Milestone 3: walk forward with a trajectory-based controller. Milestone 4: train and deploy a reinforcement learning locomotion policy. Milestone 5: optional arms and manipulation. Milestone 6: optional camera and autonomy.
