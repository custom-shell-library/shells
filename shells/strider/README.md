# strider

**Class:** hybrid (wheeled-legged)<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Hybrid wheeled-legged quadruped that drives on wheels for efficient flat-ground locomotion and uses its legs to step over obstacles, climb stairs, and traverse rough terrain. Combines the speed and efficiency of a wheeled platform with the agility of a legged one. The front legs use hip-yaw degrees of freedom instead of hip-roll, enabling efficient steering on flat ground while retaining terrain adaptability. This configuration allows seamless transitions between wheeled and legged locomotion modes.<br>

**Environment** — Indoor hard floors, low-pile carpet, stairs, ramps, gravel, and packed dirt. Calm outdoor conditions. Not for deep water, extreme heat, or loose sand. Operating temperature 0–45 °C.<br>

**Mission** — Provide a reproducible platform for hybrid locomotion research. Drive on flat ground at speed, step over obstacles up to 200 mm, climb stairs up to 25°, and transition between modes without stopping. Serves as a testbed for reinforcement learning controllers that adapt locomotion mode to terrain.<br>

**Operator** — Single operator via wireless gamepad or ROS 2 teleop. Higher-level commands (velocity, locomotion mode, body height) sent as twists or custom messages. Supervised autonomy possible with a trained policy. The RW-02OP platform provides a full open-source stack including ROS packages, MJCF model files, simulation frameworks, LQR controller code, and teleoperation tools.<br>

**Reusability** — Fully open-source design. Structural components 3D-printable or CNC-machinable. Actuators off-the-shelf. Two configuration options: a research-scale build based on FLORES and Maera, and a heavy-load build based on RW-02OP.

---

## Spec

**Physical** — Two configurations:

- **Research build (FLORES/Maera class):** 8–12 kg total mass. 400 × 300 × 350 mm standing footprint. Standing height 350–450 mm. 3D-printed PETG or PA12-CF body and legs with aluminum reinforcement. Ground clearance adjustable 80–250 mm.

- **Heavy-load build (RW-02OP class):** 21 kg total mass. 1,100 mm standing height. 10 kg payload capacity (nearly 0.5 payload-to-weight ratio). Full-size structural design with open-source 3D models, hardware system diagrams, and detailed BOM. Aluminum and carbon fiber structure.

**Kinematic** — 8 degrees of freedom. Four legs, two joints per leg. Front legs: hip-yaw and knee-pitch. Rear legs: hip-roll and knee-pitch. The front leg hip-yaw configuration replaces the conventional hip-roll DOF, enabling efficient steering on flat surfaces by yawing the front wheels while the rear legs provide propulsion. Wheel diameter 100–150 mm depending on configuration. Leg segment lengths: upper leg 200 mm, lower leg 200 mm (research build) or 300 mm / 300 mm (heavy-load build).<br>

**Dynamic** — Peak knee joint torque 40 N·m (research build), 120 N·m (heavy-load build). Max wheel speed 3 m/s (research), 2 m/s (heavy-load). Max walking speed 0.8 m/s. Obstacle height 200 mm (research), 250 mm (heavy-load). Stair climbing up to 25° incline. Payload capacity 3 kg (research), 10 kg (heavy-load).<br>

**Power** — Research build: 6S LiPo (22.2V nominal, 5000 mAh, 111 Wh). Heavy-load build: 8S LiPo or Li-ion (29.6V nominal, 10,000 mAh, 296 Wh). Runtime 1–2 hours (research), 2–4 hours (heavy-load) depending on locomotion mode. XT60 or XT90 connector. 24V or 30V direct to motor drivers. 5V 5A buck for compute. 12V 3A buck for sensors.<br>

**Thermal** — 0–45 °C operating. Passive cooling. Motors have aluminum heat sinks. Drivers report temperature and current monitoring for derating.<br>

**Environmental** — Indoor and calm outdoor. Not IP-rated. Not for rain or submergence.

---

## Frame

**Bill of materials** — See detailed BOM below. Two configurations:

- **Research build:** ≈ $1,800–$2,500
- **Heavy-load build:** ≈ $6,000–$9,000

**Structure** — Research build: 3D-printed PETG or PA12-CF body and leg links with 6061-T6 aluminum reinforcement plates at knee and hip pivots. Heavy-load build: aluminum 6061-T6 and carbon fiber structural members with 3D-printed PA12-CF brackets. The RW-02OP platform provides full open-source 3D structural models, hardware system diagrams, and detailed BOM for the heavy-load configuration.<br>

**Actuation** — Research build: 8× brushless motors with planetary or cycloidal reducers. Selected motor: T-Motor MN4006 380KV or equivalent for knee joints, paired with 3D-printed cycloidal reducers. Wheel motors: T-Motor MN3508 380KV or equivalent with direct drive. Heavy-load build: 8× high-torque brushless motors with harmonic or cycloidal reducers. Peak knee torque 120 N·m. The RW-02OP platform uses a wheel-legged composite design with LQR-based controllers and full ROS package support.<br>

**Locomotion** — Hybrid wheeled-legged quadruped. Three locomotion modes: (1) **Wheeled mode** — all four wheels in contact, driving like a car with front-wheel steering via hip-yaw joints. (2) **Legged mode** — wheels lifted, walking with a trot or walk gait. (3) **Hybrid mode** — some wheels in contact while legs adjust body height and orientation. The RL controller adapts the Hybrid Internal Model (HIM) with a customized reward structure to generate adaptive, multi-modal locomotion strategies with smooth transitions between wheeled and legged movements. Novel efficient gaits emerge from the synergistic advantages of both modes.<br>

**Manipulation** — None. Payload is sensor or small equipment only. Optional arm mount on the front for manipulation research.<br>

**Power system** — Research: 6S LiPo 5000 mAh. Heavy-load: 8S LiPo or Li-ion 10,000 mAh. 24V/30V direct to motor drivers. 5V 5A buck for compute. 12V 3A buck for sensors. Power distribution board with XT60/XT90 input and multiple XT60 outputs for motor drivers.<br>

**Wiring** — CAN bus daisy-chain across all motor drivers. Motor power distributed via power distribution board. CAN bus terminated with 120 ohm resistors at both ends. Signal wires shielded. Wiring routed through hollow leg links with service loops at joints.<br>

**Custom parts** — 3D-printed body and leg links (PETG or PA12-CF). 3D-printed cycloidal reducers. 3D-printed motor mounts. Aluminum reinforcement plates (6061-T6). 3D-printed wheel hubs. TPU wheel treads for grip.<br>

**Fasteners** — M3, M4, and M5 stainless steel. M3 for electronics and brackets. M4 for leg links. M5 for structural connections. Heat-set threaded inserts in printed parts.<br>

**Tools required** — 3D printer (PETG/PA12-CF capable), hex drivers (2 mm, 2.5 mm, 3 mm, 4 mm), soldering iron, wire crimper, multimeter, CAN bus analyzer (recommended), torque wrench.

### Bill of Materials (Research Build)

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| T-Motor MN4006 380KV (knee motors) | 4 | T-Motor | ~$60 each | Actuators/BLDC |
| T-Motor MN3508 380KV (wheel motors) | 4 | T-Motor | ~$45 each | Actuators/BLDC |
| FOC driver board (ODrive or SimpleFOC) | 8 | ODrive / custom | ~$40 each | Actuators/driver |
| AS5047P magnetic encoder | 8 | AMS | ~$8 each | Sensors/Encoder |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| 6S LiPo 5000 mAh, 22.2V | 1 | Tattu / CNHL | ~$80 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 12V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT60 connector pairs | 4 | Various | ~$5 each | Power/connector |
| CAN transceiver | 1 | Various | ~$5 | Comms/CAN |
| 120 ohm termination resistors | 2 | Various | ~$1 | Comms/CAN |
| 12 AWG, 16 AWG, 26 AWG silicone wire | assorted | Various | ~$25 | Wiring |
| M3, M4, M5 stainless screws, heat-set inserts | assorted | McMaster | ~$40 | Fasteners |
| PETG or PA12-CF filament | ~1.5 kg | Prusament / Bambu | ~$60 | Custom parts |
| TPU filament for wheel treads | ~200 g | Prusament | ~$12 | Custom parts |
| Aluminum 6061-T6 plates (reinforcement) | 2 sets | SendCutSend | ~$50 | Structure |
| Custom PCB fabrication (driver boards) | 8 | JLCPCB / PCBWay | ~$60 | Actuators/driver |
| PS4 or Xbox wireless controller | 1 | Various | ~$50 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Teensy 4.0 runs the real-time motor control loop at 1 kHz. Communicates with 8 FOC driver boards over CAN bus. Each driver runs SimpleFOC or ODrive firmware with field-oriented control at 20–40 kHz. Teensy reads joint positions from magnetic encoders, runs joint-space PD or impedance controller, sends torque commands. Reads BNO085 IMU over I2C or SPI. Receives high-level commands from Raspberry Pi 5 over micro-ROS serial. Raspberry Pi 5 runs Ubuntu 24.04 LTS and ROS 2 Jazzy.<br>

**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial at 921600 baud. Cyclone DDS on LAN for remote visualization and teleoperation. The RW-02OP platform provides full ROS package support including robot MJCF model files, simulation and sim2sim framework code, LQR controller code, controller parameter auto-generation code, and debugging tools (data collection/analysis, online status viewing, teleoperation).<br>

**Perception** — BNO085 9-DOF IMU. Optional Intel RealSense D435i depth camera for terrain sensing and autonomy. Optional wheel encoders for odometry (in addition to motor encoders).<br>

**Control** — Teensy runs 1 kHz joint-space PD or impedance controller. High-level locomotion controller runs on Raspberry Pi 5 at 200–500 Hz. Two control approaches supported: (1) LQR-based controller as provided by the RW-02OP platform, with controller parameter auto-generation. (2) Reinforcement learning controller using the Hybrid Internal Model (HIM) adapted from FLORES, with a customized reward structure optimized for the hip-yaw front leg configuration. The RL controller generates adaptive multi-modal locomotion strategies with smooth transitions between wheeled and legged modes. Novel efficient gaits emerge from synergistic advantages of both modes.<br>

**Planning** — No autonomous navigation in initial build. Optional: footstep planning for obstacle traversal. Optional: Nav2 integration with depth camera for waypoint navigation.<br>

**Learning** — Designed for reinforcement learning and imitation learning. Platform supports training locomotion policies in simulation (Isaac Lab, MuJoCo, mjlab) and deploying to hardware. FLORES demonstrates successful RL policy transfer with the HIM framework. RW-02OP provides sim2sim framework code for policy validation before hardware deployment. QDD actuators with torque transparency and encoder feedback enable proprioceptive sensing required for sim-to-real transfer.<br>

**Teleoperation** — Wireless gamepad (PS4 or Xbox) connected to Raspberry Pi 5 via Bluetooth or USB. ROS 2 node maps gamepad inputs to velocity commands and locomotion mode selection. Optional VR teleoperation for whole-body control. RW-02OP provides teleoperation tools as part of open-source package.<br>

**Safety** — Software e-stop. Joint torque limits enforced in Teensy control loop. Watchdog: if no command received within 500 ms, robot enters damping mode and holds position. Fall detection via IMU: if body pitch or roll exceeds 60°, motors disabled. Thermal monitoring: motor current monitored and derated if overheating.<br>

**Logging** — rosbag2 with MCAP format. Joint states, IMU data, wheel odometry, and commands recorded at 200 Hz. Optional camera at 30 Hz. Data format compatible with LeRobot for future policy training. RW-02OP provides data collection and analysis tools.<br>

**Networking** — Wi-Fi 6 via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access.<br>

**Config files** — URDF (`strider.urdf.xacro`), MJCF model (`strider.xml`), joint limits and PID gains (`joint_params.yaml`), gait parameters (`gait_params.yaml`), RL policy config, gamepad mapping.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`, `sim.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy, `micro_ros_arduino`, `bno08x_driver`, `joy`, `robot_state_publisher`, `rviz2`, `rosbag2`, `SimpleFOC` or `ODrive` firmware, `mjlab` or `Isaac Lab` for simulation.

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
| ODrive | Latest | odriverobotics.com | Firmware/FOC |
| mjlab (optional) | Latest | github | Simulation/RL |
| Isaac Lab (optional) | Latest | NVIDIA | Simulation/RL |

---

## Interface

**Emits** — `/joint_states` (200 Hz, JointState), `/imu/data` (200 Hz, Imu), `/wheel_odom` (100 Hz, Odometry), `/robot_status` (1 Hz), `/tf`, optional `/camera/depth/points` (30 Hz).<br>

**Accepts** — `/cmd_vel` (20 Hz, Twist for body velocity), `/locomotion_mode` (custom, for mode selection), `/body_pose` (20 Hz, custom message for torso height and orientation), `/teleop_input` (20 Hz from gamepad).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (stand up), `/sit` (crouch), `/reset_odometry`.<br>

**Executes** — `/drive` (action, wheeled locomotion), `/walk` (action, legged locomotion), `/step` (action, step over obstacle), `/climb` (action, climb stairs), `/stand` (action, hold standing pose).<br>

**Extensions** — `strider/locomotion_mode`, `strider/wheel_contacts`, `strider/motor_temps`, `strider/battery_state`, `strider/balance_margin`.<br>

**Frame conventions** — `base_link` at body center. `base_footprint` at ground projection. Leg frames: `FL_hip_yaw`, `FL_knee`, `FL_wheel` (front left), and equivalent for FR, RL, RR. Wheel frames for odometry.<br>

**Units** — SI. Meters, meters/second, radians, seconds, Newtons, Newton-meters.

---

## Model

**URDF / Xacro** — `model/strider.urdf.xacro`. Includes 8 revolute joints (4 hip, 4 knee) plus 4 continuous wheel joints. Joint limits: front hip-yaw ±60°, rear hip-roll ±45°, knee pitch 0 to −150°. Links: body, 4× upper leg, 4× lower leg, 4× wheel.<br>

**MJCF** — `model/strider.xml`. Used for MuJoCo simulation and RL training. RW-02OP provides MJCF model files as part of open-source package.<br>

**SDF** — Used for Gazebo Harmonic simulation.<br>

**Calibration** — Joint zero offsets (each motor encoder zero set to mechanical zero). IMU orientation and bias. Wheel radius and track width. Leg segment lengths measured from CAD. Body mass and inertia from CAD and verified by weighing. Wheel contact point calibration.<br>

**Dynamics** — Motor constants from datasheet. Reducer ratios from cycloidal design. Leg link masses from printed parts. Body mass from electronics, battery, and chassis. Friction and damping identified through system identification. Wheel-ground interaction model for wheeled locomotion. The QDD actuator architecture enables accurate torque control without additional torque sensors.<br>

**Sensor transforms** — IMU at body center, 30 mm above base plate. Optional camera at front, 50 mm forward, 100 mm height, 10° down tilt. Wheel contact points at bottom of each wheel.<br>

**Collision geometry** — Simple boxes and cylinders for links in simulation. Wheel collision cylinders. Foot collision spheres for legged mode.<br>

**Visual geometry** — STL meshes from printed and machined parts.

---

## Trials

**Bench** — Motor direction, encoder counts, IMU readings, CAN bus communication with all 8 drivers. Pass/fail, measured values, date. Expected: all 8 motors respond to torque commands, encoders report position with 14-bit resolution, IMU reports orientation within 2° accuracy.<br>

**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 200 Hz. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>

**Field** — Stand and hold pose for 5 minutes. Wheeled mode: drive forward 10 m at 2 m/s, turn in place. Legged mode: walk forward 5 m, turn in place. Hybrid mode: drive on flat ground, step over 150 mm obstacle, transition to legged mode, continue walking. Stair climb test: 20° incline. Terrain traversal test: gravel, packed dirt, grass. Pass/fail, measured values, date.<br>

**Endurance** — Continuous wheeled locomotion until battery cutoff at 3.3V per cell. Continuous legged locomotion until battery cutoff. Motor temperature at end (expected <80 °C with derating if exceeded).<br>

**Environmental** — Tested on flat indoor surfaces, gravel, packed dirt, and grass. Limited outdoor testing. Not for rain or submergence.<br>

**Known limitations** — Wheeled-legged hybrids are mechanically more complex than pure wheeled or pure legged platforms, increasing failure points. The front hip-yaw configuration is optimized for steering but may have less lateral stability than hip-roll designs on steep side slopes. Wheel slip in legged mode can affect odometry accuracy. Transitions between modes require careful control to avoid instability. Payload capacity is lower than a pure wheeled platform of equivalent mass.

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

**Next steps** — Finalise BOM, order components, print parts, assemble. Milestone 1: bench test all 8 motors and CAN communication. Milestone 2: stand and hold pose with wheeled mode controller. Milestone 3: wheeled locomotion (drive, steer, turn in place). Milestone 4: legged locomotion (walk, trot). Milestone 5: hybrid mode transitions (wheeled ↔ legged). Milestone 6: obstacle traversal and stair climbing. Milestone 7: RL policy training and sim-to-real deployment. Milestone 8: optional depth camera and autonomy.
