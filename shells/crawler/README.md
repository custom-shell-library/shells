# Crawler

**Class:** tracked<br>
**Generation:** 1<br>
**Version:** 0.1.0<br>
**Glossary:** 2026-09<br>
**Condition:** draft<br>
**Author:**<br>
**Last updated:** 2026-09-25

---

## Identity

**Role** — Small tracked robot with articulated front flippers for teleoperated inspection and traversal of confined, uneven, and hazardous indoor spaces. Holds a camera and IMU, drives over obstacles, climbs stairs, and relays sensor data to a single operator.<br>
**Environment** — Indoor hard floors, low-pile carpet, debris, shallow water, and confined spaces. Outdoor on grass, gravel, and packed dirt. Not for deep water, extreme heat, or explosive atmospheres without further certification.<br>
**Mission** — Teleoperated driving, obstacle climbing via flippers, camera inspection, and optional 2D mapping. The flippers allow the robot to climb obstacles up to 150 mm and stairs up to 30° incline.<br>
**Operator** — Single operator via Wi-Fi or tethered Ethernet. Supervised autonomy possible for waypoint following on flat terrain.<br>
**Reusability** — Repeatable build. Mix of off-the-shelf and 3D-printed components. Production candidate.

---

## Spec

**Physical** — Target 6–7 kg all-up weight (AUW) with battery. 420 × 270 × 150 mm chassis without flippers, extending to 420 × 380 × 150 mm with flippers deployed. 6061 aluminum chassis with 3D-printed PETG/TPU tracks. Ground clearance 40 mm (chassis), adjustable to 80 mm with flippers. Center of mass low and centered over the track contact patch.<br>

**Kinematic** — Differential drive, 2 tracks. Track width 80 mm, track contact length 200 mm. Drive sprocket diameter 60 mm. Two front flippers, each 120 mm long, independently actuated. Max speed 1.2 m/s. Zero-turn radius.<br>

**Dynamic** — Payload capacity 3 kg. Max obstacle climb 150 mm (with flippers). Max stair climb 30° incline. Max lateral tilt 25°. Track tension adjustable via idler positioning.<br>

**Power** — 22.2V nominal from a 6S LiPo (6S, 3000 mAh, 66.6 Wh). Runtime 2–4 hours depending on drive intensity and flipper use. XT60 connector. 24V direct to track motors. 5V 5A buck for Raspberry Pi 5. 6V 3A buck for flipper servo.<br>

**Thermal** — 0–55 °C operating (motor limit). Passive cooling. Motors have aluminum heat sinks. No active cooling. Sustained high-torque operation will raise motor temperature; current monitoring and derating are implemented in firmware.<br>

**Environmental** — IP54 (splash-resistant, dust-protected) with sealed electronics enclosure. Not submersible.

---

## Frame

**Bill of materials** — See detailed BOM below. Total estimated cost ≈ $1,100–$1,500.<br>

**Structure** — 6061 aluminum chassis, 2 mm wall thickness, CNC-milled or bent sheet. 3D-printed PETG track links with TPU traction pads. 3D-printed flipper arms (PETG or PA12-CF). 3D-printed motor mounts, idler mounts, and flipper pivot brackets. Electronics mounted inside a sealed aluminum enclosure with gasketed lid.<br>

**Actuation** — 2× brushed DC gearmotors for tracks. Selected motor: 12V 380RPM 1.4 kgf·cm brushed DC geared motor with 30:1 gearhead. This provides 137 mN·m of torque at 380 RPM, which translates to sufficient track force for a 6 kg robot on moderate inclines. 1× brushed DC gearmotor for flipper actuation, or a high-torque servo. For the flipper, a 12V 50RPM 694 oz-in brushed DC gearmotor with 100:1 reduction provides high torque for lifting the robot. Alternatively, a ballscrew-driven link mechanism can be used to change the footprint of the tracked robot, as described in research on flipper mechanisms for tracked rescue robots.<br>

**Locomotion** — Differential drive, 2 tracks. The tracks are 3D-printed links: PETG for structural strength and TPU on the bottom for traction. Each track is approximately 65 links for a 762 mm total length, depending on sprocket and idler spacing. The track links are assembled with steel pins or printed pins, depending on design. The drive sprocket is 3D-printed PETG with a D-shaft hub. The idler wheel is 3D-printed PETG with a bearing seat. Road wheels are 3D-printed PETG with rubber O-rings for shock absorption.<br>

**Manipulation** — None. Payload is sensor only. Optional small pan-tilt camera mount.<br>

**Power system** — 6S LiPo 3000 mAh, XT60. 24V direct to track motors via Cytron MDD10A. 5V 5A buck converter for Raspberry Pi 5. 6V 3A buck converter for flipper motor driver. All power wiring 18 AWG. Motor wiring 18 AWG. Signal wiring 26 AWG. XT60 connectors for battery and power distribution.<br>

**Wiring** — Track motor power: 18 AWG silicone wire. Track motor signal: 26 AWG to motor driver. Flipper motor power: 18 AWG. Flipper motor signal: 26 AWG. CAN bus between Teensy and motor drivers if using CAN-capable drivers. Encoder wiring: 26 AWG shielded. All wires routed through cable glands in the sealed enclosure.<br>

**Custom parts** — 3D-printed track links (PETG structural + TPU traction). 3D-printed drive sprockets (PETG). 3D-printed idler wheels (PETG with bearings). 3D-printed road wheels (PETG with O-rings). 3D-printed flipper arms (PETG or PA12-CF). 3D-printed flipper pivot brackets (PETG). 3D-printed motor mounts (PETG). 3D-printed electronics tray (PETG). 3D-printed camera mount (TPU for damping).<br>

**Fasteners** — M3 and M4 stainless steel. M3 for electronics and brackets. M4 for structural connections to the chassis. M3 shoulder screws for flipper pivots. M2.5 for camera mount.<br>

**Tools required** — 3D printer (PETG and TPU capable), hex drivers (2 mm, 2.5 mm, 3 mm), soldering iron, wire crimper, multimeter, M3/M4 tap set for chassis, thread locker (blue).

### Bill of Materials

| Part | Qty | Source | Cost | Hardware ref |
|:---|:---|:---|:---|:---|
| 6061 aluminum chassis plate, 2 mm, 420×270 mm | 1 | SendCutSend / local | ~$45 | Frame/plate |
| 12V 380RPM 1.4 kgf·cm brushed DC gearmotor (30:1) | 2 | Cytron / Pololu | ~$30 each | Actuators/DC |
| 12V 50RPM 694 oz-in brushed DC gearmotor (100:1) | 1 | RobotShop / Pololu | ~$35 | Actuators/DC |
| Cytron MDD10A dual motor driver (10A per channel) | 1 | Cytron | ~$25 | Actuators/driver |
| Cytron MD10C single motor driver (for flipper) | 1 | Cytron | ~$15 | Actuators/driver |
| Teensy 4.0 | 1 | PJRC | ~$25 | Compute/MCU |
| Raspberry Pi 5, 8 GB | 1 | Raspberry Pi | ~$80 | Compute/SBC |
| Raspberry Pi 5 active cooler | 1 | Raspberry Pi | ~$5 | Compute/cooling |
| 128 GB NVMe SSD + M.2 HAT | 1 | Various | ~$40 | Compute/storage |
| BNO085 9-DOF IMU | 1 | Adafruit | ~$25 | Sensors/IMU |
| Raspberry Pi Camera Module 3 | 1 | Raspberry Pi | ~$25 | Sensors/Camera |
| 6S LiPo 3000 mAh, 22.2V | 1 | Tattu / CNHL | ~$60 | Power/battery |
| 5V 5A buck converter | 1 | Pololu | ~$15 | Power/converter |
| 6V 3A buck converter | 1 | Pololu | ~$8 | Power/converter |
| XT60 connector pairs | 2 | Various | ~$6 | Power/connector |
| 18 AWG silicone wire | 3 m | Various | ~$8 | Wiring |
| 26 AWG shielded wire | 5 m | Various | ~$10 | Wiring |
| M3, M4 stainless screws, heat-set inserts | assorted | McMaster | ~$35 | Fasteners |
| PETG filament | ~750 g | Prusament | ~$30 | Custom parts |
| TPU filament | ~250 g | Prusament | ~$15 | Custom parts |
| 608ZZ bearings | 12 | Various | ~$12 | Locomotion/bearings |
| Steel pins for track links (2 mm × 10 mm) | 130 | Various | ~$10 | Locomotion/pins |
| O-rings for road wheels (30 mm ID) | 8 | Various | ~$5 | Locomotion/O-rings |
| Cable glands (M12) | 4 | Various | ~$8 | Enclosure |
| Aluminum electronics enclosure, 200×150×80 mm | 1 | Hammond / Bud | ~$40 | Enclosure |
| Gasket material for enclosure lid | 1 | Various | ~$5 | Enclosure |
| PS4 or Xbox wireless controller | 1 | Various | ~$50 | Operator interface |
| USB gamepad receiver or Bluetooth dongle | 1 | Various | ~$10 | Operator interface |

---

## Systems

**Manifest** — See detailed manifest below.<br>

**Firmware** — Teensy 4.0 runs the real-time motor control loop at 500 Hz. It reads encoder counts from both track motors, runs a PID velocity controller per track, and sends PWM and direction commands to the Cytron MDD10A. It reads the flipper position from a potentiometer or encoder and controls the flipper motor via the MD10C. It reads the BNO085 IMU over I2C. It receives high-level commands from the Raspberry Pi 5 over micro-ROS serial at 921600 baud. The Teensy 4.0 has built-in CAN controllers and can support CAN FD on CAN3 (pins 30/31) with an external transceiver like the TJA1051T/3.<br>

**Middleware** — ROS 2 Jazzy. micro-ROS between Teensy 4.0 and Raspberry Pi 5 over USB serial. Cyclone DDS on the LAN for remote visualization and teleoperation. A precedent for this architecture exists in the UGV Beast, an open-source tracked robot with a dual-controller structure (Raspberry Pi 4B/5 as host and ESP32 as sub-controller) supporting ROS 2 and WebRTC-based browser control.<br>

**Perception** — BNO085 9-DOF IMU for orientation and motion sensing. The BNO085 integrates a triaxial 12-bit accelerometer (±8g), a triaxial 16-bit gyroscope (±2000°/s), and a triaxial magnetometer, with onboard sensor fusion running on an ARM Cortex-M0+ processor. Raspberry Pi Camera Module 3 for visual inspection. Optional RPLIDAR A1M8 for 2D mapping and obstacle detection.<br>

**Control** — Teensy 4.0 runs PID velocity control per track at 500 Hz. Differential drive kinematics computed on Raspberry Pi 5. The Cytron MDD10A accepts PWM speed control up to 20 kHz and supports bidirectional control of two brushed DC motors at up to 10A continuous per channel, with 30A peak for 10 seconds. The flipper motor is controlled via the MD10C with position feedback from a potentiometer. Flipper control modes: manual (operator commands angle) and automatic (flipper auto-adjusts based on pitch angle from IMU).<br>

**Planning** — Nav2 stack for waypoint navigation on flat terrain. SLAM Toolbox for 2D mapping with LiDAR. For tracked robots, differential drive kinematics are used for odometry, and the robot can navigate using a Nav2 controller with appropriate acceleration and deceleration limits. Research on tracked vehicles in forest environments has demonstrated ORB-SLAM3 visual SLAM within a ROS 2 software setup for mapping and localization.<br>

**Learning** — None initially. Teleoperation data (cmd_vel, odometry, flipper angles, IMU) can be logged for future policy training.<br>

**Teleoperation** — Wireless gamepad (PS4 or Xbox) connected to the Raspberry Pi 5 via Bluetooth or USB. A ROS 2 node maps gamepad inputs to velocity commands for tracks and position commands for flippers. Optional WebRTC browser-based control as demonstrated on the UGV Beast platform. Latency target <100 ms for local Wi-Fi.<br>

**Safety** — Software e-stop. Motor current limits enforced in Teensy firmware. Watchdog: if no command received within 500 ms, tracks stop and flippers hold position. Fall detection via IMU: if pitch or roll exceeds 60°, motors are disabled. Thermal monitoring: motor current is monitored and derated if sustained high current is detected.<br>

**Logging** — rosbag2 with MCAP format. Track encoder counts, IMU data, flipper angles, and commands recorded at 100 Hz. Camera at 30 Hz. Optional LiDAR at 10 Hz.<br>

**Networking** — Wi-Fi 6 via Raspberry Pi 5 onboard. SSH over Tailscale for secure remote access. Optional tether for confined spaces where Wi-Fi does not penetrate.<br>

**Config files** — URDF (`crawler.urdf.xacro`), track PID gains (`track_params.yaml`), flipper limits and gains (`flipper_params.yaml`), micro-ROS agent config, gamepad mapping.<br>

**Launch files** — `bringup.launch.py`, `teleop.launch.py`, `mapping.launch.py`.<br>

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
| Nav2 | Jazzy branch | github | Planning/Nav2 |
| SLAM Toolbox | Jazzy branch | github | StateEstimation/SLAM |
| rplidar_ros | Latest | github | Perception/drivers |

---

## Interface

**Emits** — `/joint_states` (100 Hz, JointState for track encoders and flipper angle), `/imu/data` (100 Hz, Imu), `/odom` (50 Hz, Odometry from track encoders), `/tf`, `/robot_status` (1 Hz), `/camera/image_raw` (30 Hz, if camera fitted).<br>

**Accepts** — `/cmd_vel` (20 Hz, Twist for track velocity), `/flipper_command` (custom, for flipper angle), `/teleop_input` (20 Hz from gamepad).<br>

**Serves** — `/enable`, `/disable`, `/calibrate`, `/home` (retract flippers), `/reset_odometry`.<br>

**Executes** — `/navigate_to_pose` (Nav2 action), `/follow_waypoints` (Nav2 action), `/climb_obstacle` (action, deploy flippers and climb).<br>

**Extensions** — `crawler/track_current`, `crawler/flipper_angle`, `crawler/motor_temps`, `crawler/battery_state`.<br>

**Frame conventions** — `base_link` at chassis center. `base_footprint` at ground projection. Track frames: `track_left`, `track_right`. Flipper frames: `flipper_left`, `flipper_right`.<br>

**Units** — SI. Meters, meters/second, radians, seconds.

---

## Model

**URDF / Xacro** — `model/crawler.urdf.xacro`. Includes 2 continuous joints for tracks, 2 revolute joints for flippers. Links: chassis, track_left, track_right, flipper_left, flipper_right, sensor mounts.<br>

**SDF** — Used for Gazebo Harmonic simulation.<br>

**Calibration** — Track encoder ticks per revolution. Track separation (distance between track centers). Track contact length. Flipper zero position (fully retracted). IMU orientation and bias. Camera intrinsics.<br>

**Dynamics** — Track motor constants from datasheet: 12V nominal, 380 RPM no-load, 1.4 kgf·cm stall torque, 30:1 gear ratio, 137 mN·m output torque. Track friction and chassis mass (6 kg) identified through system identification. Flipper motor constants: 12V nominal, 50 RPM no-load, 694 oz-in stall torque, 100:1 reduction.<br>

**Sensor transforms** — IMU mounted at chassis center, 20 mm above base plate. Camera at front of chassis, 80 mm height, 10° down tilt. LiDAR (optional) at 120 mm height, centered.<br>

**Collision geometry** — Simple boxes for chassis and tracks in simulation. Flipper collision geometry includes the flipper arm and track link envelope.<br>

**Visual geometry** — STL meshes from printed and machined parts.

---

## Trials

**Bench** — Track motor direction, encoder counts, IMU readings, flipper motor direction, flipper position feedback. Pass/fail, measured values, date. Expected: track motors respond to PWM commands, encoders report position with sufficient resolution for odometry, IMU reports orientation within 2° accuracy, flipper motor moves to commanded angle within 5°.<br>

**Integration** — micro-ROS link at 921600 baud. ROS 2 bring-up with Cyclone DDS. Joint state publishing at 100 Hz. Teleop latency measured end-to-end. TF tree integrity verified. Pass/fail, measured values, date.<br>

**Field** — Drive test on tile, wood, low-pile carpet, gravel, grass. Obstacle climb test: 100 mm, 150 mm, 30° incline. Track tension check. Flipper deployment and retraction test. Pass/fail, measured values, date.<br>

**Endurance** — Continuous drive until battery cutoff at 3.3V per cell. Motor temperature at end (expected <70 °C with derating if exceeded).<br>

**Environmental** — Tested on flat indoor and outdoor surfaces. Splash test for IP54 enclosure. Not submersible.<br>

**Known limitations** — No deep water. No extreme heat. Track pins can wear over time and require replacement. Flipper mechanism adds complexity and potential failure point. 3D-printed tracks are not as durable as commercial tracks for heavy industrial use.

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

**Next steps** — Finalise BOM, order components, print tracks and parts, begin assembly. Milestone 1: bench test track motors and flipper actuator. Milestone 2: teleoperated driving with camera feed. Milestone 3: flipper deployment and obstacle climbing. Milestone 4: optional LiDAR and 2D mapping. Milestone 5: optional Nav2 waypoint following.
