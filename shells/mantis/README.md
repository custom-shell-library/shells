# mantis

**Class:** legged<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-10-06

---

## Identity

**Role** — Eighteen-degree-of-freedom hexapod for bio-inspired locomotion research, static-stability testing, and multi-agent swarm experiments. Walks with tripod, ripple, and wave gaits. Traverses uneven terrain up to 18 mm height variation. Carries a depth camera and IMU for terrain sensing. The hexapod's inherent static stability — always maintaining at least three ground contacts — makes it the most robust legged platform class for research where a fall is unacceptable.<br>

**Environment** — Indoor hard floors, low-pile carpet, and structured uneven terrain. Calm outdoor conditions on grass and packed dirt. Not for steep slopes, stairs, or wet surfaces. Operating temperature 5–40 °C.<br>

**Mission** — Provide a compact, reproducible platform for hexapod locomotion research. Stable tripod, ripple, and wave gaits with smooth online transitions. Omnidirectional walking and turning. Terrain adaptation via onboard depth sensing and foot contact switches. Serves as a testbed for central pattern generator (CPG) control, reinforcement learning, and multi-agent coordination.<br>

**Operator** — Single operator via wireless gamepad or ROS 2 teleop. Higher-level commands (velocity, gait type, body height) sent as twists or custom messages. Supervised autonomy possible with a trained locomotion policy.<br>

**Reusability** — Fully open-source design. All structural components 3D-printable. All actuators off-the-shelf hobby servos or Dynamixel servos. Repeatable build.

---

## Spec

**Physical** — 3.5 kg total mass with battery and electronics. Body diameter 280 mm. Standing height 180 mm. Ground clearance adjustable 60–220 mm via leg joints. 3D-printed PLA or PETG body and leg links with carbon fiber reinforcement at high-load joints. Center of mass low and centered over the tripod support polygon.<br>

**Kinematic** — 18 degrees of freedom. Six legs, each with 3 joints: coxa (yaw, forward/backward leg movement), femur (pitch, elevation/depression), tibia (pitch, extension/flexion). The yaw-pitch-pitch configuration is standard for hexapods and enables omnidirectional walking. Leg segment lengths: coxa 40 mm, femur 100 mm, tibia 120 mm. Leg span approximately 400 mm. Analytic inverse kinematics solver for the yaw-pitch-pitch configuration enforces workspace feasibility and handles kinematic singularities in real time.<br>

**Dynamic** — Peak coxa joint torque 3.0 N·m. Peak femur joint torque 4.0 N·m. Peak tibia joint torque 3.0 N·m. Walking speed 0.4 m/s nominal, 0.8 m/s maximum. Payload capacity 1.5 kg. Capable of traversing uneven terrain with height variations up to 18 mm, with mean body-pitch deviation below 5°.<br>

**Power** — 2S LiPo (7.4V nominal, 5000 mAh, 37 Wh). Runtime 60–90 minutes depending on gait and payload. XT60 connector. 7.4V direct to servos. 5V 5A buck converter for Raspberry Pi 5. 3.3V for IMU.<br>

**Thermal** — 5–40 °C operating. Passive cooling. Servos have metal cases for heat dissipation. Current monitoring in firmware for derating if overheating occurs.<br>

**Environmental** — Indoor and calm outdoor. Not IP-rated. Not for rain, dust, or wet surfaces.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $650–$1,200 depending on servo selection.<br>

**Structure** — 3D-printed PLA or PETG body and leg links. The body is a single printed chassis with mounting points for the six coxa servos and the electronics. Leg links are printed with integrated bearing seats. Carbon fiber plates are used at the coxa mounting points where cyclic loading is highest. Total printed mass approximately 350 g. The design follows the SPINDER open-source hexapod architecture, which uses 3D-printed PLA parts and Dynamixel XC330-M288-T servos for a compact 18-DoF platform weighing 0.8 kg. A lower-cost variant using MG996R servos is also specified.<br>

**Actuation** — Two actuator options:
- **Option A (research-grade):** 18× Dynamixel XC330-M288-T servos. The XC330 is a compact smart servo with an ARM Cortex-M0+ MCU, 5V input, 2.8 N·m stall torque, 4096 steps/revolution resolution, 16 g weight, and 20 × 36 × 26 mm dimensions. It supports position, velocity, and current control modes, and communicates over TTL at up to 3 Mbps. It provides joint angle and torque feedback.
- **Option B (budget):** 18× MG996R servos. 2.5 N·m stall torque at 6V, 55 g weight, metal gears, standard PWM input. Lower precision and no feedback, but significantly cheaper. The MG996R is sufficient for basic tripod and wave gaits on flat terrain.

**Locomotion** — Hexapod. Tripod, ripple, and wave gaits. In tripod gait, the legs alternate between two groups of three (front-left, middle-right, rear-left and front-right, middle-left, rear-right), providing maximum speed and static stability. Ripple gait moves one leg at a time, providing maximum stability at lower speed. Wave gait moves legs in a sequential wave from rear to front, providing the most stable and energy-efficient locomotion. Transitions between gaits are handled by a hierarchical central pattern generator (CPG) that smoothly reorganizes inter-leg phase relationships, settling within approximately two gait cycles.<br>

**Manipulation** — None. Payload is sensor only.<br>

**Power system** — 2S LiPo 5000 mAh, XT60. 7.4V direct to servos. 5V 5A buck converter for Raspberry Pi 5. All servo power wiring 18 AWG. Signal wiring 26 AWG. Power distribution board routes battery to servos and buck converters.<br>

**Wiring** — Daisy-chained Dynamixel bus (Option A) or parallel PWM signal wires (Option B). Each servo connects to the next via a 3-pin or 4-pin cable for Dynamixel, or a 3-pin PWM cable for MG996R. Wiring runs through the hollow centers of the printed leg links with service loops at each joint. Head segment contains the camera and IMU.<br>

**Custom parts** — 3D-printed body chassis (PLA or PETG). 3D-printed coxa links (PLA or PETG). 3D-printed femur links (PLA or PETG). 3D-printed tibia links (PLA or PETG). 3D-printed foot pads (TPU for grip). 3D-printed camera mount (PETG). Carbon fiber reinforcement plates at coxa mounts (1.5 mm, CNC or waterjet).<br>

**Fasteners** — M2 and M3 stainless steel. M2 for servo mounting. M3 for structural connections. M3 shoulder screws for joint pivots. Heat-set threaded inserts in all printed parts for repeated assembly.<br>

**Tools required** — 3D printer (PLA/PETG capable), hex drivers (1.5 mm, 2 mm), soldering iron, wire crimper, multimeter, Dynamixel configuration tool (U2D2 or OpenCM9.04) for Option A.

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| Dynamixel XC330-M288-T servo (Option A) | 18 | ROBOTIS | ~$50 each | Actuators/Servo |
| MG996R servo (Option B) | 18 | Aliexpress / Amazon | ~$4 each | Actuators/Servo |
| Dynamixel U2D2 interface (Option A) | 1 | ROBOTIS | ~$30 | Compute/interface |
| Servo2040 (Option B) | 1 | Pimoroni | ~$28 | Compute/interface |
| Raspberry Pi 5, 4 GB | 1 | Raspberry Pi | ~$60 | Compute/SBC |
| Raspberry Pi Camera Module 3 (or ToF depth camera) | 1 | Raspberry Pi / Various | ~$25 | Sensors/Camera |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| 2S LiPo 5000 mAh | 1 | Tattu | ~$35 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| XT60 connector pair | 1 | Various | ~$3 | Power/connector |
| 18 AWG silicone wire | 2 m | Various | ~$5 | Wiring |
| 26 AWG silicone wire | 5 m | Various | ~$5 | Wiring |
| M2, M3 stainless screws, heat-set inserts | assorted | McMaster | ~$25 | Fasteners |
| PLA or PETG filament | ~750 g | Prusament | ~$25 | Custom parts |
| TPU filament for foot pads | ~100 g | Prusament | ~$10 | Custom parts |
| Carbon fiber plates, 1.5 mm | 2 | SendCutSend | ~$20 | Structure |
| PS4 or Xbox wireless controller | 1 | Various | ~$50 | Operator interface |
| USB gamepad receiver or Bluetooth dongle | 1 | Various | ~$10 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — For Option A (Dynamixel), the U2D2 or OpenCM9.04 runs the servo bus at 1 Mbps or 3 Mbps. The OpenCM9.04 is based on the STM32F103CB (ARM Cortex-M3, 72 MHz, 128 kB Flash, 20 kB SRAM) and has 4 Dynamixel ports onboard. For Option B (MG996R), the Servo2040 generates 18 PWM channels at 50 Hz. The Raspberry Pi 5 runs Ubuntu 24.04 LTS and ROS 2 Jazzy.<br>

**Middleware** — ROS 2 Jazzy. For Option A, the Raspberry Pi communicates with the Dynamixel bus via USB to the U2D2. For Option B, the Raspberry Pi communicates with the Servo2040 over USB serial. Cyclone DDS on the LAN for remote visualization and teleoperation.<br>

**Perception** — BNO085 9-DOF IMU for body orientation. Raspberry Pi Camera Module 3 or a time-of-flight (ToF) depth camera for terrain sensing. Per-foot contact switches for ground contact detection. The SPINDER platform integrates a ToF depth camera, six-axis IMU, and per-foot contact switches for terrain adaptation.<br>

**Control** — The Raspberry Pi runs the hierarchical locomotion controller at 100–200 Hz. The controller combines a coupled-oscillator central pattern generator (CPG) for inter-leg coordination with local motion controllers that regulate torso motion and generate cycloid-based swing trajectories with stance compensation. Foot targets are mapped to joint commands via analytic inverse kinematics. The CPG produces stable rhythmic patterns for tripod, ripple, and wave gaits. Gait transitions are handled by smoothly reorganizing inter-leg phase relationships, settling within approximately two gait cycles. For Option A, the Dynamixel servos run a position control loop at 1 kHz internally. For Option B, the Servo2040 generates PWM signals and the Raspberry Pi runs a PID position controller.<br>

**Planning** — No autonomous navigation in the initial build. Optional: terrain-adaptive gait selection using depth camera data and foot contact feedback. Optional: waypoint navigation on flat terrain.<br>

**Learning** — Designed for reinforcement learning and imitation learning. The platform supports training locomotion policies in simulation (Isaac Lab, MuJoCo, mjlab) and deploying them to hardware. The Spiderbot platform demonstrates successful sim-to-real transfer with an RL policy trained in mjlab, despite the complexity of its mechanism. For Option A, the Dynamixel servos provide joint torque feedback, which is valuable for sim-to-real transfer.<br>

**Teleoperation** — Wireless gamepad (PS4 or Xbox) connected to the Raspberry Pi 5 via Bluetooth or USB. A ROS 2 node maps gamepad inputs to gait parameters (forward/backward speed, lateral speed, turning rate, body height). Video feed from the depth camera streamed to the operator via Wi-Fi.<br>

**Safety** — Software e-stop. Joint torque limits enforced in firmware. Watchdog: if no command received within 500 ms, the robot enters a damping mode and holds position. Fall detection via IMU: if body pitch or roll exceeds 60°, motors are disabled.<br>

**Logging** — rosbag2 with MCAP format. Joint states, IMU data, foot contacts, and commands recorded at 100 Hz. Depth camera at 30 Hz. Data format compatible with LeRobot for future policy training.<br>

**Networking** — Wi-Fi via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access.<br>

**Config files** — URDF (`mantis.urdf.xacro`), gait parameters (`gait_params.yaml`), servo limits and gains (`servo_params.yaml`), micro-ROS agent config, gamepad mapping.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`.<br>

**Dependencies** — ROS 2 Jazzy, `dynamixel_sdk` (Option A), `bno08x_driver`, `joy`, `robot_state_publisher`, `rviz2`, `rosbag2`, `usb_cam` or `camera_ros`.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| ROS 2 | Jazzy | ros.org | Middleware/ROS2 |
| Ubuntu | 24.04 LTS | ubuntu.com | OS/Linux |
| dynamixel_sdk (Option A) | Latest | ROBOTIS | SDK/servo |
| bno08x_driver | Latest | index.ros.org | Perception/drivers |
| joy | Latest | ROS 2 | Teleoperation/input |
| rosbag2 | Latest | ROS 2 | Logging/rosbag |
| robot_state_publisher | Latest | ROS 2 | Model/URDF |
| rviz2 | Latest | ROS 2 | Visualization |
| Foxglove Studio | Latest | foxglove.dev | Visualization |
| usb_cam or camera_ros | Latest | github | Perception/camera |
| mjlab (optional) | Latest | github | Simulation/RL |

---

## Interface

**Emits** — `/joint_states` (100 Hz, JointState for all 18 joints), `/imu/data` (100 Hz, Imu), `/foot_contacts` (100 Hz, custom message), `/odom` (50 Hz, Odometry from leg kinematics), `/robot_status` (1 Hz), `/tf`, optional `/camera/depth/points` (30 Hz).<br>

**Accepts** — `/cmd_vel` (20 Hz, Twist for body velocity), `/gait_command` (custom, for gait selection), `/body_pose` (20 Hz, custom message for torso height and orientation), `/teleop_input` (20 Hz from gamepad).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (stand up), `/sit` (lower body), `/reset_odometry`.<br>

**Executes** — `/walk` (action, walk for distance), `/turn` (action, turn in place), `/stand` (action, hold standing pose), `/squat` (action, crouch to specified height).<br>

**Extensions** — `mantis/gait_phase`, `mantis/foot_positions`, `mantis/servo_temps`, `mantis/battery_state`, `mantis/balance_margin`.<br>

**Frame conventions** — `base_link` at body center. `base_footprint` at ground projection. Leg frames: `L1_coxa`, `L1_femur`, `L1_tibia`, `L1_foot` (left leg 1), and equivalent for L2, L3, R1, R2, R3.<br>

**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — `model/mantis.urdf.xacro`. Includes 18 revolute joints with position and velocity limits. Joint limits from mechanical design: coxa ±45°, femur ±90°, tibia 0 to −120°. Links: body, 6× coxa, 6× femur, 6× tibia, 6× foot.<br>

**SDF** — Used for Gazebo Harmonic simulation.<br>

**Calibration** — Joint zero offsets (each servo's zero set to mechanical straight position). IMU orientation and bias. Leg segment lengths measured from CAD. Body mass and inertia from CAD and verified by weighing. Foot contact switch threshold calibration.<br>

**Dynamics** — Servo constants from datasheet. For Option A (Dynamixel XC330), 2.8 N·m stall torque, 4096 steps/rev, 5V input. For Option B (MG996R), 2.5 N·m stall torque, 6V input. Leg link masses from printed parts. Body mass from electronics, battery, and chassis. Friction and damping identified through system identification experiments. The Spiderbot platform demonstrates that a 2-DOF leg design with passive spring compensation can reduce standing power consumption by over 90%, but the 3-DOF configuration specified here prioritizes dexterity and omnidirectional capability.<br>

**Sensor transforms** — IMU mounted at body center, 20 mm above base plate. Camera at front of body, 50 mm forward, 80 mm height, 10° down tilt. Foot contact switches at each foot sole.<br>

**Collision geometry** — Cylinders approximating each leg segment in simulation. Foot collision spheres.<br>

**Visual geometry** — STL meshes from printed parts.

---

## Trials

**Bench** — Servo direction, encoder counts (Option A), IMU readings, foot contact switches, camera feed. Pass/fail, measured values, date. Expected: all 18 servos respond to position commands, encoders report position with 4096 steps/rev (Option A), IMU reports orientation within 2° accuracy, foot switches trigger on ground contact.<br>

**Integration** — Dynamixel bus communication at 1 Mbps (Option A) or PWM generation at 50 Hz (Option B). ROS 2 bring-up with Cyclone DDS. Joint state publishing at 100 Hz. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>

**Field** — Stand and hold pose for 5 minutes. Tripod gait on tile, wood, and carpet. Ripple gait at low speed. Wave gait for maximum stability. Omnidirectional walking and turning. Terrain traversal with height variations up to 18 mm. Body-pitch deviation measurement during terrain traversal (target <5°). Pass/fail, measured values, date.<br>

**Endurance** — Continuous tripod gait until battery cutoff at 3.3V per cell. Servo temperature at end (expected <60 °C).<br>

**Environmental** — Tested on flat indoor surfaces and structured uneven terrain. Limited outdoor testing on grass.<br>

**Known limitations** — No autonomous navigation without additional sensors. Servo cables are a common failure point in long hexapod legs; strain relief is critical. The 3D-printed links are not as durable as machined aluminum for industrial use. Gait efficiency varies with surface friction; a gait that works on carpet may fail on smooth tile. The 3-DOF leg configuration consumes significantly more standing power than a 2-DOF leg with passive gravity compensation, but provides greater dexterity and omnidirectional capability.

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

**Next steps** — Finalise BOM, order components, print body and legs, assemble. Milestone 1: bench test all 18 servos. Milestone 2: stand and hold pose with tripod gait controller. Milestone 3: tripod, ripple, and wave gaits with smooth transitions. Milestone 4: terrain traversal with foot contact feedback. Milestone 5: optional depth camera and terrain-adaptive gait selection. Milestone 6: optional RL policy training and sim-to-real deployment.
