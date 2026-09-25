# Quadruped

**Class:** legged<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-09-25

---

## Identity

**Role** — Small 12-DOF torque-controlled quadruped for research, education, and benchmarking of legged locomotion algorithms. Walks, trots, bounds, and jumps. Capable of dynamic locomotion over flat and mildly uneven terrain.<br>
**Environment** — Indoor hard floors and low-pile carpet. Calm outdoor conditions on grass, gravel, and packed dirt. Not for stairs, steep slopes, or extreme terrain. Operating temperature 0–55 °C (motor limit).<br>
**Mission** — Provide a low-cost, reproducible platform for testing locomotion controllers. Baseline trot and walk gaits. Optional payload for sensors, cameras, or small grippers. Supported by ROS 2 and micro-ROS.<br>
**Operator** — Single operator via wireless gamepad or ROS 2 teleop. Higher-level commands (velocity, gait type, body height) sent as twists or custom messages. Supervised autonomy possible with locomotion policy.<br>
**Reusability** — Fully open-source design. All components either off-the-shelf or 3D-printable. Repeatable build.

---

## Spec

**Physical** — 2.1 kg total mass. 300 × 175 × 240 mm standing footprint (WxHxD). 3D-printed carbon-fiber-reinforced nylon body and legs. Ground clearance adjustable 80–180 mm via joint angles. Center of mass is centered over the hip plane.<br>
**Kinematic** — 12 DOF. Four legs, each with 3 joints: hip abduction/adduction (roll), hip flexion/extension (pitch), and knee flexion/extension (pitch). Leg segment lengths: upper leg 120 mm, lower leg 120 mm. Standing leg span approximately 280 mm.<br>
**Dynamic** — Peak actuator torque 1.8 Nm per joint (M2006 stall torque). Max continuous torque 1.0 Nm. Joint speed up to 16 rad/s under trot. Trot speed up to 0.7 m/s. Capable of bounding and jumping with a trained policy. Payload capacity 300 g for sensors and electronics.<br>
**Power** — 24V nominal from a 6S LiPo (22.2V nominal, 3000 mAh, 66.6 Wh). Runtime 20–40 minutes depending on gait and payload. XT60 connector. 24V direct to C610 motor controllers. 5V 5A buck converter for Raspberry Pi 5. 3.3V for IMU.<br>
**Thermal** — Passive cooling. Motors dissipate heat through aluminum motor mounts. No active cooling. Sustained high-torque operation will cause motor temperature rise; the C610 reports temperature and can be monitored for derating. Motor ambient temperature limit is 0–55 °C.<br>
**Environmental** — Indoor and calm outdoor. Not IP-rated. Not for rain, dust, or wet surfaces.

---

## Frame

**Bill of materials** — See detailed BOM below. Total cost approximately $1,800–$2,200 depending on sourcing and options.<br>
**Structure** — 3D-printed PA12-CF (carbon fiber reinforced nylon) body and leg links. This material was chosen for its high strength-to-weight ratio and stiffness, which is critical for torque transmission through the legs without flex. The body is a single printed chassis with mounting points for electronics and the hip mechanisms. Leg links are printed with integrated bearing seats. Total printed mass approximately 400 g.<br>
**Actuation** — 12× DJI RoboMaster M2006 P36 brushless gearmotors, each paired with a DJI C610 motor controller. The M2006 uses a 22 mm brushless DC motor with an integrated absolute encoder at the input, followed by a 36:1 planetary reduction. The actuator weighs 90 g, has a 24.4 mm diameter, 64.8 mm total length, and a 6 mm output shaft. It produces 1 N·m continuous maximum torque with a no-load speed of 500 rpm. Maximum speed at 1 N·m is 416 rpm. The C610 uses a 32-bit motor driver chip and field-oriented control (FOC) to enable precise control over motor torque. It provides CAN bus command control and supports a maximum continuous current of 10 A. The C610 weighs 17 g and measures 50×22×7.3 mm (excluding wire). This actuator combination is described as a "moderately transparent, high torque-density actuator" suitable for legged locomotion research.<br>
**Locomotion** — Legged quadruped. Trot and walk gaits. Each leg has 3 joints, enabling omnidirectional walking, turning in place, and body pose adjustment.<br>
**Manipulation** — None. Payload is sensor or small gripper only.<br>
**Power system** — 6S LiPo 3000 mAh, XT60. 24V direct to C610 controllers. 5V 5A buck converter for Raspberry Pi 5. All motor and controller wiring is 18 AWG for power and 26 AWG for CAN signal.<br>
**Wiring** — CAN bus daisy-chain across all 12 C610 controllers. Motor power distributed via a power distribution board or soldered harness. CAN bus terminated with 120 ohm resistors at both ends. Signal wires shielded where possible to reduce noise from motor switching.<br>
**Custom parts** — 3D-printed body (PA12-CF). 3D-printed upper leg links (PA12-CF). 3D-printed lower leg links (PA12-CF). 3D-printed hip housings (PA12-CF). 3D-printed electronics tray (PETG). 3D-printed foot pads (TPU for grip and shock absorption).<br>
**Fasteners** — M3 stainless steel screws and heat-set threaded inserts. M3 shoulder screws for joint pivots. M2.5 for electronics mounting.<br>
**Tools required** — 3D printer (PA12-CF capable, or outsource to a print service), hex drivers (2 mm, 2.5 mm, 3 mm), soldering iron, wire crimper, multimeter, CAN bus analyzer (optional but recommended for debugging).

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| DJI RoboMaster M2006 P36 brushless gearmotor | 12 | DJI / RoboMaster | ~$41 each | Actuators/BLDC |
| DJI RoboMaster C610 brushless motor controller | 12 | DJI / RoboMaster | ~$35 each | Actuators/driver |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| 6S LiPo 3000 mAh | 1 | Tattu / CNHL | ~$60 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| XT60 connector pair | 1 | Various | ~$3 | Power/connector |
| CAN transceiver for Teensy (if not onboard) | 1 | Various | ~$5 | Comms/CAN |
| 120 ohm termination resistors | 2 | Various | ~$1 | Comms/CAN |
| 18 AWG silicone wire | 2 m | Various | ~$5 | Wiring |
| 26 AWG silicone wire | 5 m | Various | ~$5 | Wiring |
| M3 stainless screws, heat-set inserts | assorted | McMaster | ~$30 | Fasteners |
| PA12-CF filament (or print service) | ~500 g | Bambu / Shapeways | ~$60 | Custom parts |
| TPU filament for foot pads | ~50 g | Prusament | ~$5 | Custom parts |
| PS4 or Xbox wireless controller | 1 | Various | ~$50 | Operator interface |
| USB gamepad receiver or Bluetooth dongle | 1 | Various | ~$10 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>
**Firmware** — Teensy 4.0 runs the real-time motor control loop at 1 kHz. It communicates with the 12 C610 controllers over CAN bus using the DJI protocol. The Stanford Robotics Club DJIC610Controller library provides the interface for up to 8 C610 controllers on a single CAN bus, with a recommended command rate of <1 kHz to avoid saturating CAN bus bandwidth. The library provides position (radians), velocity (radians/sec), and current (amps) feedback from each motor. It reads the IMU over I2C or SPI. It receives high-level commands from the Raspberry Pi 5 over micro-ROS serial. Raspberry Pi 5 runs Ubuntu 24.04 LTS and ROS 2 Jazzy.<br>
**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial at 921600 baud. Cyclone DDS on the LAN for remote visualization and teleoperation. The HyperDog open-source quadruped platform provides a precedent for a ROS 2 and micro-ROS based quadruped system using similar architecture.<br>
**Perception** — BNO085 9-DOF IMU with onboard sensor fusion running CEVA's SH-2 firmware on an ARM Cortex-M0+. It is a 9-DOF sensor featuring an accelerometer, gyroscope, and magnetometer, providing fused orientation (rotation vector), linear acceleration, and angular velocity at up to 400 Hz. It is described as optimized for service robots employing SLAM or other intelligent navigation solutions. Optionally, a RealSense D435i or similar depth camera for terrain sensing and autonomy.<br>
**Control** — The Teensy runs a 1 kHz loop that reads motor positions and velocities from the C610 controllers, runs a joint-space PD or impedance controller, and sends current commands back. The C610's FOC handles the inner current loop. The Raspberry Pi 5 runs higher-level locomotion control: gait generation, body pose control, and velocity tracking. A reference controller with dynamic omnidirectional gaits provides a baseline for comparison. The CERBRUS open-source quadruped uses a similar architecture with a PID-based balancer that maintains robot orientation by adjusting leg heights in real time.<br>
**Planning** — No autonomous navigation in the initial build. Optional: use ROS 2 Nav2 with a depth camera for waypoint navigation on flat terrain.<br>
**Learning** — None initially. The platform is designed for sim-to-real transfer of learned locomotion policies. The transparent, torque-controllable actuators make it possible to train policies in simulation (Isaac Gym, MuJoCo) and deploy them on hardware. Sim-to-real transfer requires accurate actuator modeling, which the M2006+C610 combination supports through its current-control mode and encoder feedback. Research demonstrates that system identification, accurate actuator models, and simulated latency are critical for successful sim-to-real transfer. Data logging of joint states, IMU, and commands enables imitation learning experiments.<br>
**Teleoperation** — Wireless gamepad (PS4 or Xbox) connected to the Raspberry Pi 5 via Bluetooth or USB. A ROS 2 node maps gamepad inputs to velocity commands and gait selection. Latency target <100 ms for local Wi-Fi.<br>
**Safety** — Software e-stop. Joint torque limits enforced in the Teensy control loop (max current per motor). Watchdog: if no command received within 500 ms, the robot enters a damping mode and holds position. Fall detection via IMU: if body pitch or roll exceeds 60°, motors are disabled.<br>
**Logging** — rosbag2 with MCAP format. Joint states, IMU data, and commands recorded at 100 Hz. Optional camera and depth data at 30 Hz. Data format compatible with LeRobot for future policy training.<br>
**Networking** — Wi-Fi 6 via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access. Optional 5G module for untethered outdoor operation.<br>
**Config files** — URDF (`quadruped.urdf.xacro`), joint limits and PID gains (`joint_params.yaml`), gait parameters (`gait_params.yaml`), micro-ROS agent config, gamepad mapping.<br>
**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `logging.launch.py`.<br>
**Dependencies** — ROS 2 Jazzy, `micro_ros_arduino`, `bno08x_driver`, `joy`, `robot_state_publisher`, `rviz2`, `rosbag2`.

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
| DJIC610Controller | Latest | github | Firmware/ESC |

---

## Interface

**Emits** — `/joint_states` (100 Hz, JointState), `/imu/data` (100 Hz, Imu), `/odom` (50 Hz, Odometry from leg kinematics), `/tf`, `/robot_status` (1 Hz).<br>
**Accepts** — `/cmd_vel` (20 Hz, Twist for body velocity), `/gait_command` (custom, for gait selection), `/teleop_input` (20 Hz from gamepad).<br>
**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (stand up), `/sit` (lie down), `/reset_odometry`.<br>
**Executes** — `/walk` (action, walk for distance), `/turn` (action, turn in place), `/stand` (action, hold standing pose).<br>
**Extensions** — `quadruped/gait_state`, `quadruped/foot_contacts`, `quadruped/motor_temps`, `quadruped/battery_state`.<br>
**Frame conventions** — `base_link` at body center. `base_footprint` at ground projection. Leg frames: `FL_hip`, `FL_upper`, `FL_lower`, `FL_foot` (front left), and equivalent for FR, RL, RR.<br>
**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — `model/quadruped.urdf.xacro`. Includes 12 revolute joints with position and velocity limits. Links: body, 4× hip, 4× upper leg, 4× lower leg, 4× foot. Joint limits from mechanical design: hip roll ±30°, hip pitch ±90°, knee pitch ±120°.<br>
**SDF** — Used for Gazebo simulation.<br>
**Calibration** — Joint zero offsets (each motor's encoder zero set to mechanical zero). IMU orientation and bias. Leg segment lengths measured from CAD. Body mass and inertia from CAD and verified by weighing.<br>
**Dynamics** — Motor constants from M2006 datasheet: 24V nominal, 500 rpm no-load, 1 N·m continuous torque, 36:1 reduction, 0.18 N·m/A torque constant, 32.96 rpm/V speed constant, 110 rpm/N·m speed-torque gradient. Leg link masses from printed parts. Body mass from electronics and chassis. Friction and damping identified through system identification experiments.<br>
**Sensor transforms** — IMU mounted at body center, 20 mm above base plate. Optional camera at front of body, 50 mm forward, 100 mm height, 10° down tilt.<br>
**Collision geometry** — Simple boxes and cylinders for links in simulation. Foot collision spheres.<br>
**Visual geometry** — STL meshes from printed parts.

---

## Trials

**Bench** — Motor direction, encoder counts, IMU readings, CAN bus communication with all 12 controllers. Pass/fail, measured values, date. Expected: all 12 motors respond to current commands, encoders report position with 8192 counts per revolution (13-bit), IMU reports orientation within 2° accuracy.<br>
**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 100 Hz. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>
**Field** — Stand, trot, turn. Trot speed measurement over 5 m. Joint torque and temperature monitoring during sustained trot. Pass/fail, measured values, date.<br>
**Endurance** — Continuous trot until battery cutoff at 3.3V per cell. Motor temperature at end (expected <55 °C ambient limit).<br>
**Environmental** — Tested on flat indoor surfaces and low-pile carpet. Limited outdoor testing on grass and gravel.<br>
**Known limitations** — No stairs. Limited rough terrain capability without a trained policy. No autonomous navigation without additional sensors. Camera depth limited outdoors by IR interference.

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
**Next steps** — Finalise BOM, order components, print parts, begin assembly. Milestone 1: bench test all actuators and CAN communication. Milestone 2: stand and hold pose. Milestone 3: trot with a reference controller. Milestone 4: sim-to-real policy deployment. Milestone 5: optional camera and autonomy.
